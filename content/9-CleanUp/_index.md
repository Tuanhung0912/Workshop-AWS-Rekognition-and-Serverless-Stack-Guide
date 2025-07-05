---
title: "Clean Up Resources"
date: 2024-06-17
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

### Clean up service resources after use

**1. Clean up IAM service**
- In the search bar, enter **IAM**
- On the **IAM** service page, on the left Navigation Panel, select **Role**
- On the Roles page, search for **LambdaAnalyzeRole**, check **LambdaAnalyzeRole**
- Click the **Delete** button, enter the Role name: **LambdaAnalyzeRole**

![Clean 1](/images/9.CleanUp/clean_1.png)

![Clean 2](/images/9.CleanUp/clean_2.png)

![Clean 3](/images/9.CleanUp/clean_3.png)

![Clean 4](/images/9.CleanUp/clean_4.png)

**2. Clean up S3 service**
- In the search bar, enter **S3**
- On the **General purpose buckets** page, select the **bucket** you want to delete
- Click the **Empty** button to delete all **Objects in the bucket** before deleting the **Bucket**
- Enter **permanently delete** and click **Empty** to delete the **Objects**
- Go back, select the **bucket** you want to delete, click **Delete**
- Enter your **bucket name**, click **Delete Bucket**

![Clean 5](/images/9.CleanUp/clean_5.png)

![Clean 6](/images/9.CleanUp/clean_6.png)

![Clean 7](/images/9.CleanUp/clean_7.png)

![Clean 8](/images/9.CleanUp/clean_8.png)

![Clean 9](/images/9.CleanUp/clean_9.png)

**3. Clean up Lambda service**
- In the search bar, enter **Lambda**
- Select the **functions** you want to delete, click the **Action** button, choose **Delete**
- Enter **confirm** and click **Delete**

![Clean 10](/images/9.CleanUp/clean_10.png)

![Clean 11](/images/9.CleanUp/clean_11.png)

![Clean 12](/images/9.CleanUp/clean_12.png)

**4. Clean up CloudWatch service**
- In the search bar, enter **CloudWatch**
- On the main **CloudWatch** page, on the left **Navigation Panel** select **Log groups**
- Select the **Log group** you want to delete, click **Action**, choose **Delete log group(s)**
- In the popup window, select **Delete**

![Clean 13](/images/9.CleanUp/clean_13.png)

![Clean 14](/images/9.CleanUp/clean_14.png)

![Clean 15](/images/9.CleanUp/clean_15.png)

![Clean 16](/images/9.CleanUp/clean_16.png)

**5. Clean up API Gateway service**
- In the search bar, enter **API Gateway**
- Select the **API** you want to delete, click **Delete** on the right
- Enter **confirm**, click **Delete**
- Repeat for the remaining APIs

![Clean 17](/images/9.CleanUp/clean_17.png)

![Clean 18](/images/9.CleanUp/clean_18.png)

![Clean 19](/images/9.CleanUp/clean_19.png)

##### Congratulations, you have completed the entire lab. This section will help you save costs by cleaning up unused AWS services. Thank you for taking the time to read and

