---
title: "Cấu hình Analyze Function"
date: 2024-06-17
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

### Cấu hình Analyze Function để thực hiện việc phân tích hình ảnh

**1. Tìm kiếm và truy cập trang dịch vụ của Lambda**
- Tại thanh tìm kiếm, bạn hãy nhập: **Lambda**
- Kết quả hiển thị như hình ảnh bên dưới:

![Lambda 1](/images/3.LambdaFunction/lambda_1.png)

- Tại trang chính của dịch vụ **lambda**, bạn hãy tiến hành tạo mới một Function bằng cách bấm vào button **Create a function** như hình ảnh bên dưới:

![Lambda 2](/images/3.LambdaFunction/lambda_2.png)

- Tiếp theo, bạn sẽ được chuyển đến trang cấu hình cho **Lambda Function** như hình ảnh bên dưới:

![Lambda 3](/images/3.LambdaFunction/lambda_3.png)

**2. Cấu hình cho Analyze Function tại trang Create a function**
- Tại trang tạo mới, để cấu hình cho function mà bạn sắp chuẩn bị phải tạo
- Thì bạn cần phải nhập thông tin và chọn các cấu hình phù hợp nhất cho bài lab, bạn hãy thực hiện theo các bước sau đây:

Trong phần đầu tiên, sẽ có 3 mục để tạo trước template của **Lambda Function:** **Author from scratch, Use a blueprint, Container image**
- Bạn hãy chọn **Author from scratch**, điều này sẽ tạo một cấu trúc đoạn code đơn giản có nội dung mẫu là in ra dòng chữ **Hello World**

Trong phần **Basic information:**
- Function name: nhập tên cho function. Ví dụ: **AnalyzeImage** (hoặc đặt tên tùy ý)
- Runtime: bạn hãy chọn **Python 3.11**
- Architecture: bạn hãy chọn chuẩn **x86_64**

![Lambda 4](/images/3.LambdaFunction/lambda_4.png)

Trong phần **Change default execution role:**
- Excution role: bạn hãy chọn **Use an existing role**, điều này cho phép bạn chọn một **Role** đã tạo trước đó và phù hợp với **Lambda Function**
- Existing role: bạn hãy chọn **LambdaAnalyzeRole**, đây là **Role** mà phần trước đã tạo
- Sau khi đã cấu hình xong, bạn bấm vào button **Create function** để tiến hành tạo  Lambda function
- **Kết quả như hình ảnh bên dưới:**

![Lambda 5](/images/3.LambdaFunction/lambda_5.png)

- Đợi vài giây để hệ thống tạo **Lambda function** mà bạn đã cấu hình
- Sau khi tạo xong thì hệ thống sẽ trả về thông báo tạo thành công **Lambda function** của bạn như hình ảnh bên dưới:

![Lambda 6](/images/3.LambdaFunction/lambda_6.png)

- Tại đây chính là phần mà bạn có thể thao tác các dòng lệnh code để lập trình bằng **ngôn ngữ Python** như đã cấu hình ở phần trước đó:

![Lambda 7](/images/3.LambdaFunction/lambda_7.png)

**3. Cấu hình Code Analyze Function tại phần Code Source**
- Tại đây bạn sẽ tiến hành nhập code để chức năng phân tích ảnh có thể hoạt động
- Bạn hãy nhập code theo cấu trúc như sau:

```python
import json
import boto3
import base64

# Khởi tạo client Rekognition để gọi dịch vụ nhận diện ảnh
rekognition = boto3.client('rekognition')

def lambda_handler(event, context):
    try:
        # Kiểm tra xem request body có tồn tại không
        if 'body' not in event or not event['body']:
            return {
                "statusCode": 400,
                "body": json.dumps({"error": "Empty request body"})
            }

        # Lấy phần body từ sự kiện gửi vào (kiểm tra có phải là base64 không)
        body_str = event['body']
        if event.get("isBase64Encoded"):  # Nếu API Gateway cấu hình truyền base64
            body_str = base64.b64decode(event['body']).decode('utf-8')

        # Chuyển chuỗi JSON thành dictionary Python
        body = json.loads(body_str)

        # Lấy dữ liệu ảnh dạng base64 từ trường "image"
        image_base64 = body.get('image')

        # Nếu không có ảnh thì trả về lỗi
        if not image_base64:
            return {
                "statusCode": 400,
                "body": json.dumps({"error": "Missing 'image' in request body"})
            }

        # Giải mã ảnh từ base64 thành dạng bytes
        image_bytes = base64.b64decode(image_base64)

        # Gọi AWS Rekognition để nhận diện nhãn trong ảnh
        response = rekognition.detect_labels(
            Image={'Bytes': image_bytes},   # Truyền ảnh dạng bytes
            MaxLabels=10,                   # Giới hạn tối đa 10 nhãn trả về
            MinConfidence=75                # Chỉ lấy nhãn có độ tin cậy từ 75% trở lên
        )

        # Trả kết quả nhận diện về dưới dạng JSON
        return {
            "statusCode": 200,
            "body": json.dumps({
                "labels": response.get('Labels', []),
                "message": "Image analyzed successfully"
            }),
            "headers": {
                "Content-Type": "application/json",
                "Access-Control-Allow-Origin": "*"  # Cho phép gọi từ frontend
            }
        }

    except Exception as e:
        # Nếu có lỗi thì log ra và trả về mã lỗi 500
        print("Error:", str(e))
        return {
            "statusCode": 500,
            "body": json.dumps({"error": str(e)})
        }
```

- Sau khi nhập vào trong phần Code Source theo cấu trúc trên bạn có thể tiến hành lưu lại cách thay đổi bằng cách:
- Bấm button **Deploy** hoặc tổ hợp phím **(Ctrl + Shift + U)**
- Đợi một vài giây, hệ thống sẽ lưu lại tất cả các thay đổi của bạn và trả về thông báo lưu thành công
- **Kết quả như các hình bên dưới:**

![Lambda 8](/images/3.LambdaFunction/lambda_8.png)

![Lambda 9](/images/3.LambdaFunction/lambda_9.png)

Bạn đã hoàn thành bước cấu hình Lambda Function cho chức năng Phân tích ảnh bằng cách gọi Client của AWS Rekognition















