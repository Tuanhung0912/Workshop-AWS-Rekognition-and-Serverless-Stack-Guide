---
title: "Configure API Gateway"
date: 2024-06-17
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

### Overview

In this section, you will configure Amazon API Gateway – the component that acts as a bridge between the user interface (frontend) and the serverless backend (AWS Lambda). API Gateway will receive HTTP requests from the web application (such as when users upload images), then forward these requests to the Lambda function for processing. Properly configuring API Gateway ensures the system can communicate reliably, securely, and scale flexibly. At the same time, you will also configure CORS (Cross-Origin Resource Sharing) to allow the web application to access API resources correctly, especially when the frontend and backend are deployed on different domains. This is an important step to complete the communication process between the React frontend and the backend AWS services.

### Contents

- [Configure API Analyze Image](4.1-AnalyzeImage)
- [Configure API Upload Image](4.2-UploadImage/)

