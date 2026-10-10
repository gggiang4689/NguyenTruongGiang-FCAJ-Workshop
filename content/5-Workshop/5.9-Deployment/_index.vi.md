---
title: "Triển khai website"
weight: 9
chapter: false
pre: "<b>5.9. </b>"
---

## Quy trình triển khai

Quá trình triển khai **CloudManga** lên **GitHub Pages** được thực hiện như sau:

1. Hoàn thiện mã nguồn frontend gồm **HTML**, **CSS** và **JavaScript**.
2. Tải mã nguồn lên repository **CloudManga** trên **GitHub**.
3. Kích hoạt **GitHub Pages**, lựa chọn nhánh `main` và thư mục `/ (root)`.
4. Cập nhật **Amazon Cognito Callback URL** và cấu hình **CORS** trong **Amazon API Gateway** cho tên miền GitHub Pages.
5. Kiểm tra khả năng truy cập website và kết nối với các dịch vụ **AWS**.

Website sau khi triển khai:

[https://gggiang4689.github.io/CloudManga/](https://gggiang4689.github.io/CloudManga/)

## Giới hạn

Quy trình phát hành được thực hiện thủ công thông qua **GitHub**. Dự án chưa triển khai hệ thống **CI/CD** hoặc quy trình kiểm thử tự động trước khi phát hành.

## Kết quả

Website **CloudManga** đã được xuất bản trên **GitHub Pages** và có thể truy cập qua HTTPS.

Frontend được triển khai độc lập, trong khi backend tiếp tục sử dụng **AWS Lambda**, **Amazon API Gateway**, **Amazon S3** và **Amazon DynamoDB**.