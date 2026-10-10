---
title: "Amazon S3"
weight: 4
chapter: false
pre: "<b>5.4. </b>"
---

## Mục tiêu

Sử dụng **Amazon Simple Storage Service (Amazon S3)** để lưu trữ dữ liệu truyện và hình ảnh cho ứng dụng **CloudManga**.

## Nội dung triển khai

Quá trình cấu hình **Amazon S3** gồm hai bước:

1. **Tạo S3 Bucket:** Tạo Bucket tại Region Singapore và cấu hình quyền truy cập riêng tư.
2. **Tải dữ liệu lên S3:** Tổ chức và tải file JSON, ảnh bìa cùng các trang truyện lên Bucket.

Dữ liệu trong Bucket được truy cập thông qua **AWS Lambda** và **Presigned URL**, không công khai trực tiếp toàn bộ nội dung S3.

Sau khi hoàn thành, dữ liệu sẵn sàng phục vụ các API của CloudManga.