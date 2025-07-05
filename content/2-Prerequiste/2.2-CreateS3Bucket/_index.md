---
title: "Create an S3 Bucket for Storage"
date: 2024-06-17
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

### Initialize an S3 Bucket for storing images and analysis results

**1. Access the Console and find the Amazon S3 service**
- Go to the [AWS Management Console](https://aws.amazon.com/console/)
- Then, log in to your account as shown below:

![AWS Console](/images/2.Prerequiste/awslogin_1.png)

- After clicking the page, the login screen with required fields will appear as shown below:

![AWS Console](/images/2.Prerequiste/awslogin_2.png)

{{% notice warning %}}
Note, this is a mandatory requirement to proceed to the next steps. If you do not have an account, please register for one.
{{% /notice %}}

- **Reference link for account creation:** [Create an account](https://000001.awsstudygroup.com/)

- After successfully logging in, you will be redirected to the main page of the **AWS Management Console** as shown below:

![AWS Console 2](/images/2.Prerequiste/aws_mainpage.png)

- In the search bar, type **S3**
- Select the **S3** service
- **Result as shown below:**

![S3 Bucket 1](/images/2.Prerequiste/s3bucket_1.png)

{{% notice tip %}}
You can star the services you use frequently during the process, making it more convenient for quick access.
{{% /notice %}}

- On the main interface of the S3 service, click the **Create Bucket** button as shown below:

![S3 Bucket 2](/images/2.Prerequiste/s3bucket_2.png)

**2. Configure the S3 Bucket**
- After clicking **Create Bucket**, you will be taken to the bucket creation section as shown below:

![S3 Bucket 3](/images/2.Prerequiste/s3bucket_3.png)

In the **General configuration** section:
- AWS Region: **Asia Pacific (Singapore) ap-southeast-1** (or any region you want to use)
- Bucket type: select **General purpose**
- Bucket name: enter **rekognition-image-upload-0912**

In the **Object Ownership** section:
- Select **ACLs disable (recommended)**

{{% notice info %}}
Note, your Bucket Name must be unique and not duplicate any other buckets.
{{% /notice %}}

![S3 Bucket 4](/images/2.Prerequiste/s3bucket_4.png)

In the **Block Public Access setting for this bucket** section:
- Uncheck **Block all public access**
- Uncheck **Block public access to buckets and objects granted through new access control lists (ACLs)**
- Uncheck **Block public access to buckets and objects granted through any access control lists (ACLs)**
- Uncheck **Block public access to buckets and objects granted through new public bucket or access point policies**
- Uncheck **Block public and cross-account access to buckets and objects through any public bucket or access point policies**
- Check **I acknowledge that the current settings might result in this bucket and the objects within becoming public.**

![S3 Bucket 5](/images/2.Prerequiste/s3bucket_5.png)

In the **Bucket Versioning** section:
- Bucket Versioning: select **Disable**

In the **Default Encryption** section:
- Encryption type: select **Server-side encryption with Amazon S3 managed keys (SSE-S3)**
- Bucket key: select **Enable**

![S3 Bucket 6](/images/2.Prerequiste/s3bucket_6.png)

- After completing the above steps, scroll to the bottom of the page and click **Create Bucket** as shown below:

![S3 Bucket 7](/images/2.Prerequiste/s3bucket_7.png)

- Wait a few seconds, you will be redirected to the bucket list page and a successful bucket creation notification will appear as shown below:

![S3 Bucket 8](/images/2.Prerequiste/s3bucket_8.png)

You have completed the step of creating an S3 Bucket to store images and