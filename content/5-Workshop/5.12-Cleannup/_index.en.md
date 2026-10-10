---
title: "Resource Cleanup"
weight: 12
chapter: false
pre: "<b>5.12. </b>"
---

## Objectives

Check and clean up **AWS** resources that are no longer needed after the practical exercises to optimize costs and manage resources efficiently.

## Cleanup Process

The steps for checking and cleaning up resources are as follows:

1. **Amazon EC2:** Stop or delete Instances that are no longer in use.
2. **Amazon ECS:** Stop Tasks and Services, and delete test Clusters if they are no longer needed.
3. **Elastic Load Balancing:** Delete unused **Application Load Balancers** and Target Groups.
4. **EC2 Auto Scaling:** Delete Auto Scaling Groups and related resources after completing the practical exercises.
5. **Amazon CloudWatch:** Check Log Groups and log retention periods.
6. **AWS Billing:** Check incurred costs in **Billing and Cost Management**.

The resources currently supporting the **CloudManga** website, including **Amazon S3**, **AWS Lambda**, **Amazon API Gateway**, **Amazon Cognito**, and **Amazon DynamoDB**, are retained to maintain the application's operation.

## Notes

Resources must be carefully checked before deletion to avoid affecting the running system.

In particular, deleting an **S3 Bucket**, **DynamoDB Table**, or **Cognito User Pool** may result in data loss and directly affect CloudManga's functionality.

Additionally, resources that may continue to incur costs, such as **NAT Gateway**, **Elastic IP**, **Load Balancer**, and unused storage resources, should be checked.

## Results

Resources used for separate practical exercises are reviewed and cleaned up when they are no longer needed.

The main **CloudManga** services continue to be maintained to keep the website operational while minimizing costs incurred by unused test resources.
