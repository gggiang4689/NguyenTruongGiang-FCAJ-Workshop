---
title: "Amazon S3"
weight: 4
chapter: false
pre: "<b>5.4. </b>"
---

## Objectives

Use **Amazon Simple Storage Service (Amazon S3)** to store manga data and images for the **CloudManga** application.

## Implementation Steps

The **Amazon S3** configuration process consists of two steps:

1. **Create an S3 Bucket:** Create a Bucket in the Singapore Region and configure private access permissions.
2. **Upload Data to S3:** Organize and upload JSON files, cover images, and manga pages to the Bucket.

Data in the Bucket is accessed through **AWS Lambda** and **Presigned URLs**, without making the entire S3 content publicly accessible.

Once completed, the data is ready to be used by the CloudManga APIs.
