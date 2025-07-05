---
title: "Update Policy for S3 Bucket (Optional)"
date: 2024-06-17
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

### Update the Policy configuration for the S3 Bucket to view image information and analysis results

{{% notice note %}}
Note, this is the configuration section for the S3 Bucket Policy. To be able to directly view images and image analysis results via a public URL, you can refer to this section.
{{% /notice %}}

**1. Access the S3 Bucket Policy details page**
- In section 5, we were able to perform the image analysis function and upload images to the **S3 Bucket**
- However, viewing images and results will be denied because the **S3 bucket policy** has not been set up yet
- First, click on the image as shown below:

![RS 26](/images/5.Results/rs_26.png)

- Then, the system will redirect the user to the detailed information page of that **Object**
- On the detailed information page of the **Object (image)**, look to the right corner and you will see an **Object URL** section
- This is the **URL of the Object**, you can **click** or **copy** it to a new browser tab to view:
- **The result will be displayed as shown in the images below:**

![Bucket 1](/images/7.S3Policy/bucket_1.png)

![Bucket 2](/images/7.S3Policy/bucket_2.png)

- After accessing the Object URL link, you may see the system report **Access Denied** and the image cannot be displayed

**2. Configure the S3 Bucket Policy to view images and analysis results**
- Go back to the **Bucket** list page, click on the **Bucket** name

![Bucket 3](/images/7.S3Policy/bucket_3.png)

- Here, switch to the **Permission** tab as shown below:

![Bucket 4](/images/7.S3Policy/bucket_4.png)

- On the information page of the **Permission** tab
- Scroll down a bit
- You will see the **Bucket policy** section, look to the right and click the **Edit** button
- This allows you to edit the **policy** of the **Bucket**

![Bucket 5](/images/7.S3Policy/bucket_5.png)

- After switching to the **Edit Bucket Policy** section, you will see the part where we will edit by adding a **JSON Script** as shown below:

![Bucket 6](/images/7.S3Policy/bucket_6.png)

- Here, you will configure the **Bucket policy** with the following JSON code:
```json
{
  "Version": "2012-10-17",  // Policy version, according to AWS IAM standard
  "Statement": [
    {
      "Sid": "AllowPublicReadAccessToImagesAndResultFolders",  // Identifier for the policy statement (can be changed for easier identification)
      "Effect": "Allow",  // Specifies the "Allow" action for the actions described below
      "Principal": "*",  // Specifies that all users (Public Access) can perform this action
      "Action": "s3:GetObject",  // Grants permission to perform the "s3:GetObject" action, i.e., allows users to read (GET) objects from S3
      "Resource": [  // Grants permission for the specific resources below
        "arn:aws:s3:::your-bucket-name/images/*",  // Allows access to objects in the "images" folder of the bucket
        "arn:aws:s3:::your-bucket-name/results/*"  // Allows access to objects in the "results" folder of the bucket
      ]
    }
  ]
}
```
{{% notice info %}}
Note, please replace with your own S3 Bucket name
{{% /notice %}}

- After configuring as above, you will get the result as shown below
- Save the changes by clicking the **Save changes** button

![Bucket 7](/images/7.S3Policy/bucket_7.png)

![Bucket 8](/images/7.S3Policy/bucket_8.png)

- Wait a few seconds, the system will process and return a **success notification** along with the updated **Bucket policy** displayed on the website as follows:

![Bucket 9](/images/7.S3Policy/bucket_9.png)

- Go back to the detailed information page of the **Object**
- Access the **Object URL** link
- **The result will be displayed as shown in the images below:**

![Bucket 1](/images/7.S3Policy/bucket_1.png)

- Here, you can now view the image directly via the **public object URL** as shown below:

![Bucket 10](/images/7.S3Policy/bucket_10.png)

- Similarly, in the **Edit Policy** section of the Bucket, we have also configured the **/result** folder so that you can view the image analysis results as shown below:

![Bucket 11](/images/7.S3Policy/bucket_11.png)

![Bucket 12](/images/7.S3Policy/bucket_12.png)

![Bucket 13](/images/7.S3Policy/bucket_13.png)

Through this section, you can refer to how to quickly and directly view images








