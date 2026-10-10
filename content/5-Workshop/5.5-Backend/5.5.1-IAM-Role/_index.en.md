---
title: "Configure IAM Role"
weight: 1
chapter: false
pre: "<b>5.5.1. </b>"
---

## Objectives

Create an **IAM Role** that allows **AWS Lambda** to access data stored in **Amazon S3** and write logs to **Amazon CloudWatch**.

## Implementation Steps

### Step 1: Create an IAM Role

1. Access **AWS Management Console → IAM → Roles**.
2. Select **Create role**.
3. Under **Trusted entity type**, select **AWS service**.
4. Under **Use case**, select **Lambda**.
5. Attach the **AWSLambdaBasicExecutionRole** policy to allow Lambda to write logs.
6. Enter the Role name: `CloudJourney-Lambda-Role`.
7. Select **Create role**.

### Step 2: Grant S3 Read Permissions

Open the newly created Role and select **Add permissions → Create inline policy**.

Switch to **JSON** mode and enter:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::cloudmanga-storage-2026/manga/*",
        "arn:aws:s3:::cloudmanga-storage-2026/covers/*"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket"
      ],
      "Resource": "arn:aws:s3:::cloudmanga-storage-2026",
      "Condition": {
        "StringLike": {
          "s3:prefix": [
            "manga/*"
          ]
        }
      }
    }
  ]
}
```

Enter the Policy name:

`CloudManga-S3-ReadPolicy`

Select **Create policy**.

### Step 3: Verify Permissions

Confirm that the **IAM Role** has the following permissions:

- **AWSLambdaBasicExecutionRole:** Writes logs.
- **CloudManga-S3-ReadPolicy:** Reads JSON files, cover images, and manga page lists from S3.

## Results

The **IAM Role** has been configured to allow Lambda to access the necessary resources according to the **Least Privilege** principle.
