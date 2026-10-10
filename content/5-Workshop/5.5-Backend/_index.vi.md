---
title: "Xây dựng Backend"
weight: 5
chapter: false
pre: "<b>5.5. </b>"
---

## Mục tiêu

Xây dựng hệ thống backend **Serverless** cho ứng dụng **CloudManga** bằng **AWS Lambda** và **Amazon API Gateway**, kết hợp **AWS IAM** để quản lý quyền truy cập.

## Nội dung triển khai

1. **Cấu hình IAM Role:** Cấp quyền cho Lambda truy cập dữ liệu trên **Amazon S3**.
2. **Tạo AWS Lambda:** Xử lý yêu cầu lấy danh sách truyện và nội dung chương.
3. **Cấu hình API Gateway:** Tạo các endpoint để frontend giao tiếp với backend.

Sau khi hoàn thành, frontend có thể truy xuất dữ liệu truyện từ **Amazon S3** thông qua API mà không cần công khai Bucket.