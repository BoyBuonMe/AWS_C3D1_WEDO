---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu tuần 2:
* Tìm hiểu quản lý danh tính và truy cập với AWS IAM.
* Thiết kế nền tảng mạng an toàn bằng Amazon VPC và Site-to-Site VPN.
* Triển khai tài nguyên máy tính trên Amazon EC2 và xử lý các vấn đề kết nối mạng.
* Xây dựng hiểu biết cơ bản về cơ sở dữ liệu quan hệ với Amazon RDS.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **AWS IAM Access Control:** Thiết lập MFA cho root user và IAM users, tạo Password Policy tùy chỉnh, viết Policy dạng JSON theo nguyên tắc Least Privilege, và thử nghiệm phân quyền giữa các Groups khác nhau. | 27/04/2026 | 27/04/2026 | https://000002.awsstudygroup.com/ |
| 3 | **Amazon VPC & Site-to-Site VPN:** Thiết kế mô hình VPC nhiều tầng (public/private subnet), cấu hình NAT Gateway cho private subnet truy cập internet, và triển khai VPC Peering giữa hai VPC khác nhau. | 28/04/2026 | 28/04/2026 | https://000003.awsstudygroup.com/ |
| 4-5 | **Amazon EC2:** Cấu hình Auto Scaling Group kết hợp Application Load Balancer cho ứng dụng Node.js, thiết lập CloudWatch Alarm để tự động scale theo tải, và tạo AMI tùy chỉnh để nhân bản môi trường. | 29/04/2026 | 30/04/2026 | https://000004.awsstudygroup.com/ |
| 6 | **Amazon RDS:** Triển khai Read Replica để tối ưu hiệu năng đọc, thực hành Point-in-Time Recovery từ bản backup, cấu hình Parameter Group tùy chỉnh, và giám sát hiệu năng bằng Performance Insights. | 01/05/2026 | 01/05/2026 | https://000005.awsstudygroup.com/ |

### Kết quả đạt được tuần 2:
- **Security & Identity (IAM):** Tăng cường bảo mật tài khoản bằng cách bật MFA, áp dụng chính sách mật khẩu tùy chỉnh, và viết các Policy JSON chi tiết theo nguyên tắc phân quyền tối thiểu (Least Privilege).
- **Networking (VPC & VPN):** Thiết kế kiến trúc mạng nhiều tầng với các subnet công khai và riêng tư, cho phép tài nguyên trong private subnet truy cập internet thông qua NAT Gateway, và kết nối hai VPC riêng biệt bằng VPC Peering.
- **Compute & Scalability (EC2):** Xây dựng hạ tầng tự động mở rộng (self-healing) cho ứng dụng Node.js bằng Auto Scaling Group kết hợp Application Load Balancer, với CloudWatch Alarm kích hoạt việc scale dựa trên tải thực tế.
- **Database Management (RDS):** Cải thiện khả năng chịu lỗi và hiệu năng của database bằng cách triển khai Read Replica, thực hành khôi phục dữ liệu về một thời điểm cụ thể (Point-in-Time Recovery), tinh chỉnh cấu hình engine qua Parameter Group tùy chỉnh, và giám sát hiệu năng truy vấn bằng Performance Insights.
