---
title: "Xem Logs hoạt động bằng CloudWatch"
date: 2024-06-17
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

### Kiểm Tra Logs hoạt động của trang Web bằng CloudWatch

**1. Tìm kiếm và truy cập trang dịch vụ của CloudWatch**
- Trên thanh tìm kiếm, bạn hãy nhập: **CloudWatch**
- **Kết quả hiển thị như hình ảnh bên dưới:**

![CW 1](/images/6.CloudWatch/cw_1.png)

- Tại trang chủ chính của dịch vụ **CloudWatch**
- Ở phía bên trái Navigation Panel, bạn hãy chọn **Log groups**
- **Kết quả hiển thị như hình ảnh bên dưới:**

![CW 2](/images/6.CloudWatch/cw_2.png)

**2. Kiểm tra và xem Logs hoạt động**
- Tại trang chính của **Log groups**
- Ta có thể thấy được, có 2 **Log group** được tạo tự động, sau khi chúng ta thực hiện chức năng **Analyze Image** và **Upload Image** ở phần trước
- Đây chính là phần chúng ta có thể kiểm tra chức năng hoạt động ra sao

![CW 3](/images/6.CloudWatch/cw_3.png)

- Chọn vào **Log group** chức năng **Analyze Image**
- Trong trang chi tiết **Log group** của chức năng **Analyze Image**
- Ta có thể thấy được các thông tin chi tiết khác
- Đặc biệt là **Log Streams**, đây chính là các **luồng hoạt động chính** mỗi khi ta thực hiện chức năng, mỗi lần thực hiện chức năng sẽ thêm một **Log Streams** để ghi lại hoạt động chi tiết của lần thực hiện chức năng đó

![CW 4](/images/6.CloudWatch/cw_4.png)

- Đây là chi tiết luồng hoạt động chức năng **Log Streams**:

![CW 5](/images/6.CloudWatch/cw_5.png)

- Ta sẽ thử thực hiện một ví dụ minh họa khi mà thực hiện chức năng **Analyze Image** bị lỗi và xem kết quả **Log Streams**
- Đầu tiên, vào **Lambda Function** của chức năng **Analyze Image**
- Sau đó tiến hành sửa nội dung một đoạn code bất kì như sau:

![CW 6](/images/6.CloudWatch/cw_6.png)

- **Giải thích:** ta sẽ sửa dòng code như hình trên để **lambda function** không thể gọi được client của dịch vụ **AWS Rekognition** khi đó hệ thống sẽ báo lỗi trên Front-End vì không thể thực hiện được chức năng phân tích hình ảnh và ghi lại **Log Streams** bị lỗi như các hình ảnh sau:

![CW 7](/images/6.CloudWatch/cw_7.png)

![CW 8](/images/6.CloudWatch/cw_8.png)

![CW 9](/images/6.CloudWatch/cw_9.png)

Qua phần này, các bạn có thể hiểu sở về cách hoạt động của **Log groups** trong **CloudWatch** là như thế nào, dịch vụ này sẽ giúp các bạn thuận tiện hơn khi theo dõi hoạt động của ứng dụng và dễ dàng có thể hiển thị toàn bộ thông tin lỗi, từ đó có thể dễ dàng Debug hơn.

