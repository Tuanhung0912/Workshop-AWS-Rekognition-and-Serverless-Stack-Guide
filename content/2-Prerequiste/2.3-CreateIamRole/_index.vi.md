---
title: "Tạo IAM Role và Attach Policy"
date: 2024-06-17
weight: 3
chapter: false
pre: " <b> 2.3 </b> "
---

### Tạo IAM Role mới và Attach Policy vào cho Role

**1. Tìm kiếm và truy cập dịch vụ IAM để tạo Role**
- Tại thanh tìm kiếm, nhập vào **IAM**
- Sau khi tìm kiếm, bấm vào dịch vụ **IAM** như hình bên dưới:

![Role 1](/images/2.Prerequiste/role_1.png)

- Tại trang dịch vụ của IAM, ở bên trái Navigation Panel
- Chọn **Roles** như hình bên dưới:

![Role 2](/images/2.Prerequiste/role_2.png)

- Tại trang Role, ta có thể thấy được danh sách nhiều Role phổ biến và hay sử dụng của AWS
- Ở phía bên phải, bạn hãy bấm button **Create Role** như sau:

![Role 3](/images/2.Prerequiste/role_3.png)

**2. Tạo mới Role và cấu hình chi tiết**
- Tại trang tạo mới **Role**, ta có thể nhìn thấy khi tạo **Role** khi cần trải qua 3 bước chính như hình bên dưới:

![Role 4](/images/2.Prerequiste/role_4.png)

Tại phần **Select Trusted entity:**
- Trusted entity type: Chọn **AWS Service**

Tại phần **Use Case:**
- Service or use case: chọn **Lambda**
- Sau đó bấm button **Next**

![Role 5](/images/2.Prerequiste/role_5.png)

- Tại trang thực hiện **bước 2 Add permissions cho Role**, bạn có thể thấy được hơn 1000+ Permission Policy như hình bên dưới:

![Role 6](/images/2.Prerequiste/role_6.png)

- Tuy nhiên, bạn chỉ cần tìm một vài Policy phù hợp với bài Lab
- Ở đây, ta sẽ tìm kiếm và chọn 3 Policy cần sử dụng như sau: **AmazonS3FullAccess, AmazonRekognitionFullAccess, CloudWatchLogsFullAccess.**
- Sau khi đã chọn xong, bạn hãy bấm button **Next**
- **Kết quả như các hình bên dưới:**

![Role 7](/images/2.Prerequiste/role_7.png)
![Role 8](/images/2.Prerequiste/role_8.png)
![Role 9](/images/2.Prerequiste/role_9.png)

- Tại trang thực hiện **bước 3: Name, review, and create**, Bạn sẽ xem lại toàn bộ cấu hình của cả hai bước trên

Tại phần **Role details:**
- Role name: ta sẽ đặt tên cho Role, Ví dụ: **LambdaAnalyzeRole**
- Description: bạn có thể để mặc định hoặc ghi chú tùy ý

![Role 10](/images/2.Prerequiste/role_10.png)

- Ở phần **Step 2: Add Permission**, bạn có thể xem lại các Policy đã thêm vào trước đó một cách chi tiết
- Sau khi đã kiểm tra toàn bộ các thông tin thì bạn bấm **Create Role** để tiến hành tạo Role

![Role 11](/images/2.Prerequiste/role_11.png)

- Đợi vài giây, sau khi tạo xong hệ thống sẽ chuyển bạn về trang chủ của phần **Role** và hiển thị thông báo tạo thành công như hình bên dưới:

![Role 12](/images/2.Prerequiste/role_12.png)

Bạn đã hoàn thành các bước chuẩn bị cần thiết để có thể làm bước tiếp theo