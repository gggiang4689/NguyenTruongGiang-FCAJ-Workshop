---
title: "Điều kiện chuẩn bị"
weight: 2
chapter: false
pre: "<b>5.2. </b>"
---

## Mục tiêu

Chuẩn bị tài khoản **AWS**, môi trường lập trình và các công cụ cần thiết để triển khai ứng dụng **CloudManga** theo kiến trúc **Serverless**.

---

## 1. Tài khoản AWS

Truy cập [AWS Management Console](https://console.aws.amazon.com/) và đăng nhập bằng tài khoản AWS.

Lựa chọn Region **Asia Pacific (Singapore) – ap-southeast-1** để triển khai các dịch vụ.

<div style="text-align: center;">
  <img src="/images/week1-01.png"
       alt="Giao diện AWS Management Console"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.2.1 Giao diện AWS Management Console</em></p>
</div>


Đảm bảo tài khoản có quyền sử dụng các dịch vụ:

- **Amazon S3:** Lưu trữ dữ liệu truyện và hình ảnh.
- **AWS Lambda:** Xử lý các yêu cầu từ ứng dụng.
- **Amazon API Gateway:** Cung cấp API kết nối frontend và backend.
- **Amazon Cognito:** Xác thực người dùng.
- **Amazon DynamoDB:** Lưu trữ đánh giá.
- **AWS IAM:** Quản lý quyền truy cập.
- **Amazon CloudWatch:** Theo dõi log hệ thống.

---

## 2. Kiểm tra chi phí AWS

Truy cập **Billing and Cost Management** để kiểm tra **AWS Credits** và **AWS Budgets**.

<div style="text-align: center;">
  <img src="/images/week1-02.png"
       alt="Kiểm tra ngân sách"
       style="width: 90%; height: auto;">

  <p><em>Hình 5.2.2 Kiểm tra ngân sách AWS</em></p>
</div>

Việc theo dõi chi phí giúp hạn chế phát sinh phí ngoài dự kiến trong quá trình triển khai và kiểm thử.

## 3. Công cụ phát triển

| Công cụ | Mục đích |
|---|---|
| **Visual Studio Code** | Viết và quản lý mã nguồn |
| **HTML, CSS, JavaScript** | Phát triển giao diện CloudManga |
| **Python** | Phát triển Lambda và chạy HTTP Server cục bộ |
| **Google Chrome** | Kiểm thử giao diện và API |
| **GitHub** | Lưu trữ mã nguồn và triển khai GitHub Pages |

Các công cụ có thể tải tại:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Python](https://www.python.org/downloads/)
- [GitHub](https://github.com/)

Để chạy website trong môi trường phát triển, mở Terminal tại thư mục dự án và thực hiện:

```powershell
python -m http.server 5500
```

Truy cập địa chỉ:

`http://localhost:5500/`

## 4. Chuẩn bị dữ liệu

Dữ liệu được tổ chức trong **Amazon S3** theo cấu trúc:

```text
cloudmanga-storage-2026/
├── covers/
│   └── ...
└── manga/
    ├── manga.json
    ├── 1/
    │   └── chapter-01/
    │       ├── 001.jpg
    │       └── 002.jpg
    └── ...
```

Trong đó:

- **covers/**: Lưu ảnh bìa.
- **manga.json**: Lưu thông tin truyện.
- **chapter-01/**: Lưu các trang JPG của chương.

Dữ liệu ảnh sử dụng cho bản trình diễn cần có quyền sử dụng phù hợp.

## 5. Kết quả

Hoàn tất các điều kiện cần thiết để triển khai **CloudManga**, bao gồm tài khoản AWS, Region Singapore, môi trường lập trình, công cụ kiểm thử và cấu trúc dữ liệu dự kiến.

Các bước tạo tài nguyên và cấu hình dịch vụ sẽ được thực hiện trong những phần tiếp theo.