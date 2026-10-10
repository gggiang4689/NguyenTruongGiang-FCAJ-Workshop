---
title: "Cấu hình Amazon Cognito"
weight: 1
chapter: false
pre: "<b>5.6.1. </b>"
---

## Mục tiêu

Sử dụng **Amazon Cognito User Pools** để triển khai chức năng đăng ký, đăng nhập và đăng xuất cho **CloudManga**.

## Các bước thực hiện

### Bước 1: Tạo User Pool

1. Truy cập **AWS Management Console → Amazon Cognito**.
2. Chọn **Create user pool**.
3. Cấu hình phương thức đăng nhập bằng **Email**.
4. Bật xác minh địa chỉ email.
5. Hoàn thành tạo User Pool.

User Pool sử dụng trong dự án có tên `User pool - yowtoa`.

### Bước 2: Cấu hình App Client

Trong User Pool, tạo ứng dụng `CloudManga-Web` với các thiết lập:

| Thành phần | Cấu hình |
|---|---|
| **Application type** | Single-page application (SPA) |
| **Authentication** | Authorization Code Flow với PKCE |
| **Callback URL** | `http://localhost:5500/` |
| **Production Callback URL** | `https://gggiang4689.github.io/CloudManga/` |
| **Sign-out URL** | Các địa chỉ tương ứng của ứng dụng |

Cấu hình **Cognito Managed Login** để cung cấp giao diện đăng nhập và đăng ký tài khoản.

### Bước 3: Kết nối frontend

Cập nhật các thông tin sau trong `config.js`:

- **Cognito Domain**
- **App Client ID**
- **Redirect URI**
- **OAuth Scopes**

Frontend chuyển hướng đến **Cognito Managed Login** khi người dùng chọn đăng nhập. 
Sau khi xác thực thành công, Cognito chuyển hướng về ứng dụng và cung cấp mã ủy quyền để trao đổi lấy token.

<div style="text-align: center;">
  <img src="/images/5.6.1.png"
       alt="Giao diện đăng nhập Amazon Cognito"
       style="width: 50%; height: auto;">

  <p><em>Hình 5.6.1. Giao diện đăng nhập CloudManga bằng Amazon Cognito.</em></p>
</div>

## Kết quả

**Amazon Cognito** được tích hợp vào **CloudManga**, hỗ trợ đăng ký, đăng nhập và đăng xuất.

**Access Token** được sử dụng để xác thực các yêu cầu API cần quyền người dùng.