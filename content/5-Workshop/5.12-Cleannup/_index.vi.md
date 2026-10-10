---
title: "Dọn dẹp tài nguyên"
weight: 12
chapter: false
pre: "<b>5.12. </b>"
---

## Mục tiêu

Kiểm tra và dọn dẹp các tài nguyên **AWS** không còn cần thiết sau quá trình thực hành, nhằm tối ưu chi phí và quản lý tài nguyên hiệu quả.

## Quy trình dọn dẹp

Các bước kiểm tra và dọn dẹp tài nguyên được thực hiện như sau:

1. **Amazon EC2:** Dừng hoặc xóa các Instance không còn sử dụng.
2. **Amazon ECS:** Dừng các Task, Service và xóa Cluster thử nghiệm nếu không còn cần thiết.
3. **Elastic Load Balancing:** Xóa **Application Load Balancer** và Target Group không sử dụng.
4. **EC2 Auto Scaling:** Xóa các Auto Scaling Group và tài nguyên liên quan sau khi kết thúc bài thực hành.
5. **Amazon CloudWatch:** Kiểm tra Log Groups và thời gian lưu trữ log.
6. **AWS Billing:** Kiểm tra chi phí phát sinh trong **Billing and Cost Management**.

Các tài nguyên đang phục vụ website **CloudManga** gồm **Amazon S3**, **AWS Lambda**, **Amazon API Gateway**, **Amazon Cognito** và **Amazon DynamoDB** được giữ lại để duy trì hoạt động của ứng dụng.

## Lưu ý

Việc xóa tài nguyên cần được kiểm tra kỹ để tránh ảnh hưởng đến hệ thống đang hoạt động.

Đặc biệt, việc xóa **S3 Bucket**, **DynamoDB Table** hoặc **Cognito User Pool** có thể làm mất dữ liệu và ảnh hưởng trực tiếp đến chức năng của CloudManga.

Ngoài ra, cần kiểm tra các tài nguyên có thể tiếp tục phát sinh chi phí như **NAT Gateway**, **Elastic IP**, **Load Balancer** và các tài nguyên lưu trữ không còn sử dụng.

## Kết quả

Các tài nguyên phục vụ bài thực hành riêng biệt được rà soát và dọn dẹp khi không còn cần thiết.

Các dịch vụ chính của **CloudManga** tiếp tục được duy trì để website hoạt động, đồng thời hạn chế chi phí phát sinh từ những tài nguyên thử nghiệm không sử dụng.