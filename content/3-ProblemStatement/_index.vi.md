---
title: "Tuyên bố vấn đề"
date: "2025-11-09"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---



## Vấn đề hiện tại
Việc tìm và đặt sân cầu lông hiện nay chủ yếu dựa vào liên hệ thủ công (số điện thoại hoặc mạng xã hội), lịch đặt sân không được cập nhật theo thời gian thực và thiếu độ phủ sóng của các sân làm gây trở ngại về ước tính quãng đường đến sân. Đồng thời, chủ sân gặp khó khăn trong việc quản lý, sắp xếp số lượng sân cũng như thống kê doanh thu không hiệu quả.

## Giải pháp
Trang web này mang lại quy trình tự động hóa cho việc tìm kiếm, đặt sân và quản lý hiệu quả cho chủ doanh nghiệp. 

Người dùng có thể tìm kiếm sân gần vị trí của mình thông qua Amazon Location Service, xem tình trạng sân theo thời gian thực trong Amazon DynamoDB và được gợi ý sân phù hợp qua Amazon Personalize. 

Chủ sân có thể đăng ký và cập nhật thông tin sân, nhận email xác nhận đặt sân qua Amazon SES và thống kê doanh thu qua thông qua bảng điều khiển tùy chỉnh (Custom Dashboard) được xây dựng bằng AWS Amplify, Lambda, và biểu đồ Chart.js từ dữ liệu trong DynamoDB/S3. Giao diện web được triển khai bằng AWS Amplify và quản lý người dùng qua Amazon Cognito.

## Lợi ích và hoàn vốn đầu tư (ROI)
+ **Đối với người chơi**: dễ dàng tìm và đặt sân phù hợp chỉ trong vài giây, nhận gợi ý cá nhân hóa dựa trên hành vi và vị trí, đồng thời nhận email xác nhận tự động. Thời gian tìm sân giảm 90% (từ 30 phút còn 3 phút), và thời gian xác nhận đặt sân rút ngắn từ 2–24 giờ xuống chỉ còn 5 phút.

+ **Đối với chủ sân**: quản lý sân, lịch và người đặt tự động thông qua dashboard trung tâm, giảm 80% thời gian thao tác thủ công. Hệ thống cung cấp báo cáo doanh thu, lượt đặt và đánh giá trung bình trực quan, hỗ trợ ra quyết định dựa trên dữ liệu.

+ **Đối với nhóm phát triển**: Hệ thống hoàn toàn không máy chủ (serverless), chi phí vận hành cực thấp (<1 USD/tháng ở giai đoạn đầu, ước tính $8–15/tháng sau Free Tier). Hệ thống vừa là giải pháp thực tế, vừa là môi trường học tập giàu giá trị cung cấp dữ liệu thật phục vụ nghiên cứu AI, NLP tiếng Việt và mô hình gợi ý.