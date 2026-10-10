---
title: "Cấu hình Reviews API"
weight: 3
chapter: false
pre: "<b>5.7.3. </b>"
---

## Mục tiêu

Kết nối **AWS Lambda** với **Amazon API Gateway** để cung cấp các API xem và gửi đánh giá.

## Các bước thực hiện

### Bước 1: Tạo API Routes

Trong **Amazon API Gateway**, mở API `CloudManga-API`.

Tạo hai Route:

| Method | Route | Chức năng |
|---|---|---|
| **GET** | `/reviews` | Lấy danh sách và điểm đánh giá |
| **POST** | `/reviews` | Gửi hoặc cập nhật đánh giá |

Liên kết cả hai Route với Lambda `CloudManga-Reviews`.

### Bước 2: Cấu hình xác thực

Tại Route **POST /reviews**, gắn **JWT Authorizer**:

`CloudManga-Cognito-Auth`

Route **GET /reviews** không yêu cầu đăng nhập.

### Bước 3: Kết nối frontend

File **reviews.js** gửi yêu cầu đến API Gateway để:

1. Hiển thị điểm trung bình và danh sách nhận xét.
2. Kiểm tra trạng thái đăng nhập.
3. Gửi đánh giá kèm **Cognito Access Token** trong Header `Authorization`.

### Bước 4: Kiểm thử

Thực hiện kiểm thử:

- **GET /reviews:** Hiển thị danh sách đánh giá.
- **POST /reviews** không có token: Trả về **401 Unauthorized**.
- **POST /reviews** có token hợp lệ và dữ liệu hợp lệ: Lưu đánh giá vào DynamoDB.
- Tải lại trang để xác nhận đánh giá đã được cập nhật.

<div style="text-align: center;">
  <img src="/images/5.7.2.png"
       alt="Chức năng đánh giá CloudManga"
       style="width: 90%; height: auto;">
  <p><em>Hình 5.7.2. Chức năng đánh giá truyện trên CloudManga.</em></p>
</div>

## Kết quả

Hoàn thành chức năng xem và gửi đánh giá thông qua **Amazon API Gateway**, **AWS Lambda** và **Amazon DynamoDB**.

API gửi đánh giá được bảo vệ bằng **Amazon Cognito JWT Authorizer**.