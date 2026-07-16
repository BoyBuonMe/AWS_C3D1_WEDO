---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---



### Week 5 Objectives:
* Validate VM compatibility and track migration progress when moving virtual machines between on-premises environments and AWS with VM Import/Export.
* Optimize containerized application deployment using multi-stage Docker builds, versioned Amazon ECR images, and Nginx configured for caching and SSL termination.
* Compare Amazon ECS launch types (Fargate vs EC2) and understand how CI/CD pipelines automatically trigger service updates on new image releases.
* Evaluate task definition versions for safe rollback, and monitor container performance and logs with CloudWatch Container Insights and FireLens.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **VM Import/Export:** Prepare a VMware image for compatibility checks before import, monitor the conversion task status via CLI, and verify the resulting EC2 instance boots correctly with network settings intact. | 18/05/2026 | 18/05/2026 | https://000014.awsstudygroup.com/1-introduction/ |
| 3-5 | **Deploying Applications with Docker Containers:** Write multi-stage Dockerfiles to reduce image size, push versioned images to Amazon ECR, and configure Nginx caching and SSL termination alongside its reverse proxy role. | 19/05/2026 | 21/05/2026 | https://000015.awsstudygroup.com/1-introduction/ |
| 6 | **Study - ECS, CI/CD & Monitoring:** Compare Fargate vs EC2 launch types for cost and control trade-offs, evaluate task definition versioning strategies, and study how CI/CD pipelines trigger automatic ECS service updates on new image pushes. | 22/05/2026 | 22/05/2026 | https://000016.awsstudygroup.com/1-introduction/ <br>&emsp; https://000017.awsstudygroup.com/1-introduction/|
| 7 | Event: Participate in Event 2. | 23/05/2026 | 23/05/2026 | [View Event 2 Report](/4-eventparticipated/4.2-event2/) |

### Week 5 Achievements:
* **Cloud Migration & Storage:** Learned to validate VM image compatibility ahead of import, track conversion progress through the CLI, and confirm that migrated instances retain correct networking configuration after launch.
* **Containerization & Application Operation:** Reduced Docker image size using multi-stage builds, established a versioned image workflow through Amazon ECR, and configured Nginx to handle caching and SSL termination in addition to reverse proxying.
* **ECS Architecture & CI/CD Automation:** Compared Fargate and EC2 launch types to understand their cost and operational trade-offs, and gained clarity on how CI/CD pipelines automatically trigger ECS service updates whenever a new container image is pushed.
* **Monitoring & Log Routing:** Practiced evaluating task definition versions for safe rollback, and studied how CloudWatch Container Insights and FireLens work together to give visibility into both performance metrics and log flow across the container fleet.