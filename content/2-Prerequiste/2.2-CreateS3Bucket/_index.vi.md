---
title: "Tạo S3 Bucket để lưu trữ"
date: 2024-06-17
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

### Khởi tạo S3 Bucket dùng để lưu trữ hình ảnh và kết quả phân tích

**1. Truy cập vào Console và tìm dịch vụ Amazon S3**
- Truy cập vào trang [AWS Management Console](https://aws.amazon.com/console/)
- Sau đó, tiến hành đăng nhập tài khoản của bạn theo hình bên dưới:

![AWS Console](/images/2.Prerequiste/awslogin_1.png)

- Sau khi bấm vào trang thì sẽ hiển thị trang đăng nhập với các trường thông tin cần nhập như hình bên dưới:

![AWS Console](/images/2.Prerequiste/awslogin_2.png)

{{% notice warning %}}
Lưu ý, đây là điều kiện bắt buộc để có thể làm các bước tiếp theo, nếu bạn chưa có tài khoản hãy tiến hành đăng ký tài khoản
{{% /notice %}}

- **Link tham khảo cách tạo tài khoản:** [Tạo tài khoản](https://000001.awsstudygroup.com/)

- Sau khi đã đăng nhập tài khoản thành công thì sẽ chuyển người dùng đến trang chính của **AWS Manage Console** như hình bên dưới:

![AWS Console 2](/images/2.Prerequiste/aws_mainpage.png)

- Tại thanh tìm kiếm, hãy nhập **S3**
- Chọn vào dịch vụ **S3**
- **Kết quả như hình bên dưới:**

![S3 Bucket 1](/images/2.Prerequiste/s3bucket_1.png)

{{% notice tip %}}
Bạn có thể đánh dấu sao cho dịch vụ mà bạn sử dụng thường xuyên trong suốt quá trình làm, từ đó giúp bạn thuận tiện hơn trong việc truy cập nhanh chóng
{{% /notice %}}


- Tại giao diện chính của dịch vụ S3, bạn hãy bấm vào nút **Create Bucket** như hình bên dưới:

![S3 Bucket 2](/images/2.Prerequiste/s3bucket_2.png)

**2. Cấu hình cho S3 Bucket**
- Sau khi bấm vào **Create Bucket** thì sẽ chuyển đến phần khởi tạo Bucket như hình bên dưới:

![S3 Bucket 3](/images/2.Prerequiste/s3bucket_3.png)

Tại phần **General configuration:**
- AWS Region: **Asia Pacific (Singapore) ap-southeast-1** (hoặc tùy theo Region của bạn muốn sử dụng)
- Bucket type: chọn **General purpose**
- Bucket name: nhập **rekognition-image-upload-0912**

Tại phần **Object Ownership:**
- Chọn **ACLs disable (recommended)**

{{% notice info %}}
Lưu ý, Bucket Name của bạn phải là duy nhất và không trùng lặp với các Bucket khác
{{% /notice %}}

![S3 Bucket 4](/images/2.Prerequiste/s3bucket_4.png)


Tại phần **Block Public Access setting for this bucket:**
- Bỏ chọn **Block all public access**
- Bỏ chọn **Block public access to buckets and objects granted through new access control lists (ACLs)**
- Bỏ chọn **Block public access to buckets and objects granted through any access control lists (ACLs)**
- Bỏ chọn **Block public access to buckets and objects granted through new public bucket or access point policies**
- Bỏ chọn **Block public and cross-account access to buckets and objects through any public bucket or access point policies**
- Tích chọn **I acknowledge that the current settings might result in this bucket and the objects within becoming public.**

![S3 Bucket 5](/images/2.Prerequiste/s3bucket_5.png)

Tại phần **Bucket Versioning:**
- Bucket Versioning: chọn **Disable**

Tại phần **Default Encryption:**
- Encryption type: chọn **Server-side encryption with Amazon S3 manage keys (SSE-S3)**
- Bucket key: chọn **Enable**

![S3 Bucket 6](/images/2.Prerequiste/s3bucket_6.png)

- Sau khi đã hoàn thành các bước trên, cuộn xuống cuối trang và bấm **Create Bucket** như hình bên dưới:

![S3 Bucket 7](/images/2.Prerequiste/s3bucket_7.png)

- Đợi vài giây, bạn sẽ được chuyển đến trang danh sách bucket và hiển thị thông báo tạo thành công bucket như hình bên dưới:

![S3 Bucket 8](/images/2.Prerequiste/s3bucket_8.png)

Bạn đã hoàn thành bước tạo S3 Bucket để lưu trữ hình ảnh và kết quả phân tích