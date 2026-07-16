---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---


### Mục tiêu Tuần 3:
* Triển khai ứng dụng có khả năng tự động mở rộng và cân bằng tải bằng Auto Scaling và ELB.
* Theo dõi, quản lý và tối ưu chi phí AWS bằng AWS Budgets.
* Giám sát hệ thống, tài nguyên và ứng dụng chuyên sâu bằng Amazon CloudWatch.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **Auto Scaling Group & Load Balancer:** Cấu hình health check và target group cho ALB, thiết lập scaling policy (target tracking và step scaling), và mô phỏng tình huống tăng traffic đột biến để kiểm chứng khả năng scale-out/scale-in. | 04/05/2026 | 04/05/2026 | https://000006.awsstudygroup.com/ |
| 3 | **Cost Management with AWS Budgets:** Tạo Budget với bộ lọc tùy chỉnh theo service và tag, cấu hình thông báo qua SNS, và phân tích xu hướng chi tiêu lịch sử bằng Cost Explorer kết hợp với Budgets. | 05/05/2026 | 05/05/2026 | https://000007.awsstudygroup.com/ |
| 4-5 | **Amazon CloudWatch:** Tạo custom metric và metric filter từ dữ liệu log, cấu hình Composite Alarm kết hợp nhiều điều kiện, và thiết lập truy vấn CloudWatch Logs Insights để xử lý lỗi ứng dụng. | 06/05/2026 | 07/05/2026 | https://000008.awsstudygroup.com/ |
| 7 | **Event 1** | 09/05/2026 | 09/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 3:
* **Scalable Architecture (Auto Scaling & ELB):** Cấu hình health check và target group để đảm bảo chỉ những instance khỏe mạnh mới nhận traffic, đồng thời kiểm chứng khả năng tự động scale-out/scale-in dưới tải mô phỏng bằng target tracking policy.
* **Cost Control (AWS Budgets):** Xây dựng các budget chi tiết phân theo service và tag, tích hợp SNS để nhận cảnh báo theo thời gian thực, và sử dụng Cost Explorer để nhận diện xu hướng chi tiêu cùng cơ hội tối ưu chi phí.
* **System Monitoring (CloudWatch):** Tạo custom metric từ dữ liệu log và cấu hình Composite Alarm để giảm nhiễu cảnh báo do false positive, đồng thời sử dụng Logs Insights để nhanh chóng xác định nguyên nhân gốc rễ của lỗi ứng dụng.