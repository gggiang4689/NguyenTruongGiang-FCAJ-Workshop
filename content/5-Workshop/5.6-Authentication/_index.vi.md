---
title: "Xác thực người dùng"
weight: 6
chapter: false
pre: "<b>5.6. </b>"
---

## Mục tiêu

Tích hợp **Amazon Cognito** để quản lý đăng ký, đăng nhập và đăng xuất cho ứng dụng **CloudManga**.

Sử dụng **JWT Authorizer** của **Amazon API Gateway** để xác thực token trước khi cho phép người dùng gửi đánh giá.

## Nội dung triển khai

1. **Amazon Cognito:** Tạo User Pool, App Client và cấu hình trang đăng nhập.
2. **JWT Authorizer:** Kiểm tra Access Token và bảo vệ API `POST /reviews`.

Sau khi hoàn thành, người dùng có thể đăng nhập bằng **Amazon Cognito**, trong khi các API yêu cầu xác thực chỉ chấp nhận token hợp lệ.