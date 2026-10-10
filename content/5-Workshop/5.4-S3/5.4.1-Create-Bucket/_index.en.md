---
title: "Create S3 Bucket"
weight: 1
chapter: false
pre: "<b>5.4.1. </b>"
---

## Objectives

Create an **Amazon S3 Bucket** to store CloudManga data and configure secure access permissions.

## Implementation Steps

### Step 1: Access Amazon S3

1. Sign in to the **AWS Management Console**.
2. Search for the **S3** service.
3. Select **Buckets → Create bucket**.

### Step 2: Configure the Bucket

Enter the following information:

| Parameter | Value |
|---|---|
| **Bucket name** | `cloudmanga-storage-2026` |
| **AWS Region** | `ap-southeast-1` – Singapore |
| **Object Ownership** | ACLs disabled |
| **Block Public Access** | Block all public access |
| **Bucket Versioning** | Disable |

Keep the other default settings and select **Create bucket**.

<div style="text-align: center;">
  <img src="/images/5.4.1.png"
       alt="CloudManga S3 Bucket Configuration"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.4.1. Configuring the Amazon S3 Bucket for CloudManga.</em></p>
</div>

### Step 3: Verify the Bucket

Open the **S3 Buckets** list and confirm that the `cloudmanga-storage-2026` Bucket has been created.

Ensure that **Block all public access** remains enabled to prevent direct public access to the data.

## Results

Successfully created the **cloudmanga-storage-2026** Bucket in the Singapore Region, ready to store CloudManga data.
