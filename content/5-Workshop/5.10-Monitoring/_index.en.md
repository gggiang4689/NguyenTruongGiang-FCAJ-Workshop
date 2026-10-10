---
title: "System Monitoring"
weight: 10
chapter: false
pre: "<b>5.10. </b>"
---

## Monitoring Process

The **CloudManga** system uses **Amazon CloudWatch** to record and monitor the activities of **AWS Lambda** functions.

The monitoring process is carried out as follows:

1. Access **AWS Management Console → CloudWatch → Log groups**.
2. Select the Log Group corresponding to the `CloudManga-GetManga`, `CloudManga-GetChapter`, or `CloudManga-Reviews` function.
3. Open **Log streams** to check execution history and error messages.
4. Monitor the **Invocations**, **Errors**, and **Duration** metrics in the **Monitoring** section of Lambda.
5. Check and adjust the configuration when errors are detected during API processing.

<div style="text-align: center;">
  <img src="/images/5.10.1.png"
       alt="Monitoring Lambda with Amazon CloudWatch"
       style="width: 90%; height: auto;">

  <p><em>Figure 5.10.1. Monitoring AWS Lambda activities using Amazon CloudWatch.</em></p>
</div>

## Limitations

The system currently uses the basic monitoring features of **Amazon CloudWatch**. An automated alerting system or a dedicated monitoring dashboard has not yet been implemented.

## Results

**Amazon CloudWatch** supports checking execution history, detecting errors, and monitoring the performance of **AWS Lambda** functions, assisting in the operation and testing of **CloudManga**.
