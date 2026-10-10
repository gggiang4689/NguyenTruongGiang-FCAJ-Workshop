---
title: "Kiểm thử hệ thống"
weight: 11
chapter: false
pre: "<b>5.11. </b>"
---

## Quy trình kiểm thử

Quá trình kiểm thử **CloudManga** được thực hiện trực tiếp trên trình duyệt nhằm kiểm tra khả năng hoạt động của frontend và các dịch vụ backend **AWS**.

Các chức năng được kiểm tra bao gồm:

1. Truy cập website thông qua **GitHub Pages**.
2. Kiểm tra khả năng tải danh sách truyện và ảnh bìa từ **Amazon S3**.
3. Thử nghiệm chức năng tìm kiếm và xem chi tiết truyện.
4. Kiểm tra việc tải các trang JPG thông qua **AWS Lambda** và **Amazon API Gateway**.
5. Thử nghiệm đăng nhập, đăng xuất bằng **Amazon Cognito**.
6. Kiểm tra chức năng xem và gửi đánh giá thông qua **Amazon DynamoDB**.

## Kết quả kiểm thử

| Chức năng | Kết quả |
|---|---|
| Truy cập website | Thành công |
| Hiển thị danh sách truyện | Thành công |
| Tìm kiếm và xem chi tiết | Thành công |
| Đọc chương truyện | Thành công |
| Đăng nhập và đăng xuất | Thành công |
| Hiển thị đánh giá | Thành công |
| Gửi đánh giá khi đăng nhập | Thành công |

Website triển khai:

[https://gggiang4689.github.io/CloudManga/](https://gggiang4689.github.io/CloudManga/)

<div style="text-align: center;">
  <img src="/images/5.11.1.png"
       alt="Kiểm thử website CloudManga"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.11.1. Kiểm thử các chức năng của CloudManga trên trình duyệt.</em></p>
</div>

## Giới hạn

Quá trình kiểm thử được thực hiện thủ công trên trình duyệt. Hệ thống chưa triển khai **Automated Testing** hoặc kiểm thử hiệu năng với số lượng lớn người dùng đồng thời.

## Kết quả

Các chức năng chính của **CloudManga** đã được triển khai và kiểm tra ở mức cơ bản. Giao diện có thể truy xuất dữ liệu từ **AWS**, hỗ trợ đọc truyện và xác thực người dùng thông qua **Amazon Cognito**.

Việc kiểm thử bổ sung trên website công khai giúp xác nhận tính ổn định của chức năng đánh giá trước khi nghiệm thu.