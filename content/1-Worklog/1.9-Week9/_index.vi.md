---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---



### Mục tiêu Tuần 9:
* Ngăn chặn leo thang đặc quyền bằng cách giới hạn quyền tối đa với IAM Permission Boundary.
* Tự động hóa báo cáo tuân thủ patch và thực thi script từ xa bằng AWS Systems Manager.
* Phân tích mức sử dụng bộ nhớ và nhận đề xuất rightsizing bằng CloudWatch Agent và Compute Optimizer.
* Kích hoạt xoay vòng key tự động với AWS KMS, và truy vấn log hoạt động API đã mã hóa bằng CloudTrail và Athena.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **IAM Permission Boundary:** Gắn Permission Boundary cho một IAM user để giới hạn quyền tối đa mà user đó có thể ủy quyền, sau đó thử cấp quyền vượt mức để xác minh boundary chặn được hành vi leo thang đặc quyền. | 15/06/2026 | 15/06/2026 | https://000030.awsstudygroup.com/1-introduction/ |
| 3 | **AWS Systems Manager:** Cấu hình Patch Baseline với quy tắc phê duyệt tùy chỉnh, lên lịch patching qua Maintenance Window, và dùng Run Command để thực thi script trên nhóm instance được lọc theo tag. | 16/06/2026 | 16/06/2026 | https://000031.awsstudygroup.com/1-introduction/ |
| 4 | **EC2 Right-sizing:** Cấu hình CloudWatch Agent để thu thập custom metric về bộ nhớ và ổ đĩa, sau đó tạo và phân tích đề xuất từ Compute Optimizer để xác định các instance đang dư thừa tài nguyên. | 17/06/2026 | 17/06/2026 | https://000032.awsstudygroup.com/1-introduction/ |
| 6 | **Encryption with AWS KMS:** Kích hoạt xoay vòng key tự động hàng năm cho KMS key, áp dụng key policy giới hạn quyền decrypt cho các role cụ thể, và viết truy vấn Athena để lọc log CloudTrail tìm các lần thử decrypt trái phép. | 19/06/2026 | 19/06/2026 | https://000033.awsstudygroup.com/1-introduction/ |
| 7 | **Event:** Participate in Event 3. | 20/06/2026 | 20/06/2026 | FCAJ Event |

### Kết quả đạt được Tuần 9:
* **Access Control Security (IAM):** Cấu hình Permission Boundary để giới hạn quyền tối đa mà một IAM user có thể cấp, và xác nhận qua kiểm thử rằng các nỗ lực vượt giới hạn đều bị chặn đúng cách.
* **Operational Automation (Systems Manager):** Thiết lập Patch Baseline tùy chỉnh kết hợp Maintenance Window theo lịch, và dùng Run Command để thực thi script trên nhóm instance lọc theo tag mà không cần truy cập SSH thủ công.
* **Cost & Performance Optimization (EC2 Right-sizing):** Thu thập metric bộ nhớ chi tiết qua cấu hình CloudWatch Agent tùy chỉnh, sau đó dùng đề xuất từ Compute Optimizer để xác định và khắc phục các instance đang dư thừa tài nguyên.
* **Data Security (KMS & Data logs):** Kích hoạt xoay vòng key tự động và giới hạn quyền decrypt thông qua key policy có phạm vi cụ thể, sau đó dùng Athena để truy vấn log CloudTrail và phát hiện các lần thử decrypt trái phép.