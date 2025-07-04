---
title: "Cấu hình Upload Function"
date: 2024-06-17
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

### Cấu hình Upload Function để thực hiện việc upload hình ảnh và kết quả phân tích ảnh

**1. Tìm đến trang danh sách chứa các Lambda function**
- Ở phần trước khi đã cấu hình cho Analyze Function thì bạn có thể trở lại danh sách chứa các Lambda Function hiện có nhanh bằng cách như sau:
- Bạn hãy nhìn lên góc trái phía trên thì sẽ có mục **Functions**
- **Kết quả như hình sau:**

![Lambda 10](/images/3.LambdaFunction/lambda_10.png)

- Tại trang hiện thị tất cả các **Function** hiện có, ta có thể thấy được **Analyze Function** mà bạn đã cấu hình ở phần trước
- Tiếp theo, bạn hãy bấm vào button **Create function** nằm ở góc bên phải để tiến hành tạo thêm một function mới như hình ảnh ở dưới:

![Lambda 11](/images/3.LambdaFunction/lambda_11.png)

**3. Cấu hình cho Upload Function tại trang Create function**
- Tại trang tạo mới, để cấu hình cho function mà bạn sắp chuẩn bị phải tạo
- Thì bạn cần phải nhập thông tin và chọn các cấu hình phù hợp nhất cho bài lab, bạn hãy thực hiện theo các bước sau đây:

Trong phần đầu tiên, sẽ có 3 mục để tạo trước template của **Lambda Function:** **Author from scratch, Use a blueprint, Container image**
- Bạn hãy chọn **Author from scratch**, điều này sẽ tạo một cấu trúc đoạn code đơn giản có nội dung mẫu là in ra dòng chữ **Hello World**

Trong phần **Basic information:**
- Function name: nhập tên cho function. Ví dụ: **UploadImage** (hoặc đặt tên tùy ý)
- Runtime: bạn hãy chọn **Python 3.11**
- Architecture: bạn hãy chọn chuẩn **x86_64**

![Lambda 12](/images/3.LambdaFunction/lambda_12.png)

Trong phần **Change default execution role:**
- Excution role: bạn hãy chọn **Use an existing role**, điều này cho phép bạn chọn một **Role** đã tạo trước đó và phù hợp với **Lambda Function**
- Existing role: bạn hãy chọn **LambdaAnalyzeRole**, đây là **Role** mà phần trước đã tạo
- Sau khi đã cấu hình xong, bạn bấm vào button **Create function** để tiến hành tạo  Lambda function
- **Kết quả như hình ảnh bên dưới:**

![Lambda 5](/images/3.LambdaFunction/lambda_5.png)

- Đợi vài giây để hệ thống tạo **Lambda function** mà bạn đã cấu hình
- Sau khi tạo xong thì hệ thống sẽ trả về thông báo tạo thành công **Lambda function** của bạn như hình ảnh bên dưới:

![Lambda 13](/images/3.LambdaFunction/lambda_13.png)

- Tại đây chính là phần mà bạn có thể thao tác các dòng lệnh code để lập trình bằng **ngôn ngữ Python** như đã cấu hình ở phần trước đó:

![Lambda 14](/images/3.LambdaFunction/lambda_14.png)

**3. Cấu hình Code Upload Function tại phần Code Source**
- Tại đây bạn sẽ tiến hành nhập code để chức năng upload hình ảnh và kết quả phân tích có thể hoạt động
- Bạn hãy nhập code theo cấu trúc như sau:

```python
import json
import boto3
import base64
import uuid
import os

# Khởi tạo client S3
s3 = boto3.client('s3')

# Lấy tên bucket từ biến môi trường (thay thế bằng tên bucket của bạn)
BUCKET = os.environ.get("BUCKET_NAME", "your-bucket-name")

def lambda_handler(event, context):
    try:
        # Parse nội dung body từ HTTP request (định dạng JSON)
        body = json.loads(event["body"])
        
        # Lấy dữ liệu ảnh (base64) và kết quả phân tích từ frontend gửi lên
        image_base64 = body.get("image")
        result_data = body.get("result")

        # Kiểm tra nếu thiếu ảnh hoặc kết quả thì trả lỗi
        if not image_base64 or not result_data:
            return {
                "statusCode": 400,
                "body": json.dumps({"error": "Missing image or result"})
            }

        # Giải mã ảnh base64 thành dạng bytes
        image_bytes = base64.b64decode(image_base64)

        # Tạo tên file ảnh ngẫu nhiên bằng UUID
        filename = f"image-{uuid.uuid4()}.jpg"

        # Upload ảnh gốc lên thư mục 'images/' trong bucket S3
        s3.put_object(
            Bucket=BUCKET,
            Key=f"images/{filename}",
            Body=image_bytes,
            ContentType="image/jpeg"
        )

        # Tạo tên file JSON tương ứng và upload kết quả phân tích vào thư mục 'results/'
        s3.put_object(
            Bucket=BUCKET,
            Key=f"results/{filename.replace('.jpg', '.json')}",
            Body=json.dumps(result_data),
            ContentType="application/json"
        )

        # Trả kết quả thành công về cho frontend, bao gồm link ảnh và file JSON
        return {
            "statusCode": 200,
            "body": json.dumps({
                "message": "Upload thành công",
                "imageUrl": f"https://{BUCKET}.s3.amazonaws.com/images/{filename}",
                "resultUrl": f"https://{BUCKET}.s3.amazonaws.com/results/{filename.replace('.jpg', '.json')}"
            }),
            "headers": {
                "Access-Control-Allow-Origin": "*",  # Cho phép truy cập từ mọi domain
                "Content-Type": "application/json"
            }
        }

    except Exception as e:
        # Trả lỗi 500 nếu có exception xảy ra và cho phép CORS
        return {
            "statusCode": 500,
            "body": json.dumps({"error": str(e)}),
            "headers": {"Access-Control-Allow-Origin": "*"}
        }
```

- Sau khi nhập vào trong phần Code Source theo cấu trúc trên bạn có thể tiến hành lưu lại cách thay đổi bằng cách:
- Bấm button **Deploy** hoặc tổ hợp phím **(Ctrl + Shift + U)**
- Đợi một vài giây, hệ thống sẽ lưu lại tất cả các thay đổi của bạn và trả về thông báo lưu thành công

{{% notice note %}}
Lưu ý, bạn hãy thay thế tên bucket của mình, không được để trùng lặp tên bucket
{{% /notice %}}

- **Kết quả như các hình bên dưới:**

![Lambda 16](/images/3.LambdaFunction/lambda_16.png)

![Lambda 17](/images/3.LambdaFunction/lambda_17.png)

Bạn đã hoàn thành bước cấu hình Lambda Function cho chức năng upload hình ảnh và kết quả phân tích lên S3 Bucket
