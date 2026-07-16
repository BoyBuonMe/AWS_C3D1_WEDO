---
title : "Frontend-S3"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

Trong Module này, chúng ta sẽ đưa giao diện Web (React/Next.js) của dự án WeDo Workspace lên môi trường Internet. Chúng ta sẽ lưu trữ web tĩnh trên **Amazon S3** và dùng **Amazon CloudFront** để phân phối với tốc độ cao, đồng thời bảo vệ hệ thống bằng tường lửa WAF.

### 5.6.1. Build mã nguồn Frontend
Đầu tiên, bạn cần biên dịch mã nguồn React thành các file tĩnh.
* Mở Terminal tại thư mục chứa code Frontend.
* Đảm bảo biến môi trường `.env` đã trỏ về API Endpoint của Application Load Balancer (ALB).
* Chạy lệnh: `npm run build`.
* Kết quả ta thu được thư mục `dist` chứa giao diện đã được nén tối ưu.
{{< img src="images/5-Workshop/5.6-Frontend-S3/frontend-build.jpg" alt="Build mã nguồn Frontend" >}}

### 5.6.2. Tạo S3 Bucket và Upload Web
* Truy cập **AWS Console** → **S3** → **Create bucket**.
* Bucket name: `wedo-frontend-2026`.
* Bỏ tích chọn **Block all public access** (để có thể public web hoặc truy cập qua CloudFront dễ dàng).
* Bấm **Create bucket**.
{{< img src="images/5-Workshop/5.6-Frontend-S3/s3-create.jpg" alt="Tạo S3 Bucket" >}}

* Mở Bucket vừa tạo, nhấn nút **Upload** và kéo thả toàn bộ nội dung trong thư mục `dist` lên S3.
{{< img src="images/5-Workshop/5.6-Frontend-S3/s3-upload-success.png" alt="Upload Frontend lên S3" >}}

### 5.6.3. Cấp quyền & Kích hoạt Static Website Hosting
* Chuyển sang tab **Permissions** → Cuộn xuống phần **Bucket policy** → **Edit**.
* Dán Policy cho phép `s3:GetObject` để có quyền đọc file Public:
{{< img src="images/5-Workshop/5.6-Frontend-S3/s3-policy.png" alt="Cập nhật S3 Bucket Policy" >}}

* Tiếp tục chuyển sang tab **Properties** → Cuộn xuống dưới cùng phần **Static website hosting** → **Edit**.
* Chọn **Enable** → Index document: Nhập `index.html`. Nhấn **Save changes**.
{{< img src="images/5-Workshop/5.6-Frontend-S3/s3-static-hosting.png" alt="Kích hoạt Static Hosting" >}}


**Kết quả nghiệm thu:** Khi truy cập vào đường dẫn của CloudFront (hoặc S3 Endpoint), giao diện WeDo Workspace của bạn sẽ hiện ra cực kỳ mượt mà, mọi chức năng kết nối với Backend đều hoạt động hoàn hảo!
{{< img src="images/5-Workshop/5.6-Frontend-S3/s3-result.jpg" alt="Kết quả Website hoạt động" >}}