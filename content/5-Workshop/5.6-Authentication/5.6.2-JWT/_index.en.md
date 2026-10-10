---
title: "Configure JWT Authorizer"
weight: 2
chapter: false
pre: "<b>5.6.2. </b>"
---

## Objectives

Use the **JWT Authorizer** of **Amazon API Gateway** to protect the review submission API, allowing only requests with a valid **Cognito Access Token**.

## Implementation Steps

### Step 1: Create a JWT Authorizer

1. Access **Amazon API Gateway**.
2. Select the `CloudManga-API` API.
3. Open **Authorization → Manage authorizers**.
4. Select **Create authorizer**.
5. Select the **JWT** type.

Configure the following information:

| Component | Value |
|---|---|
| **Name** | `CloudManga-Cognito-Auth` |
| **Identity source** | `$request.header.Authorization` |
| **Issuer URL** | Cognito User Pool URL |
| **Audience** | App Client ID of `CloudManga-Web` |

The **Issuer URL** has the following structure:

```text
https://cognito-idp.ap-southeast-1.amazonaws.com/<user-pool-id>
```

The **User Pool ID** and **App Client ID** values are obtained directly from the **Amazon Cognito** configuration.

### Step 2: Protect the Review Submission API

In **API Gateway → Routes**, select:

`POST /reviews`

Under **Authorization**, attach the Authorizer:

`CloudManga-Cognito-Auth`

The APIs are configured as follows:

| API | Authentication Required |
|---|---|
| `GET /manga` | No |
| `GET /chapter` | No |
| `GET /reviews` | No |
| **`POST /reviews`** | **JWT Authorizer** |

<div style="text-align: center;">
  <img src="/images/5.6.2.png"
       alt="Configuring JWT Authorizer in API Gateway"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.6.2. JWT Authorizer attached to the POST /reviews API.</em></p>
</div>

### Step 3: Test Authentication

Test the `POST /reviews` API in two scenarios:

- **Without a token:** The API rejects the request with the **401 Unauthorized** status code.
- **With a valid Access Token:** The request is forwarded to **AWS Lambda** to validate and process the review data.

The frontend sends the token in the HTTP Header:

```text
Authorization: Bearer <access-token>
```

## Results

Completed the **JWT Authorizer** configuration to protect the `POST /reviews` API.

The system allows users to view manga lists and reviews publicly but requires login before submitting a review.
