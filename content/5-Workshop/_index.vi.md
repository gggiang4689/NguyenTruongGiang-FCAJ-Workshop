---
title: "Workshop"
weight: 5
chapter: false
pre: "<b>5. </b>"
---

# XÂY DỰNG ỨNG DỤNG ĐỌC TRUYỆN CLOUDMANGA TRÊN AWS

## Tổng quan

Trong Workshop này, tôi sẽ xây dựng và triển khai **CloudManga**, một ứng dụng web đọc truyện và đánh giá manga dựa trên kiến trúc Serverless của Amazon Web Services (AWS).

Hệ thống sử dụng **Amazon S3** để lưu trữ thông tin truyện và hình ảnh, **AWS Lambda** để xử lý dữ liệu, **Amazon API Gateway** để cung cấp API, **Amazon Cognito** để xác thực người dùng và **Amazon DynamoDB** để lưu trữ đánh giá.

Frontend được phát triển bằng HTML, CSS và JavaScript, sau đó triển khai trên GitHub Pages.

Các chức năng chính bao gồm:

- Hiển thị danh sách và tìm kiếm truyện.
- Xem thông tin chi tiết và danh sách chương.
- Đọc truyện bằng các trang ảnh JPG lưu trên Amazon S3.
- Đăng ký, đăng nhập và đăng xuất bằng Amazon Cognito.
- Đánh giá truyện từ 1 đến 5 sao và viết nhận xét.
- Sử dụng JWT Authorizer để bảo vệ API gửi đánh giá.

## Nội dung

1. [Tổng quan dự án](5.1-Overview/)
2. [Điều kiện chuẩn bị](5.2-Prerequisites/)
3. [Chuẩn bị dự án](5.3-Project-Setup/)
4. [Cấu hình Amazon S3](5.4-S3/)
5. [Xây dựng Backend](5.5-Backend/)
6. [Xác thực Amazon Cognito](5.6-Authentication/)
7. [DynamoDB Reviews](5.7-Reviews/)
8. [Phát triển Frontend](5.8-Frontend/)
9. [Triển khai GitHub Pages](5.9-Deployment/)
10. [Giám sát hệ thống](5.10-Monitoring/)
11. [Kiểm thử](5.11-Testing/)
12. [Dọn dẹp tài nguyên](5.12-Cleanup/)

## Kết quả triển khai

CloudManga đã được triển khai trên GitHub Pages và kết nối với các dịch vụ AWS.

**Website:** [CloudManga](https://gggiang4689.github.io/CloudManga/)

**Mã nguồn:** [GitHub Repository](https://github.com/gggiang4689/CloudManga)