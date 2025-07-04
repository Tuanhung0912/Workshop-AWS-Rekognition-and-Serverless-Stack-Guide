---
title: "Cấu hình API Upload Image"
date: 2024-06-17
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

### Cấu hình API Gateway cho chức năng upload hình ảnh và kết quả phân tích lên S3 Bucket

**1. Quay trở về trang APIs để xem danh sách các API hiện có**
- Sau khi đã cấu hình CORS cho API ở phần trước, bạn có thể quay trở lại trang danh sách APIs bằng cách:
- Ở phía bên trái Navigation Panel, chọn **APIs**

![API 14](/images/4.APIGateway/api_14.png)

- Tại trang danh sách các API thì bạn có thể thấy được API **AnalyzeImage** đã tạo ở bước trước như hình ảnh ở bên dưới:
- Ở phía góc phải, bấm vào **Create API**

![API 15](/images/4.APIGateway/api_15.png)

**2. Cấu hình API Gateway cho chức năng Upload Image**
- Tại trang thêm mới một API thì, bạn có thể thấy được rất nhiều lại API sử dụng cho từng mục đích khác nhau như: **HTTP API, WebSocket API, REST API**,...
- Ở phần này, ta sẽ sử dụng **HTTP API**

Trong phần **Choose an API type:**
- Bạn hãy chọn **HTTP API**
- Bấm vào Button **Build**
- Kết quả như hình ảnh sau:

![API 3](/images/4.APIGateway/api_3.png)

- Tiếp theo, sau khi thực hiện thao tác trước, bạn sẽ được chuyển đến trang cấu hình API gồm 4 bước như sau: **Configure API, Configure routes, Define Stages, Review and Create**.
- Tại đây, bạn sẽ tiến hành cấu hình API theo 4 bước trên để có thể **Build** được một **API Gateway**

![API 4](/images/4.APIGateway/api_4.png)

Trong **phần Configure API:**
- API name: bạn hãy đặt tên cho API. Ví dụ: **UploadImage**
- IP address type: chọn **IPv4**

Trong phần **Integration:**
- Tại đây chính là phần bạn sẽ kết nối một trong các dịch vụ vào API
- Chọn **Add Integration**
- Chọn dịch vụ **Lambda**
- AWS Region: bạn hãy chọn Region hiện tại. Ví dụ trong bài lab: **ap-southeast-1**
- Lambda function: chọn function đã tạo ở phần trước, ở đây ta chọn **UploadImage**
- Version: chọn **2.0**
- Sau khi cấu hình xong các bước trên, bạn bấm button **Next**

![API 16](/images/4.APIGateway/api_16.png)

- Tiếp theo, ta sẽ được chuyển tới **bước 2: Configure routes**
- Tại trang này, ta sẽ cấu hình để API thực hiện chức năng phân tích ảnh bằng đường dẫn và một trong các phương thức của API như hình ảnh bên dưới:

![API 17](/images/4.APIGateway/api_17.png)

Trong phần **Configure routes:**
- Method: chọn **POST**
- Resource path: bạn có thể tùy ý ghi đường dẫn API. Ví dụ: **/UploadImage**
- Integration target: chọn **UploadImage**
- Sau khi cấu hình các bước trên xong thì bấm button **Next**

![API 18](/images/4.APIGateway/api_18.png)

Trong phần **Bước 3: Define stages**
- Ta sẽ để nguyên các giá trị mặc định của **Stages**
- Bạn có thể tùy ý muốn **Deploy** API bằng tay hoặc tự động mỗi khi có sự thay đổi
- Ở ví dụ này, mình sẽ để mặc định là **Auto-deploy**
- Sau khi cấu hình các bước trên xong thì bấm button **Next**

![API 8](/images/4.APIGateway/api_8.png)

Trong phần **Bước 4: Review and create**
- Tại trang này, bạn sẽ kiểm tra lại toàn bộ các cấu hình ở 3 bước trước đó
- Nếu có gì sai xót thì bạn có thể bấm nút **Edit** ở mỗi phần
- Sau khi đã kiểm tra toàn bộ cấu hình của API thì bạn hãy bấm **Create** để tiến hành tạo API

![API 19](/images/4.APIGateway/api_19.png)

- Đợi một lúc, thì hệ thống sẽ tạo thành công API của bạn và trả về thông báo tạo thành công như hình dưới đây:

![API 20](/images/4.APIGateway/api_20.png)


**3. Cấu hình CORS cho API để có thể giao tiếp với Front-End và đọc dữ liệu JSON**
- Ở phía bên phải của Navigation Panel, trong phần **Develop** bạn hãy chọn **CORS** như hình ảnh bên dưới:

![API 21](/images/4.APIGateway/api_21.png)

- Tại trang **CORS**, bạn có thể xem được các phần có thể cấu hình của **CORS** gồm các phần như: **Access-Control-Allow-Origin, Access-Control-Allow-Headers, Access-Control-Allow-Methods, Access-Control-Expose-Headers, Access-Control-Max-Age, Access-Control-Allow-Credentials**.
- Bấm vào button ở góc phải: button **Configure**

![API 22](/images/4.APIGateway/api_22.png)

Trong phần **Configure CORS:**
- Access-Control-Allow-Origin: bạn hãy nhập dấu **(*)** để cho phép mọi domain có thể truy cập, nếu không muốn bạn có thể tùy chỉnh **chính xác domain mà bạn muốn API giao tiếp**
- Access-Control-Allow-Headers: bạn hãy nhập **content-type** để có thể đọc được đầu vào dưới dạng **JSON**
- Access-Control-Allow-Methods: bạn hãy chọn **POST** để phù hợp với **routes** đã cấu hình ở phần trước
- Còn lại ta sẽ để cấu hình mặc định của **CORS**
- Sau khi đã cấu hình toàn bộ các bước trên thì bấm button **Save**

{{% notice warning %}}
Lưu ý, đây là phần cấu hình bắt buộc phải có, nếu thiếu bước này, API sẽ không thể giao tiếp với Front-End
{{% /notice %}}

![API 23](/images/4.APIGateway/api_23.png)

Bạn đã hoàn thành phần cấu hình API để thực hiện chức năng Upload hình ảnh và kết quả phân tích lên S3 Bucket





