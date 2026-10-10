---
title: "Configure Amazon Cognito"
weight: 1
chapter: false
pre: "<b>5.6.1. </b>"
---

## Objectives

Use **Amazon Cognito User Pools** to implement registration, login, and logout functionality for **CloudManga**.

## Implementation Steps

### Step 1: Create a User Pool

1. Access **AWS Management Console → Amazon Cognito**.
2. Select **Create user pool**.
3. Configure **Email** as the login method.
4. Enable email address verification.
5. Complete the User Pool creation process.

The User Pool used in the project is named `User pool - yowtoa`.

### Step 2: Configure the App Client

In the User Pool, create the `CloudManga-Web` application with the following settings:

| Component | Configuration |
|---|---|
| **Application type** | Single-page application (SPA) |
| **Authentication** | Authorization Code Flow with PKCE |
| **Callback URL** | `http://localhost:5500/` |
| **Production Callback URL** | `https://gggiang4689.github.io/CloudManga/` |
| **Sign-out URL** | Corresponding application URLs |

Configure **Cognito Managed Login** to provide the login and account registration interface.

### Step 3: Connect the Frontend

Update the following information in `config.js`:

- **Cognito Domain**
- **App Client ID**
- **Redirect URI**
- **OAuth Scopes**

The frontend redirects users to **Cognito Managed Login** when they select the login option.
After successful authentication, Cognito redirects users back to the application and provides an authorization code to exchange for tokens.

<div style="text-align: center;">
  <img src="/images/5.6.1.png"
       alt="Amazon Cognito Login Interface"
       style="width: 50%; height: auto;">

  <p><em>Figure 5.6.1. CloudManga login interface using Amazon Cognito.</em></p>
</div>

## Results

**Amazon Cognito** has been integrated into **CloudManga**, supporting registration, login, and logout.

The **Access Token** is used to authenticate API requests that require user permissions.
