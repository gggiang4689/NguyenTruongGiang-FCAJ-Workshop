---
title: "Configure API Gateway"
weight: 3
chapter: false
pre: "<b>5.5.3. </b>"
---

## Objectives

Use **Amazon API Gateway** to provide APIs that connect the **CloudManga** frontend with **AWS Lambda** functions.

## Implementation Steps

### Step 1: Create an HTTP API

1. Access **AWS Console → API Gateway**.
2. Select **Create API → HTTP API → Build**.
3. Enter the API name: `CloudManga-API`.
4. Select the **ap-southeast-1** Region.
5. Use the **$default** Stage.
6. Complete the API creation process.

### Step 2: Create API Routes

In the **Routes** section, create the following endpoints:

| Method | Route | Lambda |
|---|---|---|
| **GET** | `/manga` | `CloudManga-GetManga` |
| **GET** | `/chapter` | `CloudManga-GetChapter` |

In the **Integrations** section, connect each Route to its corresponding Function.

### Step 3: Configure CORS

In the **CORS** section, configure:

- **Allowed origins:** `http://localhost:5500` and `https://gggiang4689.github.io`
- **Allowed methods:** `GET`, `POST`, `OPTIONS`
- **Allowed headers:** `content-type`, `authorization`

This configuration allows the frontend running on localhost and **GitHub Pages** to send requests to the API.

### Step 4: Test the API

After configuration, the API address used in the project is:

```text
https://oo4qm8mooj.execute-api.ap-southeast-1.amazonaws.com
```

Test the API for retrieving the manga list:

```text
https://oo4qm8mooj.execute-api.ap-southeast-1.amazonaws.com/manga
```

<div style="text-align: center;">
  <img src="/images/5.5.2.png"
       alt="API Gateway Routes"
       style="width: 50%; height: auto;">

  <p><em>Figure 5.5.2. API Routes configured in Amazon API Gateway.</em></p>
</div>

### Step 5: Connect the Frontend

Update the API address in the **config.js** file so the frontend can send requests to **Amazon API Gateway**.

Test the application on localhost and confirm that the manga list is loaded from **Amazon S3**.

<div style="text-align: center;">
  <img src="/images/5.5.3.png"
       alt="CloudManga Displaying Data from AWS"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.5.3. The CloudManga interface receiving data from AWS.</em></p>
</div>

## Results

**Amazon API Gateway** has been connected to **AWS Lambda** to provide APIs for retrieving manga lists and reading chapters.

The frontend can receive data from S3 through the Serverless backend system.
