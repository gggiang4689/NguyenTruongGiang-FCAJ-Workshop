---
title: "Tải dữ liệu lên S3"
weight: 2
chapter: false
pre: "<b>5.4.2. </b>"
---

## Mục tiêu

Tải dữ liệu truyện và hình ảnh lên **Amazon S3**, phục vụ chức năng hiển thị danh sách truyện và đọc chương của **CloudManga**.

## Các bước thực hiện

### Bước 1: Chuẩn bị dữ liệu

Dữ liệu được tổ chức theo cấu trúc:

```text
cloudmanga-storage-2026/
├── covers/
│   ├── berserk.jpg
│   ├── fire punch.jpg
│   ├── gotoubun.jpg
│   └── ...
└── manga/
    ├── manga.json
    ├── 1/
    │   ├── chapter-01/
    │   │   ├── 001.jpg
    │   │   └── 002.jpg
    │   │       ...
    │   └── chapter-02/
    └── ...
```

Trong đó:

- **covers/**: Lưu ảnh bìa truyện.
- **manga/manga.json**: Lưu thông tin tên truyện, thể loại và số chương.
- **manga/{id}/chapter-XX/**: Lưu các trang JPG theo từng chương.

### Bước 2: Tải dữ liệu lên S3

1. Truy cập **Amazon S3 → Buckets**.
2. Chọn Bucket `cloudmanga-storage-2026`.
3. Chọn **Upload → Add files / Add folder**.
4. Tải các file lên đúng vị trí theo cấu trúc đã chuẩn bị.
5. Chọn **Upload** để hoàn tất.

### Bước 3: Kiểm tra dữ liệu

Kiểm tra các file đã xuất hiện tại đúng đường dẫn trong Bucket.

<div style="text-align: center;">
  <img src="/images/5.4.2.png"
       alt="Dữ liệu CloudManga trong Amazon S3"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.4.2. Các thư mục và dữ liệu CloudManga trên Amazon S3.</em></p>
</div>

### Bước 4: Kiểm tra quyền truy cập

Giữ **S3 Bucket** ở chế độ riêng tư và không bật Public Access.

Quyền đọc dữ liệu sẽ được cấp cho **AWS Lambda** thông qua **IAM Role** ở phần tiếp theo. Lambda sử dụng **Presigned URL** để cung cấp đường dẫn truy cập ảnh có thời hạn cho frontend.

## Kết quả

Dữ liệu truyện và hình ảnh đã được lưu trên **Amazon S3**, sẵn sàng kết nối với **AWS Lambda** để xây dựng API cho CloudManga.