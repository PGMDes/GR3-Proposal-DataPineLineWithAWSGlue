---
title: "Kiến trúc giải pháp"
date: "2025-11-09"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

Nền tảng áp dụng kiến trúc AWS Serverless Data Pipeline giúp vận hành ổn định, tự động hóa hoàn toàn luồng công việc và tối ưu hóa chi phí dựa trên lưu lượng dữ liệu thực tế. Toàn bộ dữ liệu thô từ bộ hồ sơ Yellow Taxi Trip Records được lưu trữ tập trung tại Amazon S3, đóng vai trò là Data Lake bền vững. Quy trình xử lý và luân chuyển dữ liệu được điều phối linh hoạt thông qua các hàm AWS Lambda, đảm bảo logic nghiệp vụ được thực thi tách biệt và hiệu quả.

Quá trình làm sạch và chuẩn hóa dữ liệu được thực hiện tự động bởi AWS Glue DataBrew thông qua các Recipe Jobs, giúp biến đổi các trường dữ liệu phức tạp trong Data Dictionary thành thông tin có cấu trúc. Dữ liệu sau xử lý được lưu trữ tại Amazon Redshift, tạo nền tảng kho dữ liệu (Data Warehouse) hiệu năng cao cho các truy vấn phân tích quy mô lớn.

Hệ thống Custom Dashboard trên AWS QuickSight sẽ trực quan hóa các chỉ số vận hành như xu hướng di chuyển, mật độ khách hàng và doanh thu theo thời gian thực cho các nhà quản lý vận tải. Toàn bộ hệ thống được giám sát chặt chẽ qua Amazon CloudWatch và tự động hóa quy trình kích hoạt (trigger) theo lịch trình nhờ Amazon EventBridge.

![Kiến trúc](/images/2-Proposal/diagram-architecture-01.jpg)

## Dịch vụ AWS sử dụng
- **AWS QuickSight**: Cung cấp nền tảng Business Intelligence (BI) để trực quan hóa dữ liệu thông qua các dashboard tương tác, giúp phân tích xu hướng chuyến đi và doanh thu taxi.
- **AWS Lambda**: Xử lý logic nghiệp vụ, trích xuất dữ liệu (Extract) từ nguồn và điều phối luồng công việc giữa các dịch vụ trong pipeline mà không cần quản lý máy chủ.
- **AWS Redshift**: Kho dữ liệu (Data Warehouse) hiệu năng cao theo mô hình Serverless, cho phép truy vấn SQL phức tạp trên khối lượng lớn dữ liệu hành trình taxi với tốc độ nhanh chóng.
- **AWS S3**: Đóng vai trò là trung tâm lưu trữ dữ liệu (Data Lake), lưu giữ an toàn cả dữ liệu thô (Raw) và dữ liệu đã qua xử lý (Processed) với độ bền bỉ cao.
- **AWS EventBridge**: Công cụ lập lịch và điều phối hướng sự kiện (Event-driven), tự động kích hoạt pipeline xử lý dữ liệu hàng ngày theo khung giờ cố định.
- **AWS Glue DataBrew (Recipe Jobs)**: Dịch vụ chuẩn bị dữ liệu trực quan, tự động hóa việc làm sạch và chuyển đổi (Transformation) dữ liệu Taxi dựa trên các Recipe đã được thiết kế sẵn.
