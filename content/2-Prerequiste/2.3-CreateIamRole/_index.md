---
title: "Create IAM Role and Attach Policy"
date: 2024-06-17
weight: 3
chapter: false
pre: " <b> 2.3 </b> "
---

### Create a new IAM Role and Attach Policy to the Role

**1. Search for and access the IAM service to create a Role**
- In the search bar, enter **IAM**
- After searching, click on the **IAM** service as shown below:

![Role 1](/images/2.Prerequiste/role_1.png)

- On the IAM service page, in the left Navigation Panel
- Select **Roles** as shown below:

![Role 2](/images/2.Prerequiste/role_2.png)

- On the Roles page, you can see a list of many popular and frequently used AWS Roles
- On the right side, click the **Create Role** button as follows:

![Role 3](/images/2.Prerequiste/role_3.png)

**2. Create a new Role and configure details**
- On the **Create Role** page, you can see that creating a **Role** involves 3 main steps as shown below:

![Role 4](/images/2.Prerequiste/role_4.png)

In the **Select Trusted entity** section:
- Trusted entity type: Select **AWS Service**

In the **Use Case** section:
- Service or use case: select **Lambda**
- Then click the **Next** button

![Role 5](/images/2.Prerequiste/role_5.png)

- On the **Step 2 Add permissions to Role** page, you can see more than 1000+ Permission Policies as shown below:

![Role 6](/images/2.Prerequiste/role_6.png)

- However, you only need to find a few Policies suitable for the Lab
- Here, we will search for and select 3 Policies to use: **AmazonS3FullAccess, AmazonRekognitionFullAccess, CloudWatchLogsFullAccess.**
- After selecting, click the **Next** button
- **Results as shown in the images below:**

![Role 7](/images/2.Prerequiste/role_7.png)
![Role 8](/images/2.Prerequiste/role_8.png)
![Role 9](/images/2.Prerequiste/role_9.png)

- On the **Step 3: Name, review, and create** page, you will review all configurations from the previous two steps

In the **Role details** section:
- Role name: set a name for the Role, e.g., **LambdaAnalyzeRole**
- Description: you can leave it as default or add notes as you wish

![Role 10](/images/2.Prerequiste/role_10.png)

- In the **Step 2: Add Permission** section, you can review the Policies you added in detail
- After checking all the information, click **Create Role** to proceed

![Role 11](/images/2.Prerequiste/role_11.png)

- Wait a few seconds, after creation the system will redirect you to the main Roles page and display a success notification as shown below:

![Role 12](/images/2.Prerequiste/role_12.png)

You have completed the necessary preparation steps to proceed to the next step.