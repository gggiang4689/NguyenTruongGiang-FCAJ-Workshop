---
title: "Cấu hình JWT Authorizer"
weight: 2
chapter: false
pre: "<b>5.6.2. </b>"
---

## Mục tiêu

Sử dụng **JWT Authorizer** của **Amazon API Gateway** để bảo vệ API gửi đánh giá, chỉ cho phép các yêu cầu có **Cognito Access Token** hợp lệ.

## Các bước thực hiện

### Bước 1: Tạo JWT Authorizer

1. Truy cập **Amazon API Gateway**.
2. Chọn API `CloudManga-API`.
3. Mở mục **Authorization → Manage authorizers**.
4. Chọn **Create authorizer**.
5. Chọn loại **JWT**.

Thiết lập các thông tin:

| Thành phần | Giá trị |
|---|---|
| **Name** | `CloudManga-Cognito-Auth` |
| **Identity source** | `$request.header.Authorization` |
| **Issuer URL** | URL của Cognito User Pool |
| **Audience** | App Client ID của `CloudManga-Web` |

**Issuer URL** có cấu trúc:

```text
https://cognito-idp.ap-southeast-1.amazonaws.com/<user-pool-id>
```

Các giá trị **User Pool ID** và **App Client ID** được lấy trực tiếp từ cấu hình **Amazon Cognito**.

### Bước 2: Bảo vệ API gửi đánh giá

Trong **API Gateway → Routes**, chọn:

`POST /reviews`

Tại mục **Authorization**, gắn Authorizer:

`CloudManga-Cognito-Auth`

Các API được cấu hình như sau:

| API | Yêu cầu xác thực |
|---|---|
| `GET /manga` | Không |
| `GET /chapter` | Không |
| `GET /reviews` | Không |
| **`POST /reviews`** | **JWT Authorizer** |

<div style="text-align: center;">
  <img src="/images/5.6.2.png"
       alt="Cấu hình JWT Authorizer trong API Gateway"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.6.2. JWT Authorizer được gắn vào API POST /reviews.</em></p>
</div>

### Bước 3: Kiểm thử xác thực

Thực hiện kiểm thử API `POST /reviews` trong hai trường hợp:

- **Không có token:** API từ chối yêu cầu với mã trạng thái **401 Unauthorized**.
- **Có Access Token hợp lệ:** Yêu cầu được chuyển đến **AWS Lambda** để kiểm tra và xử lý dữ liệu đánh giá.

Frontend gửi token trong HTTP Header:

```text
Authorization: Bearer <access-token>
```

## Kết quả

Hoàn thành cấu hình **JWT Authorizer** để bảo vệ API `POST /reviews`.

Hệ thống cho phép xem danh sách truyện và đánh giá công khai, nhưng yêu cầu đăng nhập trước khi gửi đánh giá.