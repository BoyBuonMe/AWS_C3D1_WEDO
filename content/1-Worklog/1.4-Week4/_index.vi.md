---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---



### Mục tiêu Tuần 4:
* Cấu hình conditional forwarding DNS giữa hệ thống on-premise và AWS bằng Amazon Route 53 Resolver.
* Tự động hóa việc quản lý tài nguyên và trích xuất dữ liệu bằng AWS Command Line Interface (CLI), bao gồm viết script và cấu hình profile đa tài khoản.
* Tăng cường khả năng bảo vệ dữ liệu thông qua lifecycle rule và backup cross-region với AWS Backup và Amazon SNS.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **Hybrid DNS with Route 53 Resolver:** Cấu hình conditional forwarding rule để định tuyến truy vấn của các domain cụ thể giữa hệ thống DNS on-premise và Route 53, đồng thời xác thực khả năng phân giải tên miền bằng DNS query logging. | 11/05/2026 | 11/05/2026 | https://000010.awsstudygroup.com/ |
| 3-5 | **AWS Command Line Interface (CLI):** Viết shell script để tự động hóa các tác vụ khởi tạo tài nguyên thường gặp, sử dụng `--query` và JMESPath để lọc kết quả đầu ra từ CLI, và cấu hình named profile kết hợp assumed role để truy cập nhiều tài khoản. | 12/05/2026 | 14/05/2026 | https://000011.awsstudygroup.com/ |
| 6 | **System (AWS Backup & SNS):** Áp dụng lifecycle rule để chuyển dữ liệu backup sang cold storage, cấu hình bản sao backup ở khu vực khác (cross-region) phục vụ khôi phục thảm họa, và thiết lập thông báo SNS khi backup job thất bại. | 15/05/2026 | 15/05/2026 | https://000013.awsstudygroup.com/ |

### Kết quả đạt được tuần 4:
* **Networking & DNS (Route 53):** Cấu hình conditional forwarding rule để định tuyến chính xác các truy vấn DNS giữa hệ thống on-premise mô phỏng và AWS, đồng thời sử dụng DNS query logging để xác minh toàn bộ đường đi của quá trình phân giải tên miền.
* **Command Line Management (AWS CLI):** Tự động hóa các tác vụ khởi tạo tài nguyên lặp đi lặp lại bằng shell script, áp dụng JMESPath để trích xuất chính xác dữ liệu cần thiết từ kết quả CLI, và cấu hình truy cập đa tài khoản bằng named profile kết hợp assumed role.
* **Data Protection & Automation (AWS Backup & SNS):** Giảm chi phí lưu trữ dài hạn bằng cách áp dụng lifecycle rule để chuyển các bản backup cũ sang cold storage, tăng cường khả năng khôi phục thảm họa với bản sao backup cross-region, và thiết lập cảnh báo SNS để phát hiện ngay khi có backup job thất bại.