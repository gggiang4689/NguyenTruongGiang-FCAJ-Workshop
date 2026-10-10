---
title: "Lambda for Review Processing"
weight: 2
chapter: false
pre: "<b>5.7.2. </b>"
---

## Objectives

Develop an **AWS Lambda** function to read and write review data in **Amazon DynamoDB**.

## Implementation Steps

### Step 1: Create an IAM Role

Access **AWS IAM → Roles → Create role**.

Create a Role named:

`CloudManga-Reviews-Role`

Attach the **AWSLambdaBasicExecutionRole** policy and grant **dynamodb:Query** and **dynamodb:PutItem** permissions for the `CloudManga-Reviews` table.

### Step 2: Create a Lambda Function

1. Access **AWS Lambda → Create function**.
2. Select **Author from scratch**.
3. Enter the name `CloudManga-Reviews`.
4. Select **Python 3.x** as the Runtime.
5. Select the Execution Role `CloudManga-Reviews-Role`.
6. Select **Create function**.

### Step 3: Develop the Functionality

Lambda uses the **Boto3** library to perform the following operations:

- **GET:** Query the list of reviews by `mangaId`, calculate the average rating and the number of reviews.
- **POST:** Validate the rating, comment, and user identity from the authentication information forwarded by API Gateway.
- **PutItem:** Save or update reviews in **DynamoDB**.

The `mangaId` and `userId` key structure helps maintain one review record per user for each manga title.

### Step 4: Test the Function

Use the Lambda **Test** feature to verify data queries and write operations.

Check the execution results and logs in **Amazon CloudWatch**.

## Results

The **CloudManga-Reviews** function can read, save, and update reviews in **Amazon DynamoDB**.
