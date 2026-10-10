---
title: "System Testing"
weight: 11
chapter: false
pre: "<b>5.11. </b>"
---

## Testing Process

The **CloudManga** testing process is performed directly in a web browser to verify the functionality of the frontend and **AWS** backend services.

The tested features include:

1. Accessing the website through **GitHub Pages**.
2. Checking the ability to load manga lists and cover images from **Amazon S3**.
3. Testing the search and manga details features.
4. Checking the loading of JPG pages through **AWS Lambda** and **Amazon API Gateway**.
5. Testing login and logout using **Amazon Cognito**.
6. Checking the ability to view and submit reviews through **Amazon DynamoDB**.

## Testing Results

| Feature | Result |
|---|---|
| Website access | Successful |
| Display manga list | Successful |
| Search and view details | Successful |
| Read manga chapters | Successful |
| Login and logout | Successful |
| Display reviews | Successful |
| Submit reviews after login | Successful |

Deployed website:

[https://gggiang4689.github.io/CloudManga/](https://gggiang4689.github.io/CloudManga/)

<div style="text-align: center;">
  <img src="/images/5.11.1.png"
       alt="CloudManga Website Testing"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.11.1. Testing CloudManga features in a web browser.</em></p>
</div>

## Limitations

Testing is performed manually in a web browser. The system has not yet implemented **Automated Testing** or performance testing with a large number of concurrent users.

## Results

The main features of **CloudManga** have been deployed and tested at a basic level. The interface can retrieve data from **AWS**, support manga reading, and authenticate users through **Amazon Cognito**.

Additional testing on the public website helps confirm the stability of the review feature before final acceptance.
