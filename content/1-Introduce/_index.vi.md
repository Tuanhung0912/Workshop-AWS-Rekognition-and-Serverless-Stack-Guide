---
title: "Giới thiệu"
date: 2024-06-17
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

**Amazon Rekognition** là một dịch vụ AI mạnh mẽ của AWS, cung cấp khả năng nhận diện và phân tích hình ảnh và video. Amazon Rekognition giúp bạn nhận diện các đối tượng, khuôn mặt, văn bản, và các cảnh vật trong ảnh mà **không cần phải xây dựng mô hình học sâu phức tạp**. Dưới đây là mô hình triển khai của bài lab:

![Deployment model](/images/main.png)

**Từng bước hoạt động của mô hình:**

- Bước 1: Người dùng tải ảnh từ giao diện web để thực hiện nhận diện ảnh.
- Bước 2: Frontend gửi ảnh thông qua HTTP POST đến API Gateway để bắt đầu xử lý.
- Bước 3: API Gateway kích hoạt hàm Lambda để xử lý yêu cầu phân tích ảnh.
- Bước 4: Lambda ghi log hoạt động (event, lỗi, thông tin nhận diện) vào CloudWatch để theo dõi và giám sát.
- Bước 5: Lambda gửi ảnh đến dịch vụ Rekognition để phân tích nội dung và trích xuất thông tin.
- Bước 6: Rekognition trả về kết quả phân tích (nhãn, đối tượng, độ tin cậy) dưới dạng JSON.
- Bước 7: Lambda tạo file JSON chứa kết quả và xử lý lại ảnh đầu vào.
- Bước 8: Cả ảnh gốc và file JSON sẽ được lưu vào S3 Bucket để lưu trữ lâu dài hoặc chia sẻ.
- Bước 9: Lambda được cấp quyền thông qua IAM Role để có thể gọi Rekognition, ghi log CloudWatch và ghi dữ liệu vào S3.

**Với việc sử dụng Amazon Rekognition, bạn sẽ có được những ưu điểm sau:**

- Dễ dàng nhận diện các đối tượng và khuôn mặt trong ảnh mà không cần xây dựng mô hình AI riêng.
- Hỗ trợ phân tích văn bản trong ảnh, giúp nhận diện thông tin và chữ viết trên hình ảnh.
- Có thể cấu hình và tích hợp với các dịch vụ AWS Serverless như Lambda, S3, và API Gateway, giúp triển khai nhanh chóng và tiết kiệm chi phí.
- Tự động hóa quy trình phân tích hình ảnh và video mà không cần phần cứng đắt tiền hoặc quản lý hạ tầng.
- Cung cấp các API dễ sử dụng cho việc nhận diện hình ảnh và video, giúp lập trình viên dễ dàng tích hợp vào ứng dụng
- Quản lý các quyền truy cập và bảo mật thông qua AWS IAM để đảm bảo tính bảo mật và tuân thủ chính sách của công ty.
- Log lại các hành động và phân tích kết quả để giúp người dùng dễ dàng theo dõi và kiểm tra hiệu quả của mô hình AI.

Với những ưu điểm trên, bạn có thể sử dụng Amazon Rekognition và Serverless Stack để xây dựng các ứng dụng AI nhận diện hình ảnh thông minh, tiết kiệm thời gian và chi phí khi triển khai và bảo trì hệ thống.
