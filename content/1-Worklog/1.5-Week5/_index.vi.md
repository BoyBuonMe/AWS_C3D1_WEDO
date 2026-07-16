---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---



### Mục tiêu Tuần 5:
* Kiểm tra tính tương thích và theo dõi tiến trình di chuyển máy ảo giữa môi trường on-premises và AWS bằng VM Import/Export.
* Tối ưu việc triển khai ứng dụng container hóa bằng Docker multi-stage build, quản lý phiên bản image trên Amazon ECR, và cấu hình Nginx cho caching cùng SSL termination.
* So sánh các launch type của Amazon ECS (Fargate và EC2) và hiểu cách pipeline CI/CD tự động kích hoạt cập nhật service khi có phiên bản image mới.
* Đánh giá các phiên bản task definition để đảm bảo khả năng rollback an toàn, đồng thời giám sát hiệu năng và log của container bằng CloudWatch Container Insights và FireLens.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **VM Import/Export:** Chuẩn bị image VMware và kiểm tra tính tương thích trước khi import, theo dõi trạng thái tác vụ chuyển đổi qua CLI, và xác minh EC2 instance kết quả khởi động đúng với cấu hình mạng nguyên vẹn. | 18/05/2026 | 18/05/2026 | https://000014.awsstudygroup.com/1-introduction/ |
| 3-5 | **Deploying Applications with Docker Containers:** Viết Dockerfile dạng multi-stage để giảm dung lượng image, đẩy các phiên bản image lên Amazon ECR, và cấu hình Nginx xử lý caching cùng SSL termination bên cạnh vai trò reverse proxy. | 19/05/2026 | 21/05/2026 | https://000015.awsstudygroup.com/1-introduction/ |
| 6 | **Study - ECS, CI/CD & Monitoring:** So sánh Fargate và EC2 launch type về chi phí và mức độ kiểm soát, đánh giá chiến lược quản lý phiên bản task definition, và tìm hiểu cách pipeline CI/CD tự động kích hoạt cập nhật ECS service khi có image mới. | 22/05/2026 | 22/05/2026 | https://000016.awsstudygroup.com/1-introduction/ <br>&emsp; https://000017.awsstudygroup.com/1-introduction/|
| 7 | Event: Participate in Event 2. | 23/05/2026 | 23/05/2026 | [View Event 2 Report](/4-eventparticipated/4.2-event2/) |

### Kết quả đạt được tuần 5:
* **Cloud Migration & Storage:** Học được cách kiểm tra tính tương thích của VM image trước khi import, theo dõi tiến trình chuyển đổi qua CLI, và xác nhận rằng instance sau khi di chuyển vẫn giữ đúng cấu hình mạng sau khi khởi động.
* **Containerization & Application Operation:** Giảm dung lượng Docker image bằng kỹ thuật multi-stage build, thiết lập quy trình quản lý phiên bản image thông qua Amazon ECR, và cấu hình Nginx xử lý caching cùng SSL termination bên cạnh việc làm reverse proxy.
* **ECS Architecture & CI/CD Automation:** So sánh giữa Fargate và EC2 launch type để hiểu rõ sự đánh đổi về chi phí và khả năng vận hành, đồng thời nắm rõ cách pipeline CI/CD tự động kích hoạt cập nhật ECS service mỗi khi có container image mới được đẩy lên.
* **Monitoring & Log Routing:** Thực hành đánh giá các phiên bản task definition để đảm bảo khả năng rollback an toàn, và tìm hiểu cách CloudWatch Container Insights kết hợp với FireLens giúp quan sát toàn diện cả về chỉ số hiệu năng lẫn luồng log trong toàn bộ hệ thống container.