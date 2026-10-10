---
title: "Tạo AWS Lambda"
weight: 2
chapter: false
pre: "<b>5.5.2. </b>"
---

## Mục tiêu

Sử dụng **AWS Lambda** để truy xuất dữ liệu từ **Amazon S3** và cung cấp thông tin truyện cho frontend.

## Các bước thực hiện

### Bước 1: Tạo Lambda lấy danh sách truyện

1. Truy cập **AWS Console → Lambda → Create function**.
2. Chọn **Author from scratch**.
3. Nhập Function name: `CloudManga-GetManga`.
4. Chọn Runtime **Python 3.x**.
5. Tại **Execution role**, chọn **Use an existing role**.
6. Chọn `CloudJourney-Lambda-Role`.
7. Nhấn **Create function**.

### Bước 2: Xây dựng chức năng xử lý

Hàm `CloudManga-GetManga` sử dụng thư viện **Boto3** để:

1. Đọc file `manga/manga.json` từ **Amazon S3**.
2. Chuyển dữ liệu JSON thành danh sách truyện.
3. Tạo **Presigned URL** cho ảnh bìa.
4. Trả kết quả dưới dạng JSON để frontend sử dụng.

### Bước 3: Tạo Lambda đọc chương

Tạo thêm Function:

`CloudManga-GetChapter`

Hàm thực hiện:

1. Nhận hai tham số `mangaId` và `chapter`.
2. Sử dụng **Boto3** truy vấn các ảnh JPG tương ứng trên S3.
3. Sắp xếp ảnh theo tên file.
4. Tạo **Presigned URL** cho từng trang.
5. Trả về danh sách URL để hiển thị trên trang đọc truyện.

### Bước 4: Kiểm thử Lambda

Tại trang quản lý Function, chọn **Test** để kiểm tra kết quả trả về.

<div style="text-align: center;">
  <img src="/images/5.5.1.png"
       alt="Kiểm thử AWS Lambda"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.5.1. Kiểm thử hàm AWS Lambda của CloudManga.</em></p>
</div>

Kiểm tra kết quả JSON và trạng thái thực thi thành công.

## Kết quả

Hai hàm **CloudManga-GetManga** và **CloudManga-GetChapter** đã được tạo để xử lý dữ liệu truyện trên **Amazon S3**.

Dữ liệu được trả về dưới dạng JSON, bao gồm các **Presigned URL** phục vụ hiển thị hình ảnh.