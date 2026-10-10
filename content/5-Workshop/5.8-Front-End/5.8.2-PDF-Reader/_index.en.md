---
title: "Build the Manga Reader"
weight: 2
chapter: false
pre: "<b>5.8.2. </b>"
---

## Objectives

Build an online manga reading feature by displaying **JPG** image pages stored in **Amazon S3**.

## Implementation Steps

### Step 1: Design the Manga Reader Page

Use two files:

- **reader.html:** Build the manga reader interface.
- **reader.js:** Handle loading and displaying chapter content.

The interface is designed to display image pages continuously in a vertical layout.

### Step 2: Connect the Chapter Reading API

When a chapter is selected, the frontend sends the following request:

```text
GET /chapter?mangaId=1&chapter=1
```

**AWS Lambda** retrieves the list of JPG pages from **Amazon S3** and generates a **Presigned URL** for each image.

The frontend receives the list of URLs, then loads and displays the images in order.

### Step 3: Test the Functionality

Open a manga chapter and check that:

- Image pages load successfully.
- Pages are displayed in the correct order.
- The interface can be scrolled to read the content.

<div style="text-align: center;">
  <img src="/images/5.8.2.png"
       alt="CloudManga Manga Reader"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.8.2. CloudManga's online manga reading feature.</em></p>
</div>

## Results

Completed the manga reader using **JPG** images. Content is loaded from **Amazon S3** through temporary **Presigned URLs**.
