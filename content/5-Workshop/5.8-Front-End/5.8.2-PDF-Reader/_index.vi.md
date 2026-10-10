---
title: "Xây dựng trình đọc truyện"
weight: 2
chapter: false
pre: "<b>5.8.2. </b>"
---

## Mục tiêu

Xây dựng chức năng đọc truyện trực tuyến bằng cách hiển thị các trang ảnh **JPG** được lưu trên **Amazon S3**.

## Các bước thực hiện

### Bước 1: Thiết kế trang đọc truyện

Sử dụng hai file:

- **reader.html:** Xây dựng giao diện đọc truyện.
- **reader.js:** Xử lý tải và hiển thị nội dung chương.

Giao diện được thiết kế để các trang ảnh hiển thị liên tiếp theo chiều dọc.

### Bước 2: Kết nối API đọc chương

Khi chọn chương, frontend gửi yêu cầu:

```text
GET /chapter?mangaId=1&chapter=1
```

**AWS Lambda** truy vấn danh sách trang JPG trong **Amazon S3** và tạo **Presigned URL** cho từng ảnh.

Frontend nhận danh sách URL, sau đó tải và hiển thị ảnh theo thứ tự.

### Bước 3: Kiểm thử

Mở một chương truyện và kiểm tra:

- Các trang ảnh tải thành công.
- Thứ tự trang được hiển thị chính xác.
- Giao diện có thể cuộn để đọc nội dung.

<div style="text-align: center;">
  <img src="/images/5.8.2.png"
       alt="Trình đọc truyện CloudManga"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.8.2. Chức năng đọc truyện trực tuyến của CloudManga.</em></p>
</div>

## Kết quả

Hoàn thành trình đọc truyện bằng ảnh **JPG**. Nội dung được tải từ **Amazon S3** thông qua các **Presigned URL** có thời hạn.