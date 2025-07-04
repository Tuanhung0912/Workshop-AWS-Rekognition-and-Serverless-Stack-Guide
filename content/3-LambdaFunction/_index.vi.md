---
title: "Cấu hình Lambda Funtion"
date: 2024-06-17
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### Tổng Quan

Trong phần này, bạn sẽ tiến hành cấu hình AWS Lambda Function – một thành phần cốt lõi trong hệ thống AI nhận diện ảnh thông minh. Lambda sẽ đóng vai trò xử lý trung gian: nhận ảnh từ phía người dùng thông qua API Gateway, gửi ảnh đến dịch vụ Amazon Rekognition để phân tích nội dung, xử lý kết quả và lưu trữ thông tin phân tích dưới dạng JSON trong S3. Ngoài ra, Lambda cũng sẽ ghi log toàn bộ quá trình hoạt động vào CloudWatch để phục vụ mục đích giám sát và khắc phục lỗi. Việc cấu hình đúng Lambda function là bước quan trọng để đảm bảo hệ thống hoạt động chính xác, bảo mật và mở rộng linh hoạt theo mô hình Serverless.


### Nội Dung

- [Cấu hình Analyze Function](3.1-AnalyzeFunction)
- [Cấu hình Upload Function](3.2-UploadFunction/)


