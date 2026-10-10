---
title: "Create DynamoDB Table"
weight: 1
chapter: false
pre: "<b>5.7.1. </b>"
---

## Objectives

Use **Amazon DynamoDB** to store user ratings and reviews.

## Implementation Steps

### Step 1: Create a Table

1. Access **AWS Management Console → DynamoDB**.
2. Select **Tables → Create table**.
3. Enter the configuration information:

| Component | Value |
|---|---|
| **Table name** | `CloudManga-Reviews` |
| **Partition key** | `mangaId` – String |
| **Sort key** | `userId` – String |
| **Capacity mode** | On-demand |

4. Select **Create table**.

### Step 2: Verify the Table

After the table reaches the **Active** status, open **Explore table items** to check the data.

Each record contains the following main information:

- **mangaId:** Manga ID.
- **userId:** User ID.
- **rating:** Rating from 1 to 5.
- **comment:** Review content.
- **updatedAt:** Update time, if stored.

<div style="text-align: center;">
  <img src="/images/5.7.1.png"
       alt="CloudManga-Reviews Table in DynamoDB"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.7.1. CloudManga-Reviews table in Amazon DynamoDB.</em></p>
</div>

## Results

The **CloudManga-Reviews** table was successfully created and is ready to store the application's review data.
