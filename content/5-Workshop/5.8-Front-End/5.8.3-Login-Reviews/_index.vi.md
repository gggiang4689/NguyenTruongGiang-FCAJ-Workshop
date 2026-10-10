---
title: "Tích hợp đăng nhập và đánh giá"
weight: 3
chapter: false
pre: "<b>5.8.3. </b>"
---

## Mục tiêu

Tích hợp **Amazon Cognito** và API Reviews vào giao diện **CloudManga**, hỗ trợ đăng nhập và đánh giá truyện.

## Các bước thực hiện

### Bước 1: Tích hợp đăng nhập

Cấu hình thông tin **Amazon Cognito** trong file **config.js**.

Các nút đăng nhập và đăng xuất trên giao diện được liên kết với **Cognito Managed Login**.

Sau khi xác thực thành công, ứng dụng nhận token và cập nhật trạng thái đăng nhập.

### Bước 2: Tích hợp chức năng đánh giá

File **reviews.js** thực hiện:

1. Gọi API `GET /reviews` để hiển thị danh sách nhận xét và điểm trung bình.
2. Hiển thị biểu mẫu chấm điểm từ 1 đến 5 sao.
3. Kiểm tra trạng thái đăng nhập trước khi gửi đánh giá.
4. Gửi yêu cầu `POST /reviews` kèm **Cognito Access Token**.
5. Cập nhật danh sách đánh giá sau khi gửi thành công.

### Bước 3: Kiểm thử

Kiểm tra chức năng đăng nhập, đăng xuất và gửi đánh giá.

**JWT Authorizer** của **Amazon API Gateway** đảm bảo API `POST /reviews` chỉ tiếp nhận các yêu cầu có token hợp lệ.

## Kết quả

Hoàn thành tích hợp **Amazon Cognito** và chức năng đánh giá trên giao diện **CloudManga**.

Người dùng có thể xem nhận xét công khai và gửi đánh giá sau khi đăng nhập.