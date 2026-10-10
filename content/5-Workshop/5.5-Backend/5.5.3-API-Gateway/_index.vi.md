---
title: "Cấu hình API Gateway"
weight: 3
chapter: false
pre: "<b>5.5.3. </b>"
---

## Mục tiêu

Sử dụng **Amazon API Gateway** để cung cấp các API kết nối giao diện **CloudManga** với các hàm **AWS Lambda**.

## Các bước thực hiện

### Bước 1: Tạo HTTP API

1. Truy cập **AWS Console → API Gateway**.
2. Chọn **Create API → HTTP API → Build**.
3. Đặt tên API: `CloudManga-API`.
4. Lựa chọn Region **ap-southeast-1**.
5. Sử dụng Stage **$default**.
6. Hoàn thành quá trình tạo API.

### Bước 2: Tạo các API Route

Trong mục **Routes**, tạo các endpoint:

| Method | Route | Lambda |
|---|---|---|
| **GET** | `/manga` | `CloudManga-GetManga` |
| **GET** | `/chapter` | `CloudManga-GetChapter` |

Tại mục **Integrations**, liên kết mỗi Route với Function tương ứng.

### Bước 3: Cấu hình CORS

Trong mục **CORS**, cấu hình:

- **Allowed origins:** `http://localhost:5500` và `https://gggiang4689.github.io`
- **Allowed methods:** `GET`, `POST`, `OPTIONS`
- **Allowed headers:** `content-type`, `authorization`

Cấu hình này cho phép frontend trên localhost và **GitHub Pages** gửi yêu cầu đến API.

### Bước 4: Kiểm thử API

Sau khi cấu hình, địa chỉ API sử dụng trong dự án là:

```text
https://oo4qm8mooj.execute-api.ap-southeast-1.amazonaws.com
```

Kiểm thử API lấy danh sách truyện:

```text
https://oo4qm8mooj.execute-api.ap-southeast-1.amazonaws.com/manga
```

<div style="text-align: center;">
  <img src="/images/5.5.2.png"
       alt="Các Route trong API Gateway"
       style="width: 50%; height: auto;">

  <p><em>Hình 5.5.2. Các API Route được cấu hình trong Amazon API Gateway.</em></p>
</div>

### Bước 5: Kết nối frontend

Cập nhật địa chỉ API trong file **config.js** để frontend có thể gửi yêu cầu tới **Amazon API Gateway**.

Thực hiện kiểm thử trên localhost và xác nhận danh sách truyện được tải từ **Amazon S3**.

<div style="text-align: center;">
  <img src="/images/5.5.3.png"
       alt="CloudManga hiển thị dữ liệu từ AWS"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.5.3. Giao diện CloudManga nhận dữ liệu từ AWS.</em></p>
</div>

## Kết quả

**Amazon API Gateway** đã được kết nối với **AWS Lambda** để cung cấp API lấy danh sách truyện và đọc chương.

Frontend có thể nhận dữ liệu từ S3 thông qua hệ thống backend Serverless.