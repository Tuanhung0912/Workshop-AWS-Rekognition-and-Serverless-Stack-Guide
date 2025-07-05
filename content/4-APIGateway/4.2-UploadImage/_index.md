---
title: "Configure API Upload Image"
date: 2024-06-17
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

### Configure API Gateway for the function to upload images and analysis results to S3 Bucket

**1. Return to the APIs page to view the list of existing APIs**
- After configuring CORS for the API in the previous section, you can return to the APIs list page by:
- On the left Navigation Panel, select **APIs**

![API 14](/images/4.APIGateway/api_14.png)

- On the APIs list page, you can see the **AnalyzeImage** API created in the previous step as shown below:
- In the top right corner, click **Create API**

![API 15](/images/4.APIGateway/api_15.png)

**2. Configure API Gateway for the Upload Image function**
- On the page to add a new API, you can see many types of APIs for different purposes such as: **HTTP API, WebSocket API, REST API**, etc.
- In this section, we will use **HTTP API**

In the **Choose an API type:** section:
- Select **HTTP API**
- Click the **Build** button
- The result is as shown below:

![API 3](/images/4.APIGateway/api_3.png)

- Next, after performing the previous step, you will be taken to the API configuration page consisting of 4 steps: **Configure API, Configure routes, Define Stages, Review and Create**.
- Here, you will configure the API according to these 4 steps to **Build** an **API Gateway**

![API 4](/images/4.APIGateway/api_4.png)

In the **Configure API:** section:
- API name: enter a name for the API. For example: **UploadImage**
- IP address type: select **IPv4**

In the **Integration:** section:
- Here is where you will connect one of the services to the API
- Select **Add Integration**
- Choose the **Lambda** service
- AWS Region: select your current Region. For example, in this lab: **ap-southeast-1**
- Lambda function: select the function created in the previous section, here we choose **UploadImage**
- Version: select **2.0**
- After configuring the above steps, click the **Next** button

![API 16](/images/4.APIGateway/api_16.png)

- Next, you will be taken to **Step 2: Configure routes**
- On this page, you will configure the API to perform the upload image function using the path and one of the API methods as shown below:

![API 17](/images/4.APIGateway/api_17.png)

In the **Configure routes:** section:
- Method: select **POST**
- Resource path: you can freely set the API path. For example: **/UploadImage**
- Integration target: select **UploadImage**
- After configuring the above steps, click the **Next** button

![API 18](/images/4.APIGateway/api_18.png)

In **Step 3: Define stages**
- Leave the default values for **Stages**
- You can choose to **Deploy** the API manually or automatically whenever there are changes
- In this example, I will leave it as the default **Auto-deploy**
- After configuring the above steps, click the **Next** button

![API 8](/images/4.APIGateway/api_8.png)

In **Step 4: Review and create**
- On this page, you will review all the configurations from the previous 3 steps
- If there are any mistakes, you can click the **Edit** button in each section
- After checking all the API configurations, click **Create** to create the API

![API 19](/images/4.APIGateway/api_19.png)

- Wait a moment, the system will successfully create your API and return a success notification as shown below:

![API 20](/images/4.APIGateway/api_20.png)

**3. Configure CORS for the API to communicate with the Front-End and read JSON data**
- On the right side of the Navigation Panel, in the **Develop** section, select **CORS** as shown below:

![API 21](/images/4.APIGateway/api_21.png)

- On the **CORS** page, you can see the configurable parts of **CORS** including: **Access-Control-Allow-Origin, Access-Control-Allow-Headers, Access-Control-Allow-Methods, Access-Control-Expose-Headers, Access-Control-Max-Age, Access-Control-Allow-Credentials**.
- Click the button in the top right corner: **Configure**

![API 22](/images/4.APIGateway/api_22.png)

In the **Configure CORS:** section:
- Access-Control-Allow-Origin: enter **(*)** to allow all domains to access, or you can specify the exact domain you want the API to communicate with
- Access-Control-Allow-Headers: enter **content-type** to allow reading input in **JSON** format
- Access-Control-Allow-Methods: select **POST** to match the **routes** configured earlier
- Leave the remaining CORS settings as default
- After configuring all the above steps, click the **Save** button

{{% notice warning %}}
Note, this is a required configuration step. If you skip this step, the API will not be able to communicate with the Front-End.
{{% /notice %}}

![API 23](/images/4.APIGateway/api_23.png)

You have completed the API configuration for uploading images and analysis results to S3 Bucket





