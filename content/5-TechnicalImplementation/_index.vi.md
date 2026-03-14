---
title: "Triển khai kỹ thuật"
date: "2025-11-09"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---



## Các giai đoạn triển khai
Dự án được chia thành 4 giai đoạn chính:
- **Nghiên cứu và thiết kế kiến trúc**: Lên sơ đồ hệ thống AWS Serverless, xác định quy trình đặt sân và luồng dữ liệu (Tuần 1).
- **Phát triển và kiểm thử**: Xây dựng API Gateway + Lambda, tích hợp DynamoDB và Cognito, kiểm thử chức năng (Tuần 2-3).
- **Phân tích**: Thêm gợi ý từ Personalize, hiển thị dữ liệu bằng Dashboard (Tuần 4).
- **Triển khai và tối ưu**: Sử dụng Amplify CI/CD để triển khai tự động, thiết lập CloudWatch và EventBridge để giám sát (Tuần 5).

## Yêu cầu kỹ thuật
- **Frontend**: ReactJS / Next.js (AWS Amplify Hosting)
- **Backend**: AWS Lambda (Node.js hoặc Python) + Amazon API Gateway
- **Database**: Amazon DynamoDB (lưu người dùng, sân, lịch đặt, rating; hỗ trợ truy vấn Geo qua DynamoDB Geo Library hoặc AWS Location Service)
- **AI Integration**: Amazon Personalize (phân tích hành vi và đánh giá để gợi ý sân phù hợp)
- **Auth & Security**: Amazon Cognito (đăng nhập/xác thực), AWS IAM (phân quyền), AWS KMS (mã hóa dữ liệu), AWS WAF (chống tấn công web)
- **Email**: Amazon SES (gửi xác nhận đặt sân, thông báo, nhắc lịch tự động)
- **Analytics**: Custom Dashboard (trực quan hóa doanh thu, lượt đặt và đánh giá từ dữ liệu DynamoDB hoặc S3, hiển thị qua AWS Amplify + Lambda + Chart.js).
- **Automation**: Amazon EventBridge (Scheduler) tự động hóa nhắc lịch, cập nhật dữ liệu gợi ý và dọn dẹp dữ liệu cũ
- **Maps API**: AWS Location Service hoặc Google Maps / Places / Distance Matrix (tìm sân gần, hiển thị bản đồ và chỉ đường)