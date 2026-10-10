---
title: "Cấu hình IAM Role"
weight: 1
chapter: false
pre: "<b>5.5.1. </b>"
---

## Mục tiêu

Tạo **IAM Role** cho phép **AWS Lambda** truy cập dữ liệu trong **Amazon S3** và ghi log vào **Amazon CloudWatch**.

## Các bước thực hiện

### Bước 1: Tạo IAM Role

1. Truy cập **AWS Management Console → IAM → Roles**.
2. Chọn **Create role**.
3. Tại **Trusted entity type**, chọn **AWS service**.
4. Tại **Use case**, chọn **Lambda**.
5. Gắn policy **AWSLambdaBasicExecutionRole** để Lambda có quyền ghi log.
6. Đặt tên Role: `CloudJourney-Lambda-Role`.
7. Chọn **Create role**.

### Bước 2: Cấp quyền đọc dữ liệu S3

Mở Role vừa tạo, chọn **Add permissions → Create inline policy**.

Chuyển sang chế độ **JSON** và nhập:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::cloudmanga-storage-2026/manga/*",
        "arn:aws:s3:::cloudmanga-storage-2026/covers/*"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket"
      ],
      "Resource": "arn:aws:s3:::cloudmanga-storage-2026",
      "Condition": {
        "StringLike": {
          "s3:prefix": [
            "manga/*"
          ]
        }
      }
    }
  ]
}
```

Đặt tên Policy:

`CloudManga-S3-ReadPolicy`

Chọn **Create policy**.

### Bước 3: Kiểm tra quyền

Xác nhận **IAM Role** có các quyền:

- **AWSLambdaBasicExecutionRole:** Ghi log.
- **CloudManga-S3-ReadPolicy:** Đọc file JSON, ảnh bìa và danh sách trang truyện trên S3.

## Kết quả

**IAM Role** đã được cấu hình để Lambda truy cập các tài nguyên cần thiết theo nguyên tắc **Least Privilege**.