---
title: "Project Setup"
weight: 3
chapter: false
pre: "<b>5.3. </b>"
---

## Objectives

Prepare the frontend source code, folder structure, and development environment for the **CloudManga** application before connecting it to **AWS** services.

## 1. Create the Project Folder

Create the **CloudManga-Capstone** folder and open it using **Visual Studio Code**.

The application's source code structure:

```text
CloudManga-Capstone/
├── index.html
├── style.css
├── app.js
├── config.js
├── detail.html
├── detail.js
├── reader.html
├── reader.js
└── reviews.js
```

Main components:

- **index.html / app.js:** Homepage, manga list, and search functionality.
- **detail.html / detail.js:** Manga details page and chapter list.
- **reader.html / reader.js:** Displays manga pages as JPG images.
- **reviews.js:** Displays and submits manga reviews.
- **style.css:** Interface design.
- **config.js:** Configures the API address and **Amazon Cognito**.

## 2. Configure AWS Connections

The **config.js** file is used to manage connection information between the frontend and backend.

The main configurations include:

- **API Gateway Endpoint:** API address for handling manga lists, chapters, and reviews.
- **Amazon Cognito Domain:** Login page address.
- **Cognito App Client ID:** Application identifier.
- **Redirect URI:** Redirect address after login or logout.

The API endpoint used:

```text
https://oo4qm8mooj.execute-api.ap-southeast-1.amazonaws.com/manga
```

The configuration information must be updated after completing the setup of **Amazon API Gateway** and **Amazon Cognito**.

Sensitive information such as **AWS Access Keys** or **Client Secrets** must not be stored in publicly accessible frontend source code.

## 3. Test the Application on Localhost

Open a Terminal in the **CloudManga-Capstone** folder, then run the following command:

```powershell
python -m http.server 5500
```

Access the following address:

```text
http://localhost:5500/
```

Check that the interface is displayed correctly and that the **HTML**, **CSS**, and **JavaScript** files function properly.

<div style="text-align: center;">
  <img src="/images/5.3.2.png"
       alt="CloudManga Interface on Localhost"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.3.2. Testing the CloudManga interface on localhost.</em></p>
</div>

At this stage, features requiring data from **AWS** will only function fully after the backend has been configured.

## 4. Results

Completed the preparation of the **CloudManga** project structure, frontend files, and local testing environment.

The source code is ready to connect to **Amazon S3**, **AWS Lambda**, **Amazon API Gateway**, and other AWS services in the following deployment steps.
