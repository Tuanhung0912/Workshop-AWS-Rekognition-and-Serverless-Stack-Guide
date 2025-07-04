---
title: "Cấu hình API Gateway"
date: 2024-06-17
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

### Tổng Quan

Trong phần này, bạn sẽ tiến hành cấu hình Amazon API Gateway – thành phần đóng vai trò cầu nối giữa giao diện người dùng (frontend) và backend serverless (AWS Lambda). API Gateway sẽ tiếp nhận các yêu cầu HTTP từ ứng dụng web (chẳng hạn như khi người dùng tải ảnh lên), sau đó chuyển tiếp các yêu cầu này đến Lambda function để xử lý. Việc cấu hình đúng API Gateway giúp đảm bảo hệ thống có thể giao tiếp ổn định, bảo mật và mở rộng linh hoạt. Đồng thời, bạn cũng sẽ cấu hình CORS (Cross-Origin Resource Sharing) để cho phép ứng dụng web truy cập tài nguyên API một cách hợp lệ, đặc biệt khi frontend và backend được triển khai trên các miền khác nhau. Đây là bước quan trọng giúp hoàn thiện quy trình giao tiếp giữa frontend React và các dịch vụ AWS phía sau.

### Nội Dung

- [Cấu hình API Analyze Image](4.1-AnalyzeImage)
- [Cấu hình API Upload Image](4.2-UploadImage/)

