---
title: "User Authentication"
weight: 6
chapter: false
pre: "<b>5.6. </b>"
---

## Objectives

Integrate **Amazon Cognito** to manage user registration, login, and logout for the **CloudManga** application.

Use the **JWT Authorizer** of **Amazon API Gateway** to validate tokens before allowing users to submit reviews.

## Implementation Steps

1. **Amazon Cognito:** Create a User Pool, App Client, and configure the login page.
2. **JWT Authorizer:** Validate Access Tokens and protect the `POST /reviews` API.

Once completed, users can log in using **Amazon Cognito**, while APIs requiring authentication will only accept valid tokens.
