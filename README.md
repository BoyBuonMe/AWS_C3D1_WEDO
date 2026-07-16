<div align="center">

# 🏢 WeDo Workspace

### Nền tảng Quản lý & Kiểm soát Công việc Nội bộ

![React](https://img.shields.io/badge/FRONTEND-REACTJS-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![Spring Boot](https://img.shields.io/badge/BACKEND-SPRING%20BOOT-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Docker](https://img.shields.io/badge/CONTAINER-DOCKER-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/CLOUD-AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![ECS Fargate](https://img.shields.io/badge/DEPLOY-ECS%20FARGATE-FF9900?style=for-the-badge)
![MySQL](https://img.shields.io/badge/DATABASE-MYSQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

[🌐 Báo cáo Workshop cá nhân](https://boybuonme.github.io/AWS_C3D1_WEDO/) | [🎥 Video Demo](https://drive.google.com/file/d/16eH8pwz3igM2FXp424WUPNWnJZ4nBn-2/view) | [📄 Trải nghiệm WeDo Workspace ](http://wedo-frontend-2026.s3-website-ap-southeast-1.amazonaws.com/)

</div>

---cu

## 📖 Tổng quan dự án

**WeDo Workspace** là nền tảng giúp doanh nghiệp phân chia, kiểm soát và quản lý công việc nội bộ một cách tập trung. Hệ thống cho phép **cấp trên phân công việc cho cấp dưới**, theo dõi **tiến độ thực hiện**, và tổng hợp báo cáo theo thời gian thực — thay thế cho việc quản lý rời rạc qua chat, email hay bảng tính thủ công.

## ✨ Tính năng chính

- 👤 **Phân quyền theo vai trò**: Quản lý / Nhân viên với luồng thao tác riêng biệt
- 📋 **Giao việc & phân công**: Cấp trên tạo, giao và điều chỉnh công việc cho cấp dưới
- 📊 **Theo dõi tiến độ**: Cập nhật trạng thái công việc (Chưa làm / Đang làm / Hoàn thành / Trễ hạn)
- 🔔 **Thông báo**: Nhắc nhở deadline và cập nhật trạng thái công việc
- 📈 **Báo cáo & thống kê**: Tổng hợp khối lượng công việc theo cá nhân/phòng ban
- 🔐 **Xác thực & bảo mật**: Đăng nhập, phân quyền truy cập theo vai trò

## 🛠️ Công nghệ sử dụng

| Thành phần | Công nghệ |
|---|---|
| Frontend | ReactJS |
| Backend | Java, Spring Boot |
| Cơ sở dữ liệu | MySQL (Amazon RDS) |
| Container hóa | Docker |
| Hạ tầng triển khai | AWS ECS Fargate |

## 🏗️ Kiến trúc hệ thống

```
Người dùng
   │
   ▼
[ ReactJS - Frontend ]
   │  REST API
   ▼
[ Spring Boot - Backend ]
   │
   ▼
[ MySQL - Amazon RDS ]
```

Frontend và Backend được đóng gói thành container Docker riêng biệt, triển khai trên AWS ECS Fargate, kết nối tới cơ sở dữ liệu MySQL trên Amazon RDS.

## 🚀 Cài đặt & chạy dự án

### Yêu cầu
- Java 17+
- Node.js 18+
- MySQL 8.0+
- Maven

### Backend
```bash
cd backend
mvn spring-boot:run
```

### Frontend
```bash
cd frontend
npm install
npm start
```

### Cấu hình kết nối Database
Chỉnh sửa file `application.properties` (hoặc `application.yml`) trong thư mục backend:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/wedo_workspace
spring.datasource.username=root
spring.datasource.password=your_password
```

## 📂 Cấu trúc thư mục

```
wedo-workspace/
├── backend/          # Spring Boot API
├── frontend/          # ReactJS App
├── docker-compose.yml
└── README.md
```


## 📄 Giấy phép

Dự án phục vụ mục đích học tập / nội bộ.