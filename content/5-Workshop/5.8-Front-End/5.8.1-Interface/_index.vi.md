---
title: "Xây dựng giao diện"
weight: 1
chapter: false
pre: "<b>5.8.1. </b>"
---

## Mục tiêu

Thiết kế giao diện **CloudManga** và hiển thị dữ liệu truyện lấy từ **Amazon API Gateway**.

## Các bước thực hiện

### Bước 1: Xây dựng trang chủ

Sử dụng các file:

- **index.html:** Xây dựng bố cục trang chủ.
- **style.css:** Thiết kế màu sắc, bố cục và giao diện.
- **app.js:** Xử lý hiển thị danh sách truyện và tìm kiếm.

Trang chủ được thiết kế với các thành phần chính: thanh điều hướng, ô tìm kiếm và danh sách truyện.

### Bước 2: Kết nối API

File **app.js** gửi yêu cầu đến endpoint:

```text
GET /manga
```

Dữ liệu trả về từ **AWS Lambda** được sử dụng để hiển thị tên truyện, thể loại, số chương và ảnh bìa.

Chức năng tìm kiếm được xử lý bằng **JavaScript** dựa trên danh sách truyện đã tải.

### Bước 3: Xây dựng trang chi tiết

Sử dụng **detail.html** và **detail.js** để hiển thị thông tin truyện cùng danh sách chương.

Khi chọn một chương, ứng dụng chuyển đến trang đọc truyện tương ứng.

<div style="text-align: center;">
  <img src="/images/5.8.1.png"
       alt="Giao diện trang chủ CloudManga"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.8.1. Giao diện trang chủ CloudManga.</em></p>
</div>

## Kết quả

Hoàn thành giao diện trang chủ, chức năng tìm kiếm và trang chi tiết truyện. Dữ liệu được truy xuất từ **Amazon S3** thông qua **API Gateway** và **AWS Lambda**.