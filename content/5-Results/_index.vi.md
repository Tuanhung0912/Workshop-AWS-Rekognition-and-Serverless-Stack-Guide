---
title: "Kết quả thực nghiệm"
date: 2024-06-17
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

### Kiểm tra và thực hiện kết quả của ứng dụng trên cả hai chức năng

Trong phần này, bạn sẽ tiến hành triển khai ứng dụng với toàn bộ các thành phần đã được cấu hình, bao gồm API Gateway, Lambda function và S3 Bucket. Bạn sẽ kết nối giao diện người dùng (frontend) với backend serverless để xử lý các yêu cầu phân tích ảnh. Quá trình này bắt đầu khi người dùng tải ảnh lên thông qua giao diện web, và ứng dụng sẽ gửi ảnh đến API Gateway, nơi yêu cầu được chuyển tới Lambda function để thực hiện nhận diện ảnh với Amazon Rekognition. Sau khi nhận diện, kết quả sẽ được lưu trữ trong S3 Bucket và trả về cho người dùng dưới dạng liên kết để dễ dàng truy cập.

**1. Lưu lại đường link Endpoint và Routes của APIs**
- Ở phần trước, sau khi đã tạo và cấu hình 2 API là: **AnalyzeImage và UploadImage**
- Trong phần này ta cần lưu lại 2 đường link Endpoint và Routes

![RS 1](/images/5.Results/rs_1.png)

- Ở bên trái Navigation Panel, bạn hãy chọn vào mục như trong hình dưới đây:

![RS 2](/images/5.Results/rs_2.png)

- Tại trang này, sẽ hiển thị toàn bộ thông tin chi tiết của API này
- Trong phần **API details**, ở góc bên phải có phần **Default Endpoint**
- Ở đây sẽ hiển thị đường link **Invoke URL** của API, và cả trạng thái hoạt động của API
- **Bạn sẽ copy đường link Endpoint này như trong hình bên dưới:**

{{% notice info %}}
Lưu ý, đây là Endpoint API ngẫu nhiên, mỗi API sẽ có đường link khác nhau, vì vậy hãy thay thế bằng đường link API của bạn
{{% /notice %}}

![RS 3](/images/5.Results/rs_3.png)

**2. Thay thế đường link Endpoint và Routes của API AnalyzeImage**
- Quay trở lại Project Front-End ở phần 1
- Tìm thư mục và file cấu hình theo đường dẫn: **src/App.jsx**

![RS 4](/images/5.Results/rs_4.png)

- Tiếp theo, ta sẽ tìm đến hàm **handleAnalyzeImage**
- Ở hàm này, bạn sẽ thay thế **đường link API vừa Copy** ở bước trước
- **Kết quả như các hình dưới đây:**

![RS 5](/images/5.Results/rs_5.png)

![RS 11](/images/5.Results/rs_11.png)


- Kế tiếp, ta sẽ tìm đến **routes** của API đã cấu hình ở phần trước
- Và copy **routes** của method **POST** với path là **/AnalyzeImage**
- **Kết quả như các hình dưới đây:**

![RS 6](/images/5.Results/rs_6.png)

![RS 7](/images/5.Results/rs_7.png)

- Tiếp theo, ta dán vào đuôi của **Endpoint API** trong code và lưu lại như sau:

![RS 8](/images/5.Results/rs_8.png)

**3. Thay thế đường link Endpoint và Routes của API UploadImage**
- Quay trở lại Project Front-End ở phần 1
- Tìm thư mục và file cấu hình theo đường dẫn: **src/App.jsx**

![RS 4](/images/5.Results/rs_4.png)

- Tiếp theo, ta sẽ tìm đến API của **UploadImage** trên trang hệ thống
- Và sau đó copy lại **EndPoint** của API **UploadImage**
- **Kết quả như hình dưới đây:**

![RS 10](/images/5.Results/rs_10.png)

- Tiếp theo, ta sẽ tìm đến hàm **handleUploadToS3**
- Ở hàm này, bạn sẽ thay thế **đường link API vừa Copy** ở bước trước

- **Kết quả như các hình dưới đây:**

![RS 9](/images/5.Results/rs_9.png)

![RS 12](/images/5.Results/rs_12.png)

