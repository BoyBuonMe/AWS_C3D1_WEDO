---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---



### Mục tiêu Tuần 8:
* Cấu hình custom WAF rule kết hợp rate-based limiting để chặn các mẫu traffic độc hại.
* Tự động hóa kiểm tra tuân thủ và phân bổ chi phí bằng Resource Group dựa trên Tag.
* Thiết kế IAM policy có điều kiện để giới hạn quyền EC2 theo Resource Tag cụ thể.
* Xây dựng dashboard Grafana tùy chỉnh với ngưỡng cảnh báo cho các metric quan trọng của AWS.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **AWS WAF:** Cấu hình rate-based rule để giới hạn tốc độ request từ một địa chỉ IP, thiết lập Managed Rule Group để chặn các input độc hại đã biết, và kiểm thử hành vi rule ở cả chế độ Count và Block. | 08/06/2026 | 08/06/2026 | https://000026.awsstudygroup.com/1-introduction/ |
| 3 | **Tags & Resource Groups:** Thiết kế chiến lược gắn tag nhất quán giữa các team và môi trường, sau đó dùng Resource Groups Tag Editor để áp dụng và kiểm tra tag hàng loạt trên nhiều loại tài nguyên. | 09/06/2026 | 09/06/2026 | https://000027.awsstudygroup.com/1-introduction/ |
| 5 | **Manage EC2 Access with IAM & Tags:** Viết IAM policy sử dụng condition key `aws:ResourceTag` để giới hạn hành động start/stop cho từng team cụ thể, và kiểm thử hành vi policy bằng IAM Policy Simulator. | 11/06/2026 | 11/06/2026 | https://000028.awsstudygroup.com/1-introduction/ |
| 6 | **Monitoring with Grafana:** Kết nối Grafana với CloudWatch làm nguồn dữ liệu, xây dựng dashboard tùy chỉnh kết hợp nhiều metric, và cấu hình thông báo cảnh báo khi vượt ngưỡng. | 12/06/2026 | 12/06/2026 | https://000029.awsstudygroup.com/1-introduction/|

### Kết quả đạt được Tuần 8:
* **Application Security (AWS WAF):** Cấu hình rate-based rule để giới hạn traffic đáng ngờ từ từng IP riêng lẻ, và xác thực hiệu quả của rule bằng cách so sánh hành vi giữa chế độ Count (chỉ ghi log) và Block (chặn thực tế).
* **Resource Organization (Tags & Resource Groups):** Thiết kế quy chuẩn gắn tag áp dụng nhất quán giữa các team, sau đó dùng Tag Editor để kiểm tra và sửa hàng loạt các tag không nhất quán trên tập tài nguyên lớn.
* **Access Control (IAM):** Viết IAM policy có điều kiện để giới hạn quyền EC2 theo Resource Tag cụ thể, và xác minh tính đúng đắn của policy bằng IAM Policy Simulator trước khi triển khai lên production.
* **Visual Monitoring (Grafana):** Kết nối Grafana trực tiếp với CloudWatch làm nguồn dữ liệu thời gian thực, và cấu hình cảnh báo theo ngưỡng để chủ động phát hiện hành vi bất thường của tài nguyên.