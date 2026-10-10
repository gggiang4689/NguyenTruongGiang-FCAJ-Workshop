---
title: "Website Deployment"
weight: 9
chapter: false
pre: "<b>5.9. </b>"
---

## Deployment Process

The process of deploying **CloudManga** to **GitHub Pages** is carried out as follows:

1. Complete the frontend source code, including **HTML**, **CSS**, and **JavaScript**.
2. Upload the source code to the **CloudManga** repository on **GitHub**.
3. Enable **GitHub Pages**, selecting the `main` branch and the `/ (root)` folder.
4. Update the **Amazon Cognito Callback URL** and configure **CORS** in **Amazon API Gateway** for the GitHub Pages domain.
5. Verify website accessibility and connections to **AWS** services.

Website after deployment:

[https://gggiang4689.github.io/CloudManga/](https://gggiang4689.github.io/CloudManga/)

## Limitations

The release process is performed manually through **GitHub**. The project has not yet implemented a **CI/CD** system or an automated testing process before release.

## Results

The **CloudManga** website has been published on **GitHub Pages** and can be accessed via HTTPS.

The frontend is deployed independently, while the backend continues to use **AWS Lambda**, **Amazon API Gateway**, **Amazon S3**, and **Amazon DynamoDB**.
