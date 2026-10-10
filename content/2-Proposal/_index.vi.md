---
title: "Đề xuất"
weight: 2
chapter: false
pre: "<b>2. </b>"
---

## First Cloud AI Journey – Capstone Project CloudManga

---

# 1. Tóm tắt

**CloudManga** là dự án xây dựng ứng dụng web đọc truyện tranh trên nền tảng điện toán đám mây **Amazon Web Services (AWS)**.

Ứng dụng cho phép người dùng xem danh sách truyện, tìm kiếm, xem thông tin chi tiết và đọc các chương truyện mẫu dưới dạng PDF. Ngoài ra, hệ thống được thiết kế để hỗ trợ đăng ký, đăng nhập và đánh giá truyện.

CloudManga sử dụng **HTML, CSS, JavaScript** cho giao diện, kết hợp với các dịch vụ **AWS** như **Amazon S3, AWS Lambda, Amazon API Gateway, Amazon Cognito** và **Amazon DynamoDB**.

Mục tiêu chính của dự án là tìm hiểu cách xây dựng ứng dụng web theo kiến trúc **Serverless**, giảm nhu cầu quản lý máy chủ và tận dụng các dịch vụ được quản lý của **AWS**.

---

# 2. Vấn đề và giải pháp

## Vấn đề

- Các ứng dụng đọc truyện trực tuyến cần quản lý nhiều đầu truyện, chương truyện và thông tin người dùng.
- Việc triển khai toàn bộ hệ thống trên máy chủ truyền thống có thể đòi hỏi cấu hình máy chủ, bảo trì hệ điều hành, quản lý cơ sở dữ liệu và theo dõi tài nguyên.
- Ngoài ra, ứng dụng cần có cơ chế xác thực người dùng để quản lý các chức năng tương tác như đánh giá và nhận xét truyện.

## Giải pháp

**CloudManga** sử dụng kiến trúc Serverless nhằm đơn giản hóa quá trình triển khai:

- **Amazon S3** lưu trữ thông tin truyện, ảnh bìa và các chương PDF mẫu.
- **AWS Lambda** xử lý yêu cầu từ ứng dụng.
- **Amazon API Gateway** cung cấp các endpoint cho frontend.
- **Amazon Cognito** quản lý tài khoản và xác thực người dùng.
- **Amazon DynamoDB** lưu trữ điểm đánh giá và nhận xét.
- **Amazon CloudWatch** hỗ trợ theo dõi quá trình thực thi Lambda.
- **GitHub Pages** được sử dụng để triển khai giao diện web tĩnh.

Dự án ưu tiên kiến trúc đơn giản, chi phí thấp và phù hợp với phạm vi học tập.

---

# 3. Kiến trúc giải pháp

## Kiến trúc tổng thể CloudManga

![Sơ đồ kiến trúc CloudManga](/images/CloudManga-architecture.png)

Hệ thống được chia thành ba thành phần chính:

1. **Frontend:** Giao diện người dùng được xây dựng bằng HTML, CSS và JavaScript.
2. **Backend:** Amazon API Gateway kết hợp AWS Lambda để tiếp nhận và xử lý yêu cầu.
3. **Lưu trữ và xác thực:** Amazon S3 lưu nội dung truyện, DynamoDB lưu đánh giá và Cognito quản lý tài khoản.

Các dịch vụ được kết nối thông qua API nhằm hạn chế việc frontend truy cập trực tiếp vào dữ liệu riêng tư.

## Luồng xử lý yêu cầu

![Luồng hoạt động CloudManga](/images/CloudManga-workflow.png)

Quy trình hoạt động dự kiến:

1. Người dùng truy cập website CloudManga.
2. Frontend gửi yêu cầu đến Amazon API Gateway.
3. API Gateway gọi AWS Lambda để lấy danh sách truyện.
4. Lambda đọc dữ liệu JSON từ Amazon S3.
5. Kết quả được trả về frontend để hiển thị.
6. Người dùng đăng nhập thông qua Amazon Cognito.
7. Người dùng đã xác thực có thể gửi đánh giá truyện.
8. Lambda lưu thông tin đánh giá vào Amazon DynamoDB.

## Các dịch vụ AWS sử dụng

