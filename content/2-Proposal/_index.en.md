---
title: "Proposal"
weight: 2
chapter: false
pre: "<b>2. </b>"
---

## First Cloud AI Journey – CloudManga Capstone Project

---

# 1. Executive Summary

**CloudManga** is a project aimed at developing a manga reading web application on the **Amazon Web Services (AWS)** cloud computing platform.

The application allows users to browse manga lists, search for manga, view detailed information, and read sample chapters in PDF format. In addition, the system is designed to support user registration, login, and manga reviews.

CloudManga uses **HTML, CSS, JavaScript** for the frontend, combined with **AWS** services such as **Amazon S3, AWS Lambda, Amazon API Gateway, Amazon Cognito**, and **Amazon DynamoDB**.

The main objective of the project is to explore how to build a web application using **Serverless** architecture, reducing the need for server management and taking advantage of **AWS** managed services.

---

# 2. Problem and Solution

## Problem

- Online manga reading applications need to manage multiple manga titles, chapters, and user information.
- Deploying the entire system on traditional servers may require server configuration, operating system maintenance, database management, and resource monitoring.
- In addition, the application requires a user authentication mechanism to manage interactive features such as manga ratings and reviews.

## Solution

**CloudManga** uses Serverless architecture to simplify the deployment process:

- **Amazon S3** stores manga information, cover images, and sample PDF chapters.
- **AWS Lambda** processes requests from the application.
- **Amazon API Gateway** provides endpoints for the frontend.
- **Amazon Cognito** manages user accounts and authentication.
- **Amazon DynamoDB** stores ratings and reviews.
- **Amazon CloudWatch** supports monitoring Lambda execution.
- **GitHub Pages** is used to deploy the static web frontend.

The project prioritizes a simple architecture, low costs, and suitability for educational purposes.

---

# 3. Solution Architecture

## Overall CloudManga Architecture

![CloudManga Architecture Diagram](/images/CloudManga-architecture.png)

The system is divided into three main components:

1. **Frontend:** The user interface is built using HTML, CSS, and JavaScript.
2. **Backend:** Amazon API Gateway works with AWS Lambda to receive and process requests.
3. **Storage and Authentication:** Amazon S3 stores manga content, DynamoDB stores reviews, and Cognito manages user accounts.

The services are connected through APIs to limit direct frontend access to private data.

## Request Processing Flow

![CloudManga Workflow](/images/CloudManga-workflow.png)

The expected workflow is as follows:

1. The user accesses the CloudManga website.
2. The frontend sends a request to Amazon API Gateway.
3. API Gateway invokes AWS Lambda to retrieve the manga list.
4. Lambda reads JSON data from Amazon S3.
5. The result is returned to the frontend for display.
6. The user logs in through Amazon Cognito.
7. Authenticated users can submit manga reviews.
8. Lambda stores review information in Amazon DynamoDB.

## AWS Services Used

| AWS Service | Role |
|---|---|
| Amazon S3 | Stores manga data, cover images, and PDF files |
| AWS Lambda | Handles application business logic |
| Amazon API Gateway | Provides APIs for the frontend |
| Amazon Cognito | Handles user registration and authentication |
| Amazon DynamoDB | Stores ratings and reviews |
| AWS IAM | Manages access permissions |
| Amazon CloudWatch | Monitors logs and errors |
| AWS Budgets | Controls costs |

---

# 4. Technical Implementation

## Main Features

| Feature | Description |
|---|---|
| Homepage | Displays the manga list |
| Search | Searches for manga by title |
| Manga Details | Displays manga information and chapter lists |
| Manga Reader | Displays sample PDF chapters |
| Registration and Login | Authenticates user accounts through Cognito |
| Manga Ratings | Allows ratings from 1 to 5 stars |
| Reviews | Allows users to submit and view reviews |

## Planned APIs

| Method | Endpoint | Function |
|---|---|---|
| GET | `/manga` | Retrieves the manga list |
| GET | `/manga/{id}` | Retrieves manga details |
| GET | `/manga/{id}/chapters` | Retrieves the chapter list |
| GET | `/reviews/{mangaId}` | Retrieves reviews |
| POST | `/reviews` | Adds a review |
| PUT | `/reviews/{mangaId}` | Updates a review |
| DELETE | `/reviews/{mangaId}` | Deletes a review |

The `GET /manga` endpoint has been implemented and tested during the AWS Lambda and API Gateway practice exercises.

The remaining endpoints are within the design scope and will be tested once the implementation is complete.

## Data Storage

The **Amazon S3 Bucket** `cloudmanga-storage-2026` stores manga data and is configured to block public access.

Reviews are planned to be stored in the **DynamoDB** table `CloudManga-Reviews`, using manga IDs and user IDs to distinguish reviews.

The authentication system is planned to use **Amazon Cognito User Pool** and **JWT** to protect requests for adding, updating, and deleting reviews.

---

# 5. Implementation Roadmap

| Phase | Activities | Result |
|---|---|---|
| 1 | Learn about AWS, IAM, VPC, EC2, and S3 | LABs completed |
| 2 | Create S3, Lambda, and API Gateway | Manga list API operational |
| 3 | Practice Docker, ECS, ALB, and Auto Scaling | LABs completed |
| 4 | Develop the CloudManga frontend | In progress |
| 5 | Integrate Cognito, DynamoDB, and PDF Reader | Planned |
| 6 | Test, publish, and complete documentation | Planned |

---

# 6. Risks and Limitations

- The project is carried out within a short period, so basic features are prioritized.
- The initial manga dataset contains only a small number of titles for testing purposes.
- Integrating multiple AWS services may cause IAM permission or CORS configuration errors.
- Some services may incur costs depending on usage.
- The system has not been tested under heavy loads or evaluated for operation in a real-world production environment.

---

# 7. Future Development

- Add a manga content management dashboard.
- Support advanced search and genre filtering.
- Create a favorite manga list.
- Save manga reading history.
- Improve the interface on mobile devices.
- Add more efficient content storage and delivery mechanisms.
- Explore the use of AI to recommend manga based on user preferences.
