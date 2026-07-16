---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---



### Mục tiêu Tuần 6:
* Kích hoạt kiểm tra tuân thủ tự động và tổng hợp finding từ nhiều dịch vụ bằng AWS Security Hub.
* Thiết lập kết nối mạng trực tiếp, không transitive giữa các VPC bằng VPC Peering.
* Đơn giản hóa kết nối dạng hub-and-spoke giữa nhiều VPC bằng AWS Transit Gateway.
* Tự động hóa việc tối ưu chi phí EC2 bằng AWS Lambda và đánh giá các lựa chọn cam kết của Savings Plans.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **Study - AWS Security Hub & VPC Peering:** Kích hoạt Security Standards (CIS, PCI DSS) trong Security Hub và xem điểm tuân thủ, sau đó cập nhật route table ở cả hai phía của kết nối VPC Peering và kiểm tra kết nối bằng traceroute. | 25/05/2026 | 25/05/2026 | https://000019.awsstudygroup.com/1-introduction/ |
| 3-4 | **AWS Transit Gateway:** Cấu hình route propagation và static route trên nhiều Transit Gateway Attachment, đồng thời thiết lập một Route Table riêng để cô lập traffic giữa các phân đoạn VPC cụ thể. | 26/05/2026 | 27/05/2026 | https://000020.awsstudygroup.com/1-introduction/ |
| 6 | **Optimizing EC2 Costs with Lambda:** Cấu hình rule CloudWatch Events (EventBridge) để kích hoạt Lambda function theo lịch, thêm xử lý lỗi và thông báo SNS khi thực thi thất bại, và so sánh mức tiết kiệm ước tính với Compute Savings Plan. | 29/05/2026 | 29/05/2026 | https://000022.awsstudygroup.com/1-introduction/ |

### Kết quả đạt được tuần 6:
* **Security & Monitoring (Security Hub & NACL):** Kích hoạt Security Standards để tự động đánh giá mức độ tuân thủ tài nguyên theo tiêu chuẩn CIS và PCI DSS, đồng thời có cái nhìn rõ ràng hơn về tình trạng bảo mật tổng thể của tài khoản thông qua điểm tuân thủ tổng hợp.
* **Network Architecture (VPC Peering vs Transit Gateway):** Cập nhật route table hai chiều để thiết lập kết nối VPC Peering và xác minh đường đi bằng traceroute, đồng thời sử dụng route propagation và Route Table cô lập trong Transit Gateway để kiểm soát luồng traffic giữa các phân đoạn VPC.
* **Cost Optimization (AWS Lambda):** Tự động hóa lịch start/stop EC2 bằng Lambda function được kích hoạt qua EventBridge, thêm cảnh báo SNS để phát hiện sớm các lần thực thi thất bại, và đánh giá mức độ tiết kiệm chi phí khi sử dụng Compute Savings Plan cho các workload chạy liên tục.