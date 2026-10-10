---
title: "Build the Interface"
weight: 1
chapter: false
pre: "<b>5.8.1. </b>"
---

## Objectives

Design the **CloudManga** interface and display manga data retrieved from **Amazon API Gateway**.

## Implementation Steps

### Step 1: Build the Homepage

Use the following files:

- **index.html:** Build the homepage layout.
- **style.css:** Design the colors, layout, and interface.
- **app.js:** Handle manga list display and search functionality.

The homepage is designed with the following main components: a navigation bar, a search box, and a manga list.

### Step 2: Connect the API

The **app.js** file sends a request to the endpoint:

```text
GET /manga
```

The data returned from **AWS Lambda** is used to display manga titles, genres, chapter counts, and cover images.

The search functionality is handled using **JavaScript** based on the loaded manga list.

### Step 3: Build the Details Page

Use **detail.html** and **detail.js** to display manga information and the chapter list.

When a chapter is selected, the application navigates to the corresponding manga reader page.

<div style="text-align: center;">
  <img src="/images/5.8.1.png"
       alt="CloudManga Homepage Interface"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.8.1. CloudManga homepage interface.</em></p>
</div>

## Results

Completed the homepage interface, search functionality, and manga details page. Data is retrieved from **Amazon S3** through **API Gateway** and **AWS Lambda**.
