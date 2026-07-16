---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---



### Mục tiêu Tuần 10:
* Phát hiện bất thường về chi phí và dự báo chi tiêu trong tương lai bằng AWS Cost Explorer và Anomaly Detection.
* Xây dựng pipeline ETL để biến đổi dữ liệu thô trước khi catalog và truy vấn trong Data Lake.
* Cấu hình metric filter dựa trên log và dashboard đa tài khoản để giám sát hạ tầng bằng Amazon CloudWatch.

### Các nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 2-3 | **Cost Visualization:** Kích hoạt Cost Anomaly Detection để phát hiện các đợt tăng chi phí bất thường, xây dựng dự báo chi phí hàng tháng bằng tính năng forecasting của Cost Explorer, và thiết lập Cost and Usage Report (CUR) gửi về S3 để phân tích chuyên sâu hơn. | 22/06/2026 | 23/06/2026 | https://000034.awsstudygroup.com/1-introduction/ |
| 4 | **Data Lake on AWS:** Viết Glue ETL job để làm sạch và biến đổi dữ liệu thô trước khi catalog, phân vùng (partition) dữ liệu trong S3 để tăng tốc độ truy vấn Athena, và xây dựng dashboard QuickSight với các trường tính toán (calculated field) cho dự án phân tích âm nhạc. | 24/06/2026 | 24/06/2026 | https://000035.awsstudygroup.com/1-introduction/ |
| 6 | **Amazon CloudWatch:** Tạo metric filter để trích xuất custom metric từ dữ liệu log thô, xây dựng Dashboard đa tài khoản tổng hợp metric từ nhiều tài khoản AWS, và cấu hình cảnh báo Container Insights cho các lỗi ECS task. | 26/06/2026 | 26/06/2026 | https://000036.awsstudygroup.com/1-introduction/ |

### Kết quả đạt được Tuần 10:
* **Cost Management:** Kích hoạt Cost Anomaly Detection để phát hiện sớm các đợt tăng chi phí bất thường, và xây dựng pipeline Cost and Usage Report trong S3 để hỗ trợ phân tích chi phí chi tiết và chuyên sâu hơn so với chỉ dùng Cost Explorer.
* **Big Data Architecture (Data Lake):** Viết Glue ETL job để làm sạch và biến đổi dữ liệu thô trước khi catalog, đồng thời phân vùng dữ liệu trong S3 giúp cải thiện đáng kể tốc độ truy vấn Athena và giảm chi phí truy vấn cho dashboard phân tích.
* **System Monitoring (CloudWatch):** Tạo custom metric filter để trích xuất tín hiệu có ý nghĩa từ dữ liệu log thô, và xây dựng Dashboard đa tài khoản mang lại cái nhìn tổng hợp, thống nhất về tình trạng hạ tầng trên nhiều tài khoản AWS.