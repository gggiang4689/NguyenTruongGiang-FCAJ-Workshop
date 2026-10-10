---
title: "Hệ thống đánh giá"
weight: 7
chapter: false
pre: "<b>5.7. </b>"
---

## Mục tiêu

Xây dựng chức năng đánh giá truyện bằng **Amazon DynamoDB**, **AWS Lambda** và **Amazon API Gateway**.

Hệ thống cho phép xem nhận xét công khai và yêu cầu đăng nhập bằng **Amazon Cognito** trước khi gửi đánh giá.

## Nội dung triển khai

1. **Amazon DynamoDB:** Tạo bảng lưu điểm số và nhận xét.
2. **AWS Lambda:** Xây dựng chức năng đọc và ghi đánh giá.
3. **Amazon API Gateway:** Cấu hình API `GET /reviews` và `POST /reviews`.

API gửi đánh giá được bảo vệ bằng **JWT Authorizer** đã cấu hình ở phần 5.6.