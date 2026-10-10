---
title: "Tổng quan workshop"
weight: 1
chapter: false
pre: "<b>5.1. </b>"
---

### Mục tiêu

Giới thiệu bài toán, kiến trúc, luồng xử lý và kết quả triển khai **CloudManga**, một ứng dụng web đọc truyện và đánh giá manga được xây dựng theo kiến trúc **Serverless** trên nền tảng **Amazon Web Services**.

## 1. Bài toán và giải pháp

**CloudManga** được phát triển nhằm xây dựng một ứng dụng web cho phép người dùng tìm kiếm truyện, xem thông tin chi tiết, đọc các chương dưới dạng ảnh và gửi đánh giá sau khi đăng nhập.

Để giảm công việc quản lý máy chủ backend, hệ thống lựa chọn kiến trúc **Serverless**. Giao diện được xây dựng bằng **HTML, CSS và JavaScript**, triển khai trên **GitHub Pages**. Các chức năng backend được xử lý thông qua **Amazon API Gateway và AWS Lambda**.

**Amazon Cognito** đảm nhiệm xác thực người dùng, trong khi **Amazon DynamoDB** lưu trữ dữ liệu đánh giá.

## 2. Kiến trúc và lưu trữ

Hệ thống **CloudManga** sử dụng các thành phần chính:

- **GitHub Pages:** Triển khai giao diện web, phục vụ người dùng thông qua HTTPS.
- **Amazon API Gateway:** Cung cấp các API để frontend giao tiếp với backend.
- **AWS Lambda:** Xử lý yêu cầu lấy danh sách truyện, đọc chương và quản lý đánh giá.
- **Amazon S3:** Lưu trữ file `manga.json`, ảnh bìa và các trang JPG; Bucket được cấu hình riêng tư.
- **Amazon Cognito:** Quản lý tài khoản, đăng nhập và cấp token xác thực.
- **Amazon DynamoDB:** Lưu điểm số và nhận xét của người dùng.
- **AWS IAM:** Phân quyền cho Lambda truy cập tài nguyên AWS.
- **Amazon CloudWatch:** Ghi log và hỗ trợ kiểm tra hoạt động của các hàm Lambda.

Các file ảnh trong S3 được truy cập thông qua **Presigned URL** do Lambda tạo ra, giúp hạn chế việc phải công khai trực tiếp Bucket.


<div style="text-align: center;">
  <img src="/images/CloudManga-architecture.png"
       alt="Kiến trúc CloudManga"
       style="width: 75%; height: auto;">

  <p><em>Hình 5.1. Sơ đồ kiến trúc tổng quan CloudManga trên AWS.</em></p>
</div>


## 3. Luồng xử lý

1. Người dùng truy cập giao diện **CloudManga** trên **GitHub Pages**.
2. Frontend gửi yêu cầu `GET /manga` đến **API Gateway** để lấy danh sách truyện.
3. **Lambda** đọc dữ liệu từ **S3** và trả về thông tin truyện cùng Presigned URL của ảnh bìa.
4. Khi người dùng chọn chương, API `GET /chapter` gọi Lambda để lấy danh sách ảnh JPG tương ứng trên S3.
5. Khi đăng nhập, người dùng được chuyển đến **Amazon Cognito** để xác thực và nhận token.
6. Khi gửi đánh giá, **API Gateway** kiểm tra **JWT** trước khi **Lambda** lưu dữ liệu vào **DynamoDB**.
7. Frontend gọi `GET /reviews` để lấy và hiển thị nhận xét cùng điểm đánh giá.

## 4. Phạm vi triển khai

Workshop tập trung xây dựng một ứng dụng đọc truyện quy mô nhỏ với sáu bộ truyện, sử dụng các dịch vụ **AWS Serverless**.

Các chức năng đã được triển khai bao gồm danh sách truyện, tìm kiếm, trang chi tiết, đọc ảnh JPG, đăng nhập Cognito và đánh giá bằng DynamoDB. Frontend được triển khai trên GitHub Pages. Backend gồm ba Lambda chính: `CloudManga-GetManga`, `CloudManga-GetChapter` và `CloudManga-Reviews`.

Trong quá trình học AWS, các dịch vụ EC2, VPC, Docker, ECS và Application Load Balancer cũng đã được thực hành ở các bài lab riêng. Tuy nhiên, chúng không phải thành phần xử lý chính của phiên bản CloudManga Serverless hiện tại.

## 5. Kết quả

CloudManga đã được triển khai trên GitHub Pages và kết nối với các dịch vụ AWS. Quá trình kiểm thử ghi nhận khả năng hiển thị danh sách sáu bộ truyện, truy xuất ảnh bìa từ S3, đọc chương bằng ảnh JPG, đăng nhập bằng Cognito và gửi đánh giá được lưu trong DynamoDB.

Dự án giúp tôi hiểu rõ hơn quá trình kết nối các dịch vụ AWS, quản lý quyền IAM, xây dựng API và triển khai một ứng dụng web dựa trên kiến trúc Serverless.