---
title: "Configure Analyze Function"
date: 2024-06-17
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

### Configure the Analyze Function to perform image analysis

**1. Search for and access the Lambda service page**
- In the search bar, enter: **Lambda**
- The result will be displayed as shown below:

![Lambda 1](/images/3.LambdaFunction/lambda_1.png)

- On the main page of the **Lambda** service, create a new Function by clicking the **Create a function** button as shown below:

![Lambda 2](/images/3.LambdaFunction/lambda_2.png)

- Next, you will be taken to the configuration page for the **Lambda Function** as shown below:

![Lambda 3](/images/3.LambdaFunction/lambda_3.png)

**2. Configure the Analyze Function on the Create a function page**
- On the creation page, to configure the function you are about to create,
- You need to enter information and select the most suitable configurations for the lab. Please follow these steps:

In the first section, there are 3 options to create a template for the **Lambda Function:** **Author from scratch, Use a blueprint, Container image**
- Select **Author from scratch**, this will create a simple code structure with a sample content that prints **Hello World**

In the **Basic information** section:
- Function name: enter a name for the function. For example: **AnalyzeImage** (or any name you prefer)
- Runtime: select **Python 3.11**
- Architecture: select **x86_64**

![Lambda 4](/images/3.LambdaFunction/lambda_4.png)

In the **Change default execution role** section:
- Execution role: select **Use an existing role**, this allows you to choose a **Role** that was created earlier and is suitable for the **Lambda Function**
- Existing role: select **LambdaAnalyzeRole**, this is the **Role** created in the previous section
- After configuring, click the **Create function** button to create the Lambda function
- **Result as shown below:**

![Lambda 5](/images/3.LambdaFunction/lambda_5.png)

- Wait a few seconds for the system to create the **Lambda function** you have configured
- After creation, the system will return a successful creation notification for your **Lambda function** as shown below:

![Lambda 6](/images/3.LambdaFunction/lambda_6.png)

- Here is where you can write code in **Python** as configured earlier:

![Lambda 7](/images/3.LambdaFunction/lambda_7.png)

**3. Configure the Analyze Function code in the Code Source section**
- Here you will enter the code so that the image analysis function can work
- Enter the code with the following structure:

```python
import json
import boto3
import base64

# Initialize Rekognition client to call the image recognition service
rekognition = boto3.client('rekognition')

def lambda_handler(event, context):
    try:
        # Check if the request body exists
        if 'body' not in event or not event['body']:
            return {
                "statusCode": 400,
                "body": json.dumps({"error": "Empty request body"})
            }

        # Get the body from the incoming event (check if it's base64)
        body_str = event['body']
        if event.get("isBase64Encoded"):  # If API Gateway is configured to send base64
            body_str = base64.b64decode(event['body']).decode('utf-8')

        # Convert JSON string to Python dictionary
        body = json.loads(body_str)

        # Get the base64 image data from the "image" field
        image_base64 = body.get('image')

        # If there is no image, return an error
        if not image_base64:
            return {
                "statusCode": 400,
                "body": json.dumps({"error": "Missing 'image' in request body"})
            }

        # Decode the image from base64 to bytes
        image_bytes = base64.b64decode(image_base64)

        # Call AWS Rekognition to detect labels in the image
        response = rekognition.detect_labels(
            Image={'Bytes': image_bytes},   # Pass the image as bytes
            MaxLabels=10,                   # Limit to 10 labels returned
            MinConfidence=75                # Only get labels with at least 75% confidence
        )

        # Return the recognition result as JSON
        return {
            "statusCode": 200,
            "body": json.dumps({
                "labels": response.get('Labels', []),
                "message": "Image analyzed successfully"
            }),
            "headers": {
                "Content-Type": "application/json",
                "Access-Control-Allow-Origin": "*"  # Allow calls from frontend
            }
        }

    except Exception as e:
        # If there is an error, log it and return a 500 error code
        print("Error:", str(e))
        return {
            "statusCode": 500,
            "body": json.dumps({"error": str(e)})
        }
```

- After entering the code in the Code Source section as above, you can save your changes by:
- Clicking the **Deploy** button or using the shortcut **(Ctrl + Shift + U)**
- Wait a few seconds, the system will save all your changes and return a successful save notification
- **Result as shown in the images below:**

![Lambda 8](/images/3.LambdaFunction/lambda_8.png)

![Lambda 9](/images/3.LambdaFunction/lambda_9.png)

You have completed the step of configuring the Lambda Function for the Analyze Image feature by calling the AWS Rekognition















