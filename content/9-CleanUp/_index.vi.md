---
title: "Dọn dẹp tài nguyên"
date: 2024-06-17
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

### Dọn dẹp tài nguyên dịch vụ sau khi sử dụng

**1. Dọn dẹp dịch vụ IAM**
- Tại thanh tìm kiếm, nhập **IAM**
- Tại trang dịch vụ **IAM**, bên trái thanh Navigation Panel chọn **Role**
- Tại trang Roles, tìm kiếm **LambdaAnalyzeRole**, tích chọn **LambdaAnalyzeRole**
- Bấm button **Delete**, nhập tên Role: **LambdaAnalyzeRole**

![Clean 1](/images/9.CleanUp/clean_1.png)

![Clean 2](/images/9.CleanUp/clean_2.png)

![Clean 3](/images/9.CleanUp/clean_3.png)

![Clean 4](/images/9.CleanUp/clean_4.png)

**2. Dọn dẹp dịch vụ S3**
- Tại thanh tìm kiếm, nhập **S3**
- Tại trang **General purpose buckets**, chọn **bucket** muốn xóa
- Bấm button **Empty** để xóa toàn bộ **Object của bucket** trước khi xóa **Bucket**
- Nhập **permanently delete** và bấm **Empty** để xóa **Object**
- Quay trở lại, chọn **bucket** muốn xóa, bấm **Delete**
- Nhập tên **bucket của bạn**, bấm **Delete Bucket**

![Clean 5](/images/9.CleanUp/clean_5.png)

![Clean 6](/images/9.CleanUp/clean_6.png)

![Clean 7](/images/9.CleanUp/clean_7.png)

![Clean 8](/images/9.CleanUp/clean_8.png)

![Clean 9](/images/9.CleanUp/clean_9.png)

**3. Dọn dẹp dịch vụ Lambda**
- Tại thanh tìm kiếm, nhập **Lambda**
- Tích chọn các **function** muốn xóa, bấm vào button **Action**, chọn **Delete**
- Nhập **confirm** và bấm **Delete**

![Clean 10](/images/9.CleanUp/clean_10.png)

![Clean 11](/images/9.CleanUp/clean_11.png)

![Clean 12](/images/9.CleanUp/clean_12.png)

**4. Dọn dẹp dịch vụ CloudWatch**
- Tại thanh tìm kiếm, nhập **CloudWatch**
- Tại trang chính **CloudWatch**, bên trái **Navigation Panel** chọn **Log groups**
- Chọn **Log group** muốn xóa, bấm vào **Action**, chọn **Delete log group(s)**
- Tại cửa sổ nổi, chọn **Delete**

![Clean 13](/images/9.CleanUp/clean_13.png)

![Clean 14](/images/9.CleanUp/clean_14.png)

![Clean 15](/images/9.CleanUp/clean_15.png)

![Clean 16](/images/9.CleanUp/clean_16.png)

**5. Dọn dẹp dịch vụ API Gateway**
- Tại thanh tìm kiếm, nhập **API Gateway**
- Chọn **API** muốn xóa, bấm **Delete** ở bên phải
- Nhập **confirm**, bấm **Delete**
- Thực hiện tương tự với API còn lại

![Clean 17](/images/9.CleanUp/clean_17.png)

![Clean 18](/images/9.CleanUp/clean_18.png)

![Clean 19](/images/9.CleanUp/clean_19.png)

##### Chúc mừng, bạn đã hoàn thành toàn bộ bài lab, qua phần này sẽ giúp bạn tiết kiệm chi phí sử dụng cho các dịch vụ AWS không còn sử dụng. Cảm ơn bạn đã dành thời gian đọc và làm bài lab này.

