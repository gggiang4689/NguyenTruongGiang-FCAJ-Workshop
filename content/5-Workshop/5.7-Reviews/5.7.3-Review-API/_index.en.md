---
title: "Configure Reviews API"
weight: 3
chapter: false
pre: "<b>5.7.3. </b>"
---

## Objectives

Connect **AWS Lambda** with **Amazon API Gateway** to provide APIs for viewing and submitting reviews.

## Implementation Steps

### Step 1: Create API Routes

In **Amazon API Gateway**, open the `CloudManga-API` API.

Create two Routes:

| Method | Route | Function |
|---|---|---|
| **GET** | `/reviews` | Retrieve the review list and ratings |
| **POST** | `/reviews` | Submit or update reviews |

Connect both Routes to the `CloudManga-Reviews` Lambda function.

### Step 2: Configure Authentication

For the **POST /reviews** Route, attach the **JWT Authorizer**:

`CloudManga-Cognito-Auth`

The **GET /reviews** Route does not require login.

### Step 3: Connect the Frontend

The **reviews.js** file sends requests to API Gateway to:

1. Display the average rating and list of reviews.
2. Check the login status.
3. Submit reviews with the **Cognito Access Token** in the `Authorization` Header.

### Step 4: Test the APIs

Perform the following tests:

- **GET /reviews:** Display the list of reviews.
- **POST /reviews** without a token: Return **401 Unauthorized**.
- **POST /reviews** with a valid token and valid data: Save the review to DynamoDB.
- Reload the page to confirm that the review has been updated.

<div style="text-align: center;">
  <img src="/images/5.7.2.png"
       alt="CloudManga Review Feature"
       style="width: 90%; height: auto;">
  <p><em>Figure 5.7.2. Manga review feature on CloudManga.</em></p>
</div>

## Results

Completed the review viewing and submission features using **Amazon API Gateway**, **AWS Lambda**, and **Amazon DynamoDB**.

The review submission API is protected by the **Amazon Cognito JWT Authorizer**.