| Dịch vụ AWS | Vai trò |
|---|---|
| Amazon S3 | Lưu dữ liệu truyện, ảnh bìa và PDF |
| AWS Lambda | Xử lý nghiệp vụ ứng dụng |
| Amazon API Gateway | Cung cấp API cho frontend |
| Amazon Cognito | Đăng ký và xác thực người dùng |
| Amazon DynamoDB | Lưu điểm đánh giá và nhận xét |
| AWS IAM | Quản lý quyền truy cập |
| Amazon CloudWatch | Theo dõi log và lỗi |
| AWS Budgets | Kiểm soát chi phí |

---

# 4. Triển khai kỹ thuật

## Các chức năng chính

| Chức năng | Mô tả |
|---|---|
| Trang chủ | Hiển thị danh sách truyện |
| Tìm kiếm | Tìm kiếm truyện theo tên |
| Chi tiết truyện | Xem thông tin và danh sách chương |
| Đọc truyện | Hiển thị chương PDF mẫu |
| Đăng ký và đăng nhập | Xác thực tài khoản qua Cognito |
| Đánh giá truyện | Chấm điểm từ 1 đến 5 sao |
| Nhận xét | Gửi và xem đánh giá của người dùng |

## Các API dự kiến

| Phương thức | Endpoint | Chức năng |
|---|---|---|
| GET | `/manga` | Lấy danh sách truyện |
| GET | `/manga/{id}` | Lấy thông tin chi tiết |
| GET | `/manga/{id}/chapters` | Lấy danh sách chương |
| GET | `/reviews/{mangaId}` | Xem đánh giá |
| POST | `/reviews` | Thêm đánh giá |
| PUT | `/reviews/{mangaId}` | Cập nhật đánh giá |
| DELETE | `/reviews/{mangaId}` | Xóa đánh giá |

Trong đó, endpoint `GET /manga` đã được triển khai và kiểm thử trong quá trình thực hành AWS Lambda và API Gateway.

Các endpoint còn lại thuộc phạm vi thiết kế và sẽ được kiểm thử khi triển khai hoàn chỉnh.

## Lưu trữ dữ liệu

**Amazon S3 Bucket** `cloudmanga-storage-2026` lưu dữ liệu truyện, được cấu hình chặn truy cập công khai.

Các đánh giá dự kiến được lưu trong bảng **DynamoDB** `CloudManga-Reviews`, sử dụng mã truyện và mã người dùng để phân biệt đánh giá.

Hệ thống xác thực dự kiến sử dụng **Amazon Cognito User Pool** và **JWT** để bảo vệ các yêu cầu thêm, sửa và xóa đánh giá.

---

# 5. Lộ trình thực hiện

| Giai đoạn | Nội dung | Kết quả |
|---|---|---|
| 1 | Tìm hiểu AWS, IAM, VPC, EC2, S3 | Hoàn thành LAB |
| 2 | Tạo S3, Lambda, API Gateway | API danh sách truyện hoạt động |
| 3 | Thực hành Docker, ECS, ALB, Auto Scaling | Hoàn thành LAB |
| 4 | Phát triển giao diện CloudManga | Đang triển khai |
| 5 | Tích hợp Cognito, DynamoDB và PDF Reader | Theo kế hoạch |
| 6 | Kiểm thử, xuất bản và hoàn thiện tài liệu | Theo kế hoạch |

---

# 6. Rủi ro và giới hạn

- Dự án được thực hiện trong thời gian ngắn nên ưu tiên các chức năng cơ bản.
- Dữ liệu truyện ban đầu chỉ có số lượng nhỏ để phục vụ kiểm thử.
- Việc tích hợp nhiều dịch vụ AWS có thể phát sinh lỗi phân quyền IAM hoặc cấu hình CORS.
- Một số dịch vụ có thể phát sinh chi phí tùy theo mức sử dụng.
- Hệ thống chưa được kiểm thử tải lớn hoặc đánh giá khả năng vận hành trong môi trường thực tế.

---

# 7. Hướng phát triển

- Bổ sung trang quản trị nội dung truyện.
- Hỗ trợ tìm kiếm nâng cao và lọc theo thể loại.
- Xây dựng danh sách truyện yêu thích.
- Lưu lịch sử đọc truyện.
- Cải thiện giao diện trên thiết bị di động.
- Bổ sung cơ chế lưu trữ và phân phối nội dung hiệu quả hơn.
- Nghiên cứu ứng dụng AI để gợi ý truyện phù hợp với sở thích người dùng.


