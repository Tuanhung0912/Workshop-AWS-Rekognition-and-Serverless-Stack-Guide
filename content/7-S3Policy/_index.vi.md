---
title: "Cập nhật Policy cho S3 Bucket (Tùy chọn)"
date: 2024-06-17
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

### Cập nhật cấu hình Policy cho S3 Bucket để có thể xem thông tin ảnh và kết quả phân tích

{{% notice note %}}
Lưu ý, đây là phần cấu hình cho Policy của S3 Bucket, để có thể xem trực tiếp ảnh và kết quả phân tích hình ảnh thông qua URL công khai, bạn có thể xem để tham khảo thêm
{{% /notice %}}

**1. Truy cập trang chi tiết thông tin phần S3 Bucket Policy**
- Ở phần 5, chúng ta đã có thể thực hiện chức năng phân tích hình ảnh và Upload hình ảnh lên **S3 Bucket**
- Tuy nhiên việc xem ảnh và kết quả sẽ bị từ chối vì chưa cài đặt **Policy cho S3 bucket**
- Đầu tiên, ta bấm vào hình ảnh như sau:

![RS 26](/images/5.Results/rs_26.png)

- Sau đó, hệ thống sẽ chuyển người dùng đến trang xem thông tin chi tiết của **Object** đó
- Tại trang thông tin chi tiết của **Object (hình ảnh)**, nhìn sang góc bên phải ta sẽ thấy một mục **Object URL**
- Đây chính là **URL của Object**, bạn có thể **click chuột** hoặc **copy** ra một tab trình duyệt mới để xem:
- **Kết quả hiển thị như các hình ảnh bên dưới:**

![Bucket 1](/images/7.S3Policy/bucket_1.png)

![Bucket 2](/images/7.S3Policy/bucket_2.png)

- Sau khi truy cập đường link URL của Object, ta có thể thấy được hệ thống báo **Access Denied** và không hiển thị được hình ảnh

**2. Cấu hình cho S3 Bucket Policy để xem ảnh và kết quả phân tích**
- Quay trở lại trang danh sách **Bucket**, bấm vào tên **Bucket**

![Bucket 3](/images/7.S3Policy/bucket_3.png)

- Tại đây, bạn sẽ chuyển sang tab **Permission** như hình sau:

![Bucket 4](/images/7.S3Policy/bucket_4.png)

- Tại trang thông tin của tab **Permission**
- Lăn chuột xuống một đoạn
- Bạn sẽ thấy được phần **Bucket policy**, nhìn qua bên phải bấm button **Edit**
- Điều này cho phép bạn chỉnh sửa **policy** của **Bucket**

![Bucket 5](/images/7.S3Policy/bucket_5.png)

- Sau khi chuyển đến phần **Edit Bucket Policy**, bạn có thể thấy được phần chúng ta sẽ chỉnh sửa là thêm vào một đoạn **JSON Script** như hình ảnh bên dưới:

![Bucket 6](/images/7.S3Policy/bucket_6.png)

- Tại đây, bạn sẽ tiến hành cấu hình cho **Bucket policy** bằng đoạn mã **JSON**
- Bạn sẽ nhập đoạn cấu hình với cấu trúc như sau:

```json
{
  "Version": "2012-10-17",  // Phiên bản của policy, theo chuẩn của AWS IAM
  "Statement": [
    {
      "Sid": "AllowPublicReadAccessToImagesAndResultFolders",  // Mã định danh cho policy statement (có thể thay đổi để dễ nhận diện)
      "Effect": "Allow",  // Chỉ định hành động "Allow" (cho phép) đối với các hành động được mô tả dưới đây
      "Principal": "*",  // Chỉ định rằng tất cả người dùng (Public Access) đều có thể thực hiện hành động này
      "Action": "s3:GetObject",  // Cấp quyền thực hiện hành động "s3:GetObject", tức là cho phép người dùng đọc (GET) đối tượng từ S3
      "Resource": [  // Cấp quyền cho các tài nguyên cụ thể dưới đây
        "arn:aws:s3:::your-bucket-name/images/*",  // Cho phép truy cập đối với các đối tượng trong thư mục "images" của bucket
        "arn:aws:s3:::your-bucket-name/results/*"  // Cho phép truy cập đối với các đối tượng trong thư mục "results" của bucket
      ]
    }
  ]
}
```
{{% notice info %}}
Lưu ý, hãy thay thế bằng tên S3 Bucket của bạn
{{% /notice %}}

- Sau khi cấu hình như đoạn mã trên, ta sẽ có kết quả như hình bên dưới
- Ta tiến hành lưu thay đổi bằng cách bấm vào Button **Save changes**

![Bucket 7](/images/7.S3Policy/bucket_7.png)

![Bucket 8](/images/7.S3Policy/bucket_8.png)

- Đợi một vài giây, hệ thống xử lý và sẽ trả về **thông báo thành công** cùng với phần **Bucket policy** đã được cập nhật trên trang web như sau:

![Bucket 9](/images/7.S3Policy/bucket_9.png)

- Quay trở lại trang hiện thị thông tin chi tiết của **Object**
- Truy cập đường link **URL của Object**
- **Kết quả sẽ hiển thị như các hình ảnh bên dưới:**

![Bucket 1](/images/7.S3Policy/bucket_1.png)

- Tại đây, ta đã có thể xem được hình ảnh trực tiếp thông qua **URL công khai của object** như hình ảnh dưới đây:

![Bucket 10](/images/7.S3Policy/bucket_10.png)

- Tương tự, trong phần **Edit Policy** của Bucket ta cũng đã đồng thời cấu hình cho thư mục **/result** để có thể xem được kết quả phân tích hình ảnh như hình ảnh bên dưới:

![Bucket 11](/images/7.S3Policy/bucket_11.png)

![Bucket 12](/images/7.S3Policy/bucket_12.png)

![Bucket 13](/images/7.S3Policy/bucket_13.png)

Qua phần này, bạn có thể tham khảo thêm cách làm sao để chúng ta có thể xem được hình ảnh và kết quả phân tích một cách trực tiếp nhanh chóng hơn.