- Kế tiếp, ta sẽ tìm đến **routes** của API đã cấu hình ở phần trước
- Và copy **routes** của method **POST** với path là **/UploadImage**
- **Kết quả như các hình dưới đây:**

![RS 13](/images/5.Results/rs_13.png)

![RS 14](/images/5.Results/rs_14.png)

- Tiếp theo, ta dán vào đuôi của **Endpoint API** trong code và lưu lại như sau:

![RS 15](/images/5.Results/rs_15.png)

**4. Kiểm tra kết quả**
- Ở trong Project, dưới cửa sổ **terminal**
- Bạn hãy nhập cấu trúc câu lệnh sau để chạy trang Web:

```bash
npm run dev
```
![RS 16](/images/5.Results/rs_16.png)

- Đợi vài giây, code sẽ chạy và sẽ hiển thị đường link để truy cập trang web
- Bạn có thể di chuột vào đường link trong **Terminal** và bấm tổ hợp: **Ctrl + Click chuột trái**
- Hoặc truy cập địa chỉ [http://localhost:5173/](http://localhost:5173/) để truy cập trang web

![RS 17](/images/5.Results/rs_17.png)

- Tại trang web, sẽ có phần để bạn có thể Drop một bức ảnh hoặc chọn bức ảnh từ máy tính cá nhân như sau:

![RS 18](/images/5.Results/rs_18.png)

- Sau khi tải một ảnh bất kì từ máy tính cá nhân của bạn
- Ta có thể thấy được trang web sẽ có thể thực hiện 2 chức năng như sau: **AnalyzeImage, Upload To S3**
- Ta sẽ thực hiện theo từng bước đã **được đánh số trên ảnh** như sau:

![RS 19](/images/5.Results/rs_19.png)

Chức năng **Analyze Image (Phân tích ảnh)**:
- Sau khi đã tải ảnh lên thành công
- Bấm button **Analyze Image** để thực hiện chức năng
- Đợi một lúc, khi đó trang web sẽ hiển thị kết quả phân tích bên **Component Result**
- **Kết quả hiển thị như hình ảnh ở bên dưới:**

![RS 20](/images/5.Results/rs_20.png)

- Bạn có thể xem chi tiết **JSON Script** mà kết quả phân tích ảnh của **AWS Rekognition** trả về với các thông tin như **Label, Name, Confidence**,... Và kết quả sẽ lấy là tối đa **10 nhãn**, độ tin cậy trên **75%**
- **Labels**: nhãn
- **Name**: Tên của object
- **Confidence**: Độ tin cậy
- **Categories**: Danh mục
- **Kết quả hiện thị chi tiết như hình bên dưới:**

![RS 21](/images/5.Results/rs_21.png)

Chức năng **Upload Image (Tải ảnh cùng với kết quả phân tích lên S3)**:
- Sau khi đã thực hiện chức năng phân tích ảnh
- Tiếp theo, bạn sẽ thực hiện chức năng tải ảnh lên S3 Bucket bằng bấm vào Button **Upload To S3**
- Đợi một lúc, khi đã **tải ảnh và kết quả** lên **S3 Bucket** thành công thì hệ thống sẽ trả về thông báo thành công như hình bên dưới:

![RS 22](/images/5.Results/rs_22.png)

- Ta sẽ kiểm tra **S3 Bucket xem ảnh và kết quả phân tích** đã thực sự được tải lên chưa như sau:
- Truy cập **S3 Bucket và bấm vào tên Bucket** của bạn
- **Kết quả hiển thị như các hình ảnh dưới đây:**

![RS 23](/images/5.Results/rs_23.png)

- Ta có thể thấy rằng, S3 Bucket sẽ tự động tạo 2 Folder là: **images và results**

![RS 24](/images/5.Results/rs_24.png)


- Sau khi kiểm tra thì, bạn có thể thấy rằng sẽ có **1 ảnh** và **1 file JSON** nằm ở **thư mục** tương ứng như sau:

![RS 25](/images/5.Results/rs_25.png)

![RS 26](/images/5.Results/rs_26.png)

Chúc mừng bạn đã hoàn thành phần thực nghiệm kết quả, qua đó có thể tham khảo được một trong nhiều cách để có thể tận dụng tối đa sức mạnh của các dịch vụ AWS được triển khai trong bài lab này.






















