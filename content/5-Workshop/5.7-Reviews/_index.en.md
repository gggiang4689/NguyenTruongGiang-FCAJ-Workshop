---
title: "Review System"
weight: 7
chapter: false
pre: "<b>5.7. </b>"
---

## Objectives

Build a manga review feature using **Amazon DynamoDB**, **AWS Lambda**, and **Amazon API Gateway**.

The system allows users to view reviews publicly and requires login through **Amazon Cognito** before submitting a review.

## Implementation Steps

1. **Amazon DynamoDB:** Create a table to store ratings and reviews.
2. **AWS Lambda:** Develop functions to read and write reviews.
3. **Amazon API Gateway:** Configure the `GET /reviews` and `POST /reviews` APIs.

The review submission API is protected by the **JWT Authorizer** configured in Section 5.6.
