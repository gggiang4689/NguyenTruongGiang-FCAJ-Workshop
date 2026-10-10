---
title: "Create AWS Lambda"
weight: 2
chapter: false
pre: "<b>5.5.2. </b>"
---

## Objectives

Use **AWS Lambda** to retrieve data from **Amazon S3** and provide manga information to the frontend.

## Implementation Steps

### Step 1: Create a Lambda Function to Retrieve the Manga List

1. Access **AWS Console → Lambda → Create function**.
2. Select **Author from scratch**.
3. Enter the Function name: `CloudManga-GetManga`.
4. Select **Python 3.x** as the Runtime.
5. Under **Execution role**, select **Use an existing role**.
6. Select `CloudJourney-Lambda-Role`.
7. Click **Create function**.

### Step 2: Develop the Processing Function

The `CloudManga-GetManga` function uses the **Boto3** library to:

1. Read the `manga/manga.json` file from **Amazon S3**.
2. Convert JSON data into a manga list.
3. Generate **Presigned URLs** for cover images.
4. Return the results in JSON format for the frontend.

### Step 3: Create a Lambda Function to Read Chapters

Create another Function:

`CloudManga-GetChapter`

The function performs the following tasks:

1. Receive two parameters: `mangaId` and `chapter`.
2. Use **Boto3** to retrieve the corresponding JPG images from S3.
3. Sort the images by filename.
4. Generate a **Presigned URL** for each page.
5. Return a list of URLs to display on the manga reader page.

### Step 4: Test Lambda

On the Function management page, select **Test** to verify the returned results.

<div style="text-align: center;">
  <img src="/images/5.5.1.png"
       alt="AWS Lambda Testing"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.5.1. Testing the CloudManga AWS Lambda function.</em></p>
</div>

Check the JSON response and confirm that the execution was successful.

## Results

The **CloudManga-GetManga** and **CloudManga-GetChapter** functions have been created to process manga data stored in **Amazon S3**.

The data is returned in JSON format, including **Presigned URLs** used to display images.
