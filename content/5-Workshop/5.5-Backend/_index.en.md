---
title: "Backend Development"
weight: 5
chapter: false
pre: "<b>5.5. </b>"
---

## Objectives

Build a **Serverless** backend system for the **CloudManga** application using **AWS Lambda** and **Amazon API Gateway**, combined with **AWS IAM** to manage access permissions.

## Implementation Steps

1. **Configure IAM Role:** Grant Lambda permission to access data stored in **Amazon S3**.
2. **Create AWS Lambda:** Process requests to retrieve manga lists and chapter content.
3. **Configure API Gateway:** Create endpoints for communication between the frontend and backend.

Once completed, the frontend can retrieve manga data from **Amazon S3** through APIs without making the Bucket publicly accessible.
