---
title: "Prerequisites"
weight: 2
chapter: false
pre: "<b>5.2. </b>"
---

## Objectives

Prepare an **AWS** account, development environment, and necessary tools to deploy the **CloudManga** application using **Serverless** architecture.

---

## 1. AWS Account

Access the [AWS Management Console](https://console.aws.amazon.com/) and sign in with an AWS account.

Select the **Asia Pacific (Singapore) – ap-southeast-1** Region to deploy the services.

<div style="text-align: center;">
  <img src="/images/week1-01.png"
       alt="AWS Management Console Interface"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.2.1 AWS Management Console Interface</em></p>
</div>

Ensure that the account has permission to use the following services:

- **Amazon S3:** Stores manga data and images.
- **AWS Lambda:** Processes requests from the application.
- **Amazon API Gateway:** Provides APIs connecting the frontend and backend.
- **Amazon Cognito:** Authenticates users.
- **Amazon DynamoDB:** Stores reviews.
- **AWS IAM:** Manages access permissions.
- **Amazon CloudWatch:** Monitors system logs.

---

## 2. Checking AWS Costs

Access **Billing and Cost Management** to check **AWS Credits** and **AWS Budgets**.

<div style="text-align: center;">
  <img src="/images/week1-02.png"
       alt="Checking the Budget"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.2.2 Checking the AWS Budget</em></p>
</div>

Monitoring costs helps minimize unexpected charges during deployment and testing.

## 3. Development Tools

| Tool | Purpose |
|---|---|
| **Visual Studio Code** | Writing and managing source code |
| **HTML, CSS, JavaScript** | Developing the CloudManga frontend |
| **Python** | Developing Lambda functions and running a local HTTP Server |
| **Google Chrome** | Testing the interface and APIs |
| **GitHub** | Storing source code and deploying GitHub Pages |

The tools can be downloaded from:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Python](https://www.python.org/downloads/)
- [GitHub](https://github.com/)

To run the website in the development environment, open a Terminal in the project directory and execute:

```powershell
python -m http.server 5500
```

Access the following address:

`http://localhost:5500/`

## 4. Data Preparation

Data is organized in **Amazon S3** using the following structure:

```text
cloudmanga-storage-2026/
├── covers/
│   └── ...
└── manga/
    ├── manga.json
    ├── 1/
    │   └── chapter-01/
    │       ├── 001.jpg
    │       └── 002.jpg
    └── ...
```

Where:

- **covers/:** Stores cover images.
- **manga.json:** Stores manga information.
- **chapter-01/:** Stores JPG pages of a chapter.

Image data used for the demonstration must have appropriate usage rights.

## 5. Results

Completed the necessary preparations for deploying **CloudManga**, including an AWS account, the Singapore Region, a development environment, testing tools, and the planned data structure.

The steps for creating resources and configuring services will be carried out in the following sections.
