---
title: "Lambda xử lý đánh giá"
weight: 2
chapter: false
pre: "<b>5.7.2. </b>"
---

## Mục tiêu

Xây dựng **AWS Lambda** để đọc và ghi dữ liệu đánh giá trong **Amazon DynamoDB**.

## Các bước thực hiện

### Bước 1: Tạo IAM Role

Truy cập **AWS IAM → Roles → Create role**.

Tạo Role:

`CloudManga-Reviews-Role`

Gắn policy **AWSLambdaBasicExecutionRole** và cấp các quyền **dynamodb:Query**, **dynamodb:PutItem** đối với bảng `CloudManga-Reviews`.

### Bước 2: Tạo Lambda

1. Truy cập **AWS Lambda → Create function**.
2. Chọn **Author from scratch**.
3. Nhập tên `CloudManga-Reviews`.
4. Chọn Runtime **Python 3.x**.
5. Chọn Execution Role `CloudManga-Reviews-Role`.
6. Chọn **Create function**.

### Bước 3: Xây dựng chức năng

Lambda sử dụng thư viện **Boto3** để thực hiện:

- **GET:** Truy vấn danh sách đánh giá theo `mangaId`, tính điểm trung bình và số lượng đánh giá.
- **POST:** Kiểm tra điểm số, nhận xét và danh tính người dùng từ thông tin xác thực do API Gateway chuyển đến.
- **PutItem:** Lưu hoặc cập nhật đánh giá trong **DynamoDB**.

Cấu trúc khóa `mangaId` và `userId` giúp quản lý một bản ghi đánh giá cho mỗi người dùng đối với từng truyện.

### Bước 4: Kiểm thử

Sử dụng chức năng **Test** của Lambda để kiểm tra việc truy vấn và ghi dữ liệu.

Kiểm tra kết quả thực thi và log trong **Amazon CloudWatch**.

## Kết quả

Hàm **CloudManga-Reviews** có khả năng đọc, lưu và cập nhật đánh giá trong **Amazon DynamoDB**.