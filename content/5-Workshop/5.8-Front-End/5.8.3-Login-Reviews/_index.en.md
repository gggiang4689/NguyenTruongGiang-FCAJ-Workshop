---
title: "Integrate Login and Reviews"
weight: 3
chapter: false
pre: "<b>5.8.3. </b>"
---

## Objectives

Integrate **Amazon Cognito** and the Reviews API into the **CloudManga** interface to support login and manga reviews.

## Implementation Steps

### Step 1: Integrate Login

Configure **Amazon Cognito** information in the **config.js** file.

The login and logout buttons on the interface are linked to **Cognito Managed Login**.

After successful authentication, the application receives the token and updates the login status.

### Step 2: Integrate the Review Feature

The **reviews.js** file performs the following tasks:

1. Call the `GET /reviews` API to display the review list and average rating.
2. Display a rating form from 1 to 5 stars.
3. Check the login status before submitting a review.
4. Send a `POST /reviews` request with the **Cognito Access Token**.
5. Update the review list after successful submission.

### Step 3: Test the Functionality

Test the login, logout, and review submission features.

The **JWT Authorizer** of **Amazon API Gateway** ensures that the `POST /reviews` API only accepts requests with valid tokens.

## Results

Completed the integration of **Amazon Cognito** and the review feature into the **CloudManga** interface.

Users can view reviews publicly and submit reviews after logging in.
