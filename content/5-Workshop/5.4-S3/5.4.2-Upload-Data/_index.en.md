---
title: "Upload Data to S3"
weight: 2
chapter: false
pre: "<b>5.4.2. </b>"
---

## Objectives

Upload manga data and images to **Amazon S3** to support the manga listing and chapter reading features of **CloudManga**.

## Implementation Steps

### Step 1: Prepare the Data

The data is organized according to the following structure:

```text
cloudmanga-storage-2026/
├── covers/
│   ├── berserk.jpg
│   ├── fire punch.jpg
│   ├── gotoubun.jpg
│   └── ...
└── manga/
    ├── manga.json
    ├── 1/
    │   ├── chapter-01/
    │   │   ├── 001.jpg
    │   │   └── 002.jpg
    │   │       ...
    │   └── chapter-02/
    └── ...
```

Where:

- **covers/:** Stores manga cover images.
- **manga/manga.json:** Stores manga titles, genres, and chapter counts.
- **manga/{id}/chapter-XX/:** Stores JPG pages for each chapter.

### Step 2: Upload Data to S3

1. Access **Amazon S3 → Buckets**.
2. Select the `cloudmanga-storage-2026` Bucket.
3. Select **Upload → Add files / Add folder**.
4. Upload the files to the correct locations according to the prepared structure.
5. Select **Upload** to complete the process.

### Step 3: Verify the Data

Verify that the files appear at the correct paths in the Bucket.

<div style="text-align: center;">
  <img src="/images/5.4.2.png"
       alt="CloudManga Data in Amazon S3"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.4.2. CloudManga folders and data in Amazon S3.</em></p>
</div>

### Step 4: Check Access Permissions

Keep the **S3 Bucket** private and do not enable Public Access.

Read permissions will be granted to **AWS Lambda** through an **IAM Role** in the following section. Lambda uses **Presigned URLs** to provide temporary image access links to the frontend.

## Results

Manga data and images have been stored in **Amazon S3**, ready to be connected to **AWS Lambda** to build APIs for CloudManga.
