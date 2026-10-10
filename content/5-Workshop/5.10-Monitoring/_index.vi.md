---
title: "Giám sát hệ thống"
weight: 10
chapter: false
pre: "<b>5.10. </b>"
---

## Quy trình giám sát

Hệ thống **CloudManga** sử dụng **Amazon CloudWatch** để ghi nhận và theo dõi hoạt động của các hàm **AWS Lambda**.

Quy trình giám sát được thực hiện như sau:

1. Truy cập **AWS Management Console → CloudWatch → Log groups**.
2. Chọn Log Group tương ứng với các hàm `CloudManga-GetManga`, `CloudManga-GetChapter` hoặc `CloudManga-Reviews`.
3. Mở **Log streams** để kiểm tra lịch sử thực thi và thông báo lỗi.
4. Theo dõi các chỉ số **Invocations**, **Errors** và **Duration** trong phần **Monitoring** của Lambda.
5. Kiểm tra và điều chỉnh cấu hình khi phát hiện lỗi trong quá trình xử lý API.

<div style="text-align: center;">
  <img src="/images/5.10.1.png"
       alt="Giám sát Lambda bằng Amazon CloudWatch"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.10.1. Theo dõi hoạt động AWS Lambda bằng Amazon CloudWatch.</em></p>
</div>

## Giới hạn

Hệ thống hiện sử dụng các chức năng giám sát cơ bản của **Amazon CloudWatch**. Chưa triển khai hệ thống cảnh báo tự động hoặc bảng điều khiển giám sát chuyên biệt.

## Kết quả

**Amazon CloudWatch** hỗ trợ kiểm tra lịch sử thực thi, phát hiện lỗi và theo dõi hiệu suất của các hàm **AWS Lambda**, phục vụ quá trình vận hành và kiểm thử **CloudManga**.