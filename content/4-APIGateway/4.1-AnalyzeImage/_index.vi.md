---
title: "Cấu hình API Analyze Image"
date: 2024-06-17
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

### Cấu hình API GateWay cho chức năng Analyze Image để phân tích ảnh

**1. Tìm kiếm và truy cập trang dịch vụ của API Gateway**
- Tại thanh tìm kiếm, bạn hãy nhập **API Gateway**
- Kết quả hiển thị như hình ảnh bên dưới:

![API 1](/images/4.APIGateway/api_1.png)

- Tại trang chủ của dịch vụ **API Gateway** của AWS thì bạn có thể tạo mới một API bằng cách bấm vào button **Create an API** ở bên phải như hình ảnh bên dưới:

![API 2](/images/4.APIGateway/api_2.png)

**2. Cấu hình API Gateway cho chức năng Analyze Image**
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
- API name: bạn hãy đặt tên cho API. Ví dụ: **AnalyzeImage**
- IP address type: chọn **IPv4**

Trong phần **Integration:**
- Tại đây chính là phần bạn sẽ kết nối một trong các dịch vụ vào API
- Chọn **Add Integration**
- Chọn dịch vụ **Lambda**
- AWS Region: bạn hãy chọn Region hiện tại. Ví dụ trong bài lab: **ap-southeast-1**
- Lambda function: chọn function đã tạo ở phần trước, ở đây ta chọn **AnalyzeImage**
- Version: chọn **2.0**
- Sau khi cấu hình xong các bước trên, bạn bấm button **Next**

![API 5](/images/4.APIGateway/api_5.png)

- Tiếp theo, ta sẽ được chuyển tới **bước 2: Configure routes**
- Tại trang này, ta sẽ cấu hình để API thực hiện chức năng phân tích ảnh bằng đường dẫn và một trong các phương thức của API như hình ảnh bên dưới:

![API 6](/images/4.APIGateway/api_6.png)

Trong phần **Configure routes:**
- Method: chọn **POST**
- Resource path: bạn có thể tùy ý ghi đường dẫn API. Ví dụ: **/AnalyzeImage**
- Integration target: chọn **AnalyzeImage**
- Sau khi cấu hình các bước trên xong thì bấm button **Next**

![API 7](/images/4.APIGateway/api_7.png)

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

![API 9](/images/4.APIGateway/api_9.png)

- Đợi một lúc, thì hệ thống sẽ tạo thành công API của bạn và trả về thông báo tạo thành công như hình dưới đây:

![API 10](/images/4.APIGateway/api_10.png)

**3. Cấu hình CORS cho API để có thể giao tiếp với Front-End và đọc dữ liệu JSON**
- Ở phía bên phải của Navigation Panel, trong phần **Develop** bạn hãy chọn **CORS** như hình ảnh bên dưới:

![API 11](/images/4.APIGateway/api_11.png)

- Tại trang **CORS**, bạn có thể xem được các phần có thể cấu hình của **CORS** gồm các phần như: **Access-Control-Allow-Origin, Access-Control-Allow-Headers, Access-Control-Allow-Methods, Access-Control-Expose-Headers, Access-Control-Max-Age, Access-Control-Allow-Credentials**. 


![API 12](/images/4.APIGateway/api_12.png)


Trong phần **Configure CORS:**
- Bấm vào button ở góc phải: button **Configure**
- Access-Control-Allow-Origin: bạn hãy nhập dấu **(*)** để cho phép mọi domain có thể truy cập, nếu không muốn bạn có thể tùy chỉnh **chính xác domain mà bạn muốn API giao tiếp**
- Access-Control-Allow-Headers: bạn hãy nhập **content-type** để có thể đọc được đầu vào dưới dạng **JSON**
- Access-Control-Allow-Methods: bạn hãy chọn **POST** để phù hợp với **routes** đã cấu hình ở phần trước
- Còn lại ta sẽ để cấu hình mặc định của **CORS**
- Sau khi đã cấu hình toàn bộ các bước trên thì bấm button **Save**

{{% notice warning %}}
Lưu ý, đây là phần cấu hình bắt buộc phải có, nếu thiếu bước này, API sẽ không thể giao tiếp với Front-End
{{% /notice %}}

![API 13](/images/4.APIGateway/api_13.png)

Bạn đã hoàn thành phần cấu hình API cho chức năng phân tích ảnh bằng AWS Rekognition



