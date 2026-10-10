---
title: "Tạo bảng DynamoDB"
weight: 1
chapter: false
pre: "<b>5.7.1. </b>"
---

## Mục tiêu

Sử dụng **Amazon DynamoDB** để lưu trữ điểm đánh giá và nhận xét của người dùng.

## Các bước thực hiện

### Bước 1: Tạo bảng

1. Truy cập **AWS Management Console → DynamoDB**.
2. Chọn **Tables → Create table**.
3. Nhập thông tin cấu hình:

| Thành phần | Giá trị |
|---|---|
| **Table name** | `CloudManga-Reviews` |
| **Partition key** | `mangaId` – String |
| **Sort key** | `userId` – String |
| **Capacity mode** | On-demand |

4. Chọn **Create table**.

### Bước 2: Kiểm tra bảng

Sau khi bảng chuyển sang trạng thái **Active**, mở mục **Explore table items** để kiểm tra dữ liệu.

Mỗi bản ghi chứa các thông tin chính:

- **mangaId:** Mã truyện.
- **userId:** Mã người dùng.
- **rating:** Điểm đánh giá từ 1 đến 5.
- **comment:** Nội dung nhận xét.
- **updatedAt:** Thời gian cập nhật, nếu được lưu.

<div style="text-align: center;">
  <img src="/images/5.7.1.png"
       alt="Bảng CloudManga-Reviews trên DynamoDB"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.7.1. Bảng CloudManga-Reviews trong Amazon DynamoDB.</em></p>
</div>

## Kết quả

Bảng **CloudManga-Reviews** được tạo thành công, sẵn sàng lưu dữ liệu đánh giá của ứng dụng.