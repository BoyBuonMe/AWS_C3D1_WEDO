---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---



### Mục tiêu Tuần 7:
* Cấu hình mã hóa artifact và kiểm thử build nhiều giai đoạn trong pipeline CI/CD bằng AWS Developer Tools.
* Kiểm thử khả năng failover và tối ưu băng thông cho kết nối storage lai (hybrid) với File Storage Gateway.
* Cấu hình giới hạn quota, bảo vệ dữ liệu và mở rộng dung lượng cho hệ thống file chia sẻ bằng Amazon FSx.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 2-3 | **CI/CD with AWS CodePipeline:** Cấu hình trigger dựa theo branch để commit vào các nhánh khác nhau triển khai đến môi trường riêng biệt, thêm giai đoạn phê duyệt thủ công trước khi deploy production, và thiết lập rollback khi deployment thất bại. | 01/06/2026 | 02/06/2026 | https://000023.awsstudygroup.com/1-introduction/ |
| 4 | **AWS File Storage Gateway:** Cấu hình local caching để tối ưu hiệu năng đọc cho các file truy cập thường xuyên, kiểm thử lịch giới hạn băng thông (bandwidth throttling), và xác thực khả năng failover khi kết nối on-premises bị gián đoạn. | 03/06/2026 | 03/06/2026 | https://000024.awsstudygroup.com/1-introduction/ |
| 5-6 | **Amazon FSx for Windows File Server:** Tích hợp Active Directory để kiểm soát quyền truy cập theo người dùng, thiết lập backup tự động hàng ngày, và kiểm thử khả năng auto-scaling dung lượng khi mô phỏng tình huống dữ liệu tăng trưởng. | 04/06/2026 | 05/06/2026 | https://000025.awsstudygroup.com/1-introduction/ |

### Kết quả đạt được tuần 7:
* **Release Automation (DevOps & CI/CD):** Cấu hình trigger deploy theo branch cùng cổng phê duyệt thủ công để kiểm soát an toàn việc release lên production, đồng thời xác thực khả năng rollback tự động khi deployment gặp lỗi.
* **Hybrid Storage (Storage Gateway):** Cải thiện hiệu năng đọc cho các file truy cập thường xuyên nhờ local caching, và xác nhận kết nối storage vẫn duy trì khả năng phục hồi (failover) khi đường truyền on-premises bị gián đoạn.
* **Windows Storage Management (Amazon FSx):** Tích hợp Active Directory để kiểm soát quyền truy cập người dùng chi tiết hơn, tự động hóa backup hàng ngày để bảo vệ dữ liệu, và xác minh dung lượng mở rộng đúng cách khi mô phỏng tình huống dữ liệu tăng trưởng.