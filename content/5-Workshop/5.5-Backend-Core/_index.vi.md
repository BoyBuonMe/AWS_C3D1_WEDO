---
title : "Backend-Core"
date : 2024-01-01
weight : 5
chapter : false
pre : " <b> 5.5 </b> "
---

### 5.5.1. Chuẩn bị mã nguồn & Dockerfile
Trước tiên, cấu hình `application.yml` của Spring Boot cần được tinh chỉnh để đọc thông tin Database từ AWS Secrets Manager. Sau đó, chúng ta tạo một `Dockerfile` tại thư mục gốc của dự án:

```dockerfile
# Sử dụng JDK 17 làm base image
FROM eclipse-temurin:17-jdk-alpine
VOLUME /tmp
# Copy file JAR sau khi build vào container
COPY target/wedo-workspace-0.0.1-SNAPSHOT.jar app.jar
# Mở port 8080
EXPOSE 8080
# Lệnh chạy ứng dụng
ENTRYPOINT ["java","-jar","/app.jar"]
```

### 5.5.2. Đẩy Image lên Amazon ECR (Elastic Container Registry)
ECR là kho chứa các Docker Image bảo mật của AWS.
* Truy cập **AWS Console** → **Elastic Container Registry** → **Create repository**.
* Visibility settings: Chọn **Private**.
* Repository name: `wedo-backend`.
* Image tag mutability: Chọn **Mutable** (Để có thể ghi đè image bản cập nhật mới).
* Bấm **Create repository**.

{{< img src="images/5-Workshop/5.5-Backend-Core/ecr-create.jpg" alt="Tạo ECR Repository" >}}

Sau khi tạo xong, click vào repository `wedo-backend` vừa tạo, chọn nút **View push commands**. AWS sẽ cung cấp sẵn các lệnh dòng lệnh (CLI). Bạn mở Terminal trên máy tính và chạy lần lượt các lệnh để: Đăng nhập AWS, Build Docker Image, và Push Image lên kho chứa.

{{< img src="images/5-Workshop/5.5-Backend-Core/ecr-push-btn.png" alt="Xem nút Push Commands" >}}

{{< img src="images/5-Workshop/5.5-Backend-Core/ecr-terminal.jpg" alt="Thực thi lệnh Docker Build & Push" >}}
*(Lưu ý: Luôn bảo mật tuyệt đối Access Key và Secret Key của bạn khi cấu hình AWS CLI).*

### 5.5.3. Khởi tạo Cụm Amazon ECS (Cluster)
Cluster là cụm logic để quản lý các Container.
* Truy cập **AWS Console** → **Amazon ECS** → **Clusters** → **Create cluster**.
* Cluster name: `wedo-cluster`.
* Infrastructure: Chọn **AWS Fargate (serverless)**.
* Bấm **Create**.

{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-cluster.jpg" alt="Tạo ECS Cluster" >}}

### 5.5.4. Tạo Task Definition (Định nghĩa Container)
Đây là bản thiết kế chỉ định cách Container của chúng ta hoạt động và kết nối với Database an toàn.

**Bước 1: Lấy ARN của Database Secret**
* Truy cập **AWS Console** → **Secrets Manager**.
* Chọn Secret của RDS đã tạo ở Module 4.
* Copy giá trị **Secret ARN** để sử dụng cho bước sau.
{{< img src="images/5-Workshop/5.5-Backend-Core/secrets-arn.png" alt="Copy Secret ARN" >}}

**Bước 2: Khởi tạo Task Definition**
* Chuyển sang **Amazon ECS** → **Task definitions** → **Create new task definition**.
* Task definition family: `wedo-backend-task`.
* Infrastructure requirements: Chọn **AWS Fargate** (1 vCPU, 2 GB Memory).
* **Task role:** Chọn `WeDo-ECS-Task-Role`.
* **Task execution role:** Chọn `WeDo-ECS-Execution-Role`.

**Bước 3: Cấu hình Storage (Tích hợp EFS)**
* Kéo xuống phần Storage, nhấn **Add volume**.
* Đặt tên volume `wedo_backend`, Volume type chọn **EFS** và trỏ đến `wedo-uploads-efs` đã tạo ở Module 4.
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-volume.jpg" alt="Cấu hình ECS Volume" >}}

**Bước 4: Cấu hình Container & Biến môi trường**
* **Name:** `backend-container`.
* **Image URI:** Dán đường dẫn URI từ ECR.
* **Port mappings:** `8080` (TCP).
* Kéo xuống phần **Environment variables**, thêm biến môi trường để Spring Boot đọc Database an toàn:
  * Key: `SPRING_DATASOURCE_PASSWORD` (hoặc cấu trúc JSON trỏ vào secret).
  * Value type: Chọn **ValueFrom**.
  * Value: Dán **Secret ARN** đã copy ở Bước 1.
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-env-vars.jpg" alt="Cấu hình Biến môi trường" >}}
* Quay lại phần Storage của Container, mount cái Volume `wedo_backend` vào đường dẫn `/app/uploads` (Root directory).
* Nhấn **Create**.

**Kết quả:** Hệ thống báo Success, bản thiết kế Container đã sẵn sàng!
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-task-success.jpg" alt="Tạo Task Definition thành công" >}}

### 5.5.5. Cấu hình Load Balancer (ALB) & Target Group
Vì các Container Backend được đặt trong Private Subnet để bảo mật, chúng ta cần một Application Load Balancer (ALB) nằm ở Public Subnet để tiếp nhận luồng truy cập từ Internet.

**Bước 1: Tạo Target Group**
* Truy cập **EC2** → **Target Groups** → **Create target group**.
* Target type: Chọn **IP addresses** (Bắt buộc với AWS Fargate).
* Target group name: `tg-wedo-backend`.
* Protocol: **HTTP**, Port: **8080**.
* VPC: Chọn `wedo-workspace-vpc`. Bấm **Create target group**.
{{< img src="images/5-Workshop/5.5-Backend-Core/alb-tg-create.jpg" alt="Tạo Target Group" >}}

**Bước 2: Tạo Application Load Balancer**
* Truy cập **EC2** → **Load Balancers** → **Create Load Balancer** → Chọn **Application Load Balancer**.
* Name: `alb-wedo-backend`.
* Scheme: **Internet-facing**.
* Network mapping: Chọn VPC và tích chọn các **Public Subnets**.
* Security groups: Chọn SG dành riêng cho ALB (`wedo-alb-sg`).
* Listeners and routing: HTTP:80 forward về `tg-wedo-backend`.
* Bấm **Create load balancer** và chờ cấp phát thành công.
{{< img src="images/5-Workshop/5.5-Backend-Core/alb-create-success.png" alt="Tạo ALB thành công" >}}

### 5.5.6. Cập nhật ECS Service để gắn Load Balancer
Bây giờ chúng ta sẽ liên kết cụm Container đang chạy với Load Balancer vừa tạo.

* Quay lại **Amazon ECS** → Chọn Cluster `wedo-cluster`.
* Tại tab **Services**, chọn Service `wedo-backend-task-service...` và nhấn nút **Update**.
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-service-update.png" alt="Cập nhật ECS Service" >}}

* Kéo xuống phần **Networking**, đảm bảo vẫn giữ nguyên các Private Subnets và Security Group `wedo-ecs-sg`.
* Kéo xuống phần **Load balancing**, chọn **Use load balancing**.
* Load balancer type: **Application Load Balancer**.
* Load balancer: Chọn `alb-wedo-backend`.
* Container to load balance: Chọn `backend-container:8080`.
{{< img src="images/5-Workshop/5.5-Backend-Core/ecs-service-alb.png" alt="Gắn ALB vào ECS Service" >}}
* Nhấn **Update** để AWS tiến hành cấu hình lại luồng mạng.

**Kết quả:** Hệ thống Backend Core đã được bảo vệ phía sau Load Balancer, sẵn sàng tiếp nhận các API Request từ Frontend một cách an toàn và tự động phân tải!