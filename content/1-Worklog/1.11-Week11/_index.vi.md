---
title: "Nhật ký công việc Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---


### Mục tiêu Tuần 11:

* Thiết lập môi trường phát triển và các công cụ cần thiết cho kỳ thực tập.
* Hiểu mô hình trách nhiệm chia sẻ (Shared Responsibility Model) và các khái niệm cơ bản của AWS Well-Architected Framework.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ                                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Thiết lập Git và clone repository dùng chung của kỳ thực tập <br> - Xem lại mẫu báo cáo hàng tuần và quy trình nộp bài                                                                          | 08/11/2025 | 08/11/2025      |
| 3   | - Tìm hiểu về AWS Shared Responsibility Model <br>&emsp; + Trách nhiệm của AWS <br>&emsp; + Trách nhiệm của khách hàng <br>&emsp; + Ví dụ theo từng loại dịch vụ <br>                              | 08/12/2025 | 08/12/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Kích hoạt AWS Billing Alerts và Budgets trên tài khoản Free Tier <br> - Tìm hiểu cơ bản về IAM Identity Center <br> - **Thực hành:** <br>&emsp; + Kích hoạt Billing Alarm <br>&emsp; + Tạo Budget với ngưỡng chi tiêu <br> &emsp; + Khám phá AWS Well-Architected Tool | 08/13/2025 | 08/13/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu các khái niệm bảo mật cơ bản của EC2: <br>&emsp; + Security Groups <br>&emsp; + Key Pairs <br>&emsp; + Instance Metadata <br>&emsp; + ... <br> - Hiểu các mô hình giá của EC2 <br> - Tìm hiểu về EBS Snapshots <br>                            | 08/14/2025 | 08/15/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành:** <br>&emsp; + Cấu hình Security Group với inbound rule tùy chỉnh <br>&emsp; + Tạo EBS Snapshot <br>&emsp; + Khôi phục volume từ Snapshot                                     | 08/15/2025 | 08/15/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được Tuần 11:

* Hiểu được AWS Shared Responsibility Model và cách trách nhiệm bảo mật được phân chia giữa AWS và khách hàng.

* Kích hoạt thành công Billing Alerts và cấu hình AWS Budget với ngưỡng chi tiêu trên tài khoản Free Tier.

* Làm quen với AWS Well-Architected Tool và cách sử dụng công cụ này để đánh giá workload theo best practice.

* Cấu hình các thiết lập bảo mật cơ bản của EC2, bao gồm:
  * Inbound/outbound rule tùy chỉnh của Security Group
  * Quản lý Key Pair
  * Kiến thức cơ bản về Instance Metadata

* Thực hành làm việc với EBS Snapshot, chẳng hạn như:

  * Tạo Snapshot từ một volume có sẵn
  * Khôi phục một volume mới từ Snapshot
  * Hiểu chi phí lưu trữ của Snapshot
  * ...

* Học được cách các công cụ billing và cấu hình bảo mật phối hợp với nhau để giữ tài khoản Free Tier an toàn và kiểm soát chi phí.
* ...