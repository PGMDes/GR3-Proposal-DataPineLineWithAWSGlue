---
title: "Đánh giá rủi ro"
date: "2025-11-09"
weight: 8
chapter: false
pre: " <b> 8. </b> "
---


## Ma trận rủi ro
- **Mất kết nối Internet**: Tác động trung bình, xác suất trung bình
- **Truy cập trái phép**: Tác động cao, xác suất thấp
- **Vượt ngân sách**: Tác động thấp, xác suất thấp
- **Lỗi gợi ý AI**: Tác động trung bình, xác suất thấp

## Chiến lược giảm thiểu
- **Mạng**: Tự động thử lại khi mất kết nối
- **Bảo mật**: Áp dụng MFA qua Cognito, WAF ngăn chặn tấn công
- **Chi phí**: Cảnh báo qua AWS Budgets, tối ưu tần suất truy vấn
- **AI**: Theo dõi và cập nhật mô hình Personalize định kỳ

## Kế hoạch dự phòng
- Cho phép đặt sân tạm thời offline và đồng bộ khi có mạng
- Rollback CodePipeline nếu có lỗi triển khai hoặc vượt chi phí

## Kết quả kỳ vọng

### Cải tiến kỹ thuật
Ứng dụng cung cấp khả năng tìm kiếm và đặt sân theo thời gian thực, gợi ý cá nhân hóa và báo cáo trực quan giúp tối ưu hóa hoạt động cho cả người chơi và chủ sân.

### Giá trị dài hạn
Nền tảng có thể mở rộng sang các môn thể thao khác (tennis, bóng rổ, phòng gym), đóng vai trò như một mẫu khung cho các giải pháp thể thao thông minh dựa trên AWS Serverless và AI. Ngoài ra, đây là dự án thực hành lý tưởng cho sinh viên hoặc nhóm nghiên cứu muốn ứng dụng AWS trong việc phát triển hệ thống thông minh.