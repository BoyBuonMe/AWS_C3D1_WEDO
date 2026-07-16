---
title : "Backend-Core"
date : 2024-01-01
weight : 5
chapter : false
pre : " <b> 5.5 </b> "
---

### 5.5.1. Prepare Source Code & Dockerfile
First, the Spring Boot `application.yml` configuration needs to be fine-tuned to read Database credentials from AWS Secrets Manager. Then, we create a `Dockerfile` at the root directory of the project:

```dockerfile
# Use JDK 17 as the base image
FROM eclipse-temurin:17-jdk-alpine
VOLUME /tmp
# Copy the compiled JAR file into the container
COPY target/wedo-workspace-0.0.1-SNAPSHOT.jar app.jar
# Expose port 8080
EXPOSE 8080
# Command to run the application
ENTRYPOINT ["java","-jar","/app.jar"]
```

### 5.5.2. Push Image to Amazon ECR (Elastic Container Registry)
ECR is AWS's secure Docker Image repository.
* Access **AWS Console** → **Elastic Container Registry** → **Create repository**.
* Visibility settings: Select **Private**.
* Repository name: `wedo-backend`.
* Image tag mutability: Select **Mutable** (To allow overwriting with new image updates).
* Click **Create repository**.

{{< img src="images/5-Workshop/5.5-Backend-Core/ecr-create.jpg" alt="Create ECR Repository" >}}

After creation, click on the newly created `wedo-backend` repository, and select the **View push commands** button. AWS will provide command-line interface (CLI) commands. Open the Terminal on your machine and run the commands sequentially to: Authenticate with AWS, Build the Docker Image, and Push the Image to the repository.

{{< img src="images/5-Workshop/5.5-Backend-Core/ecr-push-btn.png" alt="View Push Commands Button" >}}

{{< img src="images/5-Workshop/5.5-Backend-Core/ecr-terminal.jpg" alt="Execute Docker Build & Push commands" >}}
*(Note: Always keep your Access Key and Secret Key absolutely secure when configuring the AWS CLI).*

### 5.5.3. Initialize Amazon ECS Cluster
A Cluster is a logical grouping used to manage Containers.
* Access **AWS Console** → **Amazon ECS** → **Clusters** → **Create cluster**.
* Cluster name: `wedo-cluster`.
* Infrastructure: Select **AWS Fargate (serverless)**.
* Click **Create**.

{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-cluster.jpg" alt="Create ECS Cluster" >}}

### 5.5.4. Create Task Definition (Container Definition)
This is the blueprint specifying how our Container operates and securely connects to the Database.

**Step 1: Retrieve Database Secret ARN**
* Access **AWS Console** → **Secrets Manager**.
* Select the RDS Secret created in Module 4.
* Copy the **Secret ARN** value for the next step.
{{< img src="images/5-Workshop/5.5-Backend-Core/secrets-arn.png" alt="Copy Secret ARN" >}}

**Step 2: Initialize Task Definition**
* Navigate to **Amazon ECS** → **Task definitions** → **Create new task definition**.
* Task definition family: `wedo-backend-task`.
* Infrastructure requirements: Select **AWS Fargate** (1 vCPU, 2 GB Memory).
* **Task role:** Select `WeDo-ECS-Task-Role`.
* **Task execution role:** Select `WeDo-ECS-Execution-Role`.

**Step 3: Configure Storage (Integrate EFS)**
* Scroll down to the Storage section, click **Add volume**.
* Name the volume `wedo_backend`, select **EFS** for Volume type, and point it to the `wedo-uploads-efs` created in Module 4.
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-volume.jpg" alt="Configure ECS Volume" >}}

**Step 4: Configure Container & Environment Variables**
* **Name:** `backend-container`.
* **Image URI:** Paste the URI path from ECR.
* **Port mappings:** `8080` (TCP).
* Scroll down to the **Environment variables** section, add environment variables for Spring Boot to read the Database securely:
  * Key: `SPRING_DATASOURCE_PASSWORD` (or JSON structure pointing to the secret).
  * Value type: Select **ValueFrom**.
  * Value: Paste the **Secret ARN** copied in Step 1.
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-env-vars.jpg" alt="Configure Environment Variables" >}}
* Go back to the Container's Storage section, mount the `wedo_backend` Volume to the path `/app/uploads` (Root directory).
* Click **Create**.

**Result:** The system reports Success; the Container blueprint is ready!
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-task-success.jpg" alt="Create Task Definition Successfully" >}}

### 5.5.5. Configure Load Balancer (ALB) & Target Group
Because the Backend Containers are placed in a Private Subnet for security, we need an Application Load Balancer (ALB) located in a Public Subnet to receive incoming traffic from the Internet.

**Step 1: Create Target Group**
* Access **EC2** → **Target Groups** → **Create target group**.
* Target type: Select **IP addresses** (Mandatory for AWS Fargate).
* Target group name: `tg-wedo-backend`.
* Protocol: **HTTP**, Port: **8080**.
* VPC: Select `wedo-workspace-vpc`. Click **Create target group**.
{{< img src="images/5-Workshop/5.5-Backend-Core/alb-tg-create.jpg" alt="Create Target Group" >}}

**Step 2: Create Application Load Balancer**
* Access **EC2** → **Load Balancers** → **Create Load Balancer** → Select **Application Load Balancer**.
* Name: `alb-wedo-backend`.
* Scheme: **Internet-facing**.
* Network mapping: Select the VPC and check the **Public Subnets**.
* Security groups: Select the SG dedicated to the ALB (`wedo-alb-sg`).
* Listeners and routing: Forward HTTP:80 to `tg-wedo-backend`.
* Click **Create load balancer** and wait for successful provisioning.
{{< img src="images/5-Workshop/5.5-Backend-Core/alb-create-success.png" alt="Create ALB Successfully" >}}

### 5.5.6. Update ECS Service to Attach Load Balancer
Now we will link the running Container cluster to the newly created Load Balancer.

* Go back to **Amazon ECS** → Select the Cluster `wedo-cluster`.
* Under the **Services** tab, select the Service `wedo-backend-task-service...` and click the **Update** button.
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-service-update.png" alt="Update ECS Service" >}}

* Scroll down to the **Networking** section, ensuring the Private Subnets and Security Group `wedo-ecs-sg` remain unchanged.
* Scroll down to the **Load balancing** section, select **Use load balancing**.
* Load balancer type: **Application Load Balancer**.
* Load balancer: Select `alb-wedo-backend`.
* Container to load balance: Select `backend-container:8080`.
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-service-alb.png" alt="Attach ALB to ECS Service" >}}
* Click **Update** to let AWS proceed with reconfiguring the network flow.

**Result:** The Backend Core system is now protected behind the Load Balancer, ready to safely and automatically load-balance incoming API Requests from the Frontend!