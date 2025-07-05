---
title : "Prerequiste"
date :  2024-06-17 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

### Overview

Before starting to implement the intelligent image recognition AI system, you need to prepare some basic components in the AWS environment to ensure the smooth process of analysis and storage. Specifically, you will create an S3 Bucket to store the original images uploaded by the user, as well as the analysis results in JSON format. Next, you need to configure an IAM Role with appropriate permissions such as AmazonS3FullAccess, AmazonRekognitionFullAccess, CloudWatchLogsFullAccess... so that the Lambda function can call the Rekognition service, log data to CloudWatch, and write data to S3.

### Content

- [Clone và Setup Front-End](2.1-CloneFrontEnd/)
- [Create an S3 Bucket for storage](2.2-CreateS3Bucket/)
- [Create IAM Role and Attach Policy](2.3-CreateIamRole/)