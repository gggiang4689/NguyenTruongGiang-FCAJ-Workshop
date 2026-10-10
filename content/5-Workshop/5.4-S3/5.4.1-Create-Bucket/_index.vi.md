---
title: "Tạo S3 Bucket"
weight: 1
chapter: false
pre: "<b>5.4.1. </b>"
---

## Mục tiêu

Tạo **Amazon S3 Bucket** để lưu trữ dữ liệu CloudManga và thiết lập quyền truy cập an toàn.

## Các bước thực hiện

### Bước 1: Truy cập Amazon S3

1. Đăng nhập **AWS Management Console**.
2. Tìm kiếm dịch vụ **S3**.
3. Chọn **Buckets → Create bucket**.

### Bước 2: Cấu hình Bucket

Nhập các thông tin:

| Thông số | Giá trị |
|---|---|
| **Bucket name** | `cloudmanga-storage-2026` |
| **AWS Region** | `ap-southeast-1` – Singapore |
| **Object Ownership** | ACLs disabled |
| **Block Public Access** | Block all public access |
| **Bucket Versioning** | Disable |

Giữ các thiết lập mặc định khác và chọn **Create bucket**.

<div style="text-align: center;">
  <img src="/images/5.4.1.png"
       alt="Cấu hình S3 Bucket CloudManga"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.4.1. Cấu hình Amazon S3 Bucket cho CloudManga.</em></p>
</div>

### Bước 3: Kiểm tra Bucket

Truy cập danh sách **S3 Buckets** và xác nhận Bucket `cloudmanga-storage-2026` đã được tạo.

Đảm bảo **Block all public access** vẫn được bật để ngăn việc công khai dữ liệu trực tiếp.

## Kết quả

Hoàn thành tạo Bucket **cloudmanga-storage-2026** tại Region Singapore, sẵn sàng lưu trữ dữ liệu cho CloudManga.