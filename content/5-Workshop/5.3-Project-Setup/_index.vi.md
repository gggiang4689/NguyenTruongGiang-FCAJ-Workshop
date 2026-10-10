---
title: "Chuẩn bị dự án"
weight: 3
chapter: false
pre: "<b>5.3. </b>"
---

## Mục tiêu

Chuẩn bị mã nguồn frontend, cấu trúc thư mục và môi trường phát triển cho ứng dụng **CloudManga**, trước khi kết nối với các dịch vụ **AWS**.

## 1. Tạo thư mục dự án

Tạo thư mục **CloudManga-Capstone** và mở bằng **Visual Studio Code**.

Cấu trúc mã nguồn của ứng dụng:

```text
CloudManga-Capstone/
├── index.html
├── style.css
├── app.js
├── config.js
├── detail.html
├── detail.js
├── reader.html
├── reader.js
└── reviews.js
```

Các thành phần chính:

- **index.html / app.js:** Trang chủ, danh sách truyện và tìm kiếm.
- **detail.html / detail.js:** Trang thông tin truyện và danh sách chương.
- **reader.html / reader.js:** Hiển thị các trang truyện dưới dạng ảnh JPG.
- **reviews.js:** Hiển thị và gửi đánh giá truyện.
- **style.css:** Thiết kế giao diện.
- **config.js:** Cấu hình địa chỉ API và **Amazon Cognito**.

## 2. Cấu hình kết nối AWS

File **config.js** được sử dụng để quản lý các thông tin kết nối giữa frontend và backend.

Những cấu hình chính bao gồm:

- **API Gateway Endpoint:** Địa chỉ API xử lý danh sách truyện, chương và đánh giá.
- **Amazon Cognito Domain:** Địa chỉ trang đăng nhập.
- **Cognito App Client ID:** Mã định danh ứng dụng.
- **Redirect URI:** Địa chỉ chuyển hướng sau khi đăng nhập hoặc đăng xuất.

Địa chỉ API được sử dụng:

```text
https://oo4qm8mooj.execute-api.ap-southeast-1.amazonaws.com/manga
```

Thông tin cấu hình cần được cập nhật sau khi hoàn thành bước tạo **Amazon API Gateway** và **Amazon Cognito**.

Các thông tin bí mật như **AWS Access Key** hoặc **Client Secret** không được lưu trong mã nguồn frontend công khai.

## 3. Chạy thử ứng dụng trên localhost

Mở Terminal tại thư mục **CloudManga-Capstone**, sau đó chạy lệnh:

```powershell
python -m http.server 5500
```

Truy cập địa chỉ:

```text
http://localhost:5500/
```

Kiểm tra khả năng hiển thị giao diện và hoạt động của các file **HTML**, **CSS**, **JavaScript**.

<div style="text-align: center;">
  <img src="/images/5.3.2.png"
       alt="Giao diện CloudManga trên localhost"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.3.2. Kiểm tra giao diện CloudManga trên localhost.</em></p>
</div>

Ở bước này, các chức năng cần dữ liệu từ **AWS** chỉ hoạt động đầy đủ sau khi backend được cấu hình.

## 4. Kết quả

Hoàn thành việc chuẩn bị cấu trúc dự án **CloudManga**, thiết lập các file frontend và môi trường kiểm thử cục bộ.

Mã nguồn sẵn sàng để kết nối với **Amazon S3**, **AWS Lambda**, **Amazon API Gateway** và các dịch vụ AWS trong những bước triển khai tiếp theo.