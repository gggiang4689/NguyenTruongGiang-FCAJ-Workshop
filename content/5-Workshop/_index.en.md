---
title: "Workshop"
weight: 5
chapter: false
pre: "<b>5. </b>"
---

# BUILDING THE CLOUDMANGA READING APPLICATION ON AWS

## Overview

In this Workshop, I will build and deploy **CloudManga**, a manga reading and review web application based on the Serverless architecture of Amazon Web Services (AWS).

The system uses **Amazon S3** to store manga information and images, **AWS Lambda** to process data, **Amazon API Gateway** to provide APIs, **Amazon Cognito** to authenticate users, and **Amazon DynamoDB** to store reviews.

The frontend is developed using HTML, CSS, and JavaScript, then deployed on GitHub Pages.

The main features include:

- Displaying and searching manga lists.
- Viewing manga details and chapter lists.
- Reading manga through JPG image pages stored on Amazon S3.
- Registering, logging in, and logging out using Amazon Cognito.
- Rating manga from 1 to 5 stars and writing reviews.
- Using JWT Authorizer to protect the review submission API.

## Contents

1. [Project Overview](5.1-Overview/)
2. [Prerequisites](5.2-Prerequisites/)
3. [Project Setup](5.3-Project-Setup/)
4. [Amazon S3 Configuration](5.4-S3/)
5. [Backend Development](5.5-Backend/)
6. [Amazon Cognito Authentication](5.6-Authentication/)
7. [DynamoDB Reviews](5.7-Reviews/)
8. [Frontend Development](5.8-Frontend/)
9. [GitHub Pages Deployment](5.9-Deployment/)
10. [System Monitoring](5.10-Monitoring/)
11. [Testing](5.11-Testing/)
12. [Resource Cleanup](5.12-Cleanup/)

## Deployment Results

CloudManga has been deployed on GitHub Pages and connected to AWS services.

**Website:** [CloudManga](https://gggiang4689.github.io/CloudManga/)

**Source Code:** [GitHub Repository](https://github.com/gggiang4689/CloudManga)
