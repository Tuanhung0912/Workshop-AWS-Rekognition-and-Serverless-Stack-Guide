---
title: "Các bước chuẩn bị"
date: 2024-06-17
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

### Tổng Quan 

Trước khi bắt đầu triển khai hệ thống AI nhận diện ảnh thông minh, bạn cần chuẩn bị một số thành phần cơ bản trong môi trường AWS để đảm bảo quá trình phân tích và lưu trữ diễn ra suôn sẻ. Cụ thể, bạn sẽ tạo một S3 Bucket để lưu trữ ảnh gốc mà người dùng tải lên, cũng như các tệp kết quả phân tích ở định dạng JSON. Tiếp theo, cần cấu hình một IAM Role với các quyền truy cập phù hợp như AmazonS3FullAccess, AmazonRekognitionFullAccess, CloudWatchLogsFullAccess... để Lambda function có thể gọi dịch vụ Rekognition, ghi log vào CloudWatch và ghi dữ liệu vào S3

### Nội Dung

- [Clone và Setup Front-End](2.1-CloneFrontEnd/)
- [Tạo S3 Bucket để lưu trữ](2.2-CreateS3Bucket/)
- [Tạo IAM Role và Attach Policy](2.3-CreateIamRole/)
