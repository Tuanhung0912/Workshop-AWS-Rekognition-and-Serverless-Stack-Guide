---
title: "Configure Lambda Function"
date: 2024-06-17
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### Overview

In this section, you will configure the AWS Lambda Function – a core component in the intelligent image recognition AI system. Lambda acts as an intermediary processor: it receives images from users via API Gateway, sends the images to Amazon Rekognition for content analysis, processes the results, and stores the analysis information as JSON in S3. Additionally, Lambda logs the entire operation process to CloudWatch for monitoring and troubleshooting purposes. Properly configuring the Lambda function is an important step to ensure the system operates accurately, securely, and can scale flexibly following the Serverless model.

### Contents

- [Configure Analyze Function](3.1-AnalyzeFunction)
- [Configure Upload Function](3.2-UploadFunction/)


