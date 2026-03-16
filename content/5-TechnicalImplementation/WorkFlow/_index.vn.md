---
title: "Triển khai kỹ thuật"
date: "2025-11-09"
weight: 1
chapter: false
pre: " <b> 5. </b> "
---
# Workflow

![Kiến trúc](/images/2-Proposal/diagram-architecture-01.jpg)

## 1. Data Ingestion – Data Input → Amazon S3 (Raw Data)

Nguồn dữ liệu ban đầu là dataset Yellow Taxi Trips từ NYC Taxi and Limousine Commission.

| Field                 | Ý nghĩa               |
| --------------------- | --------------------- |
| VendorID              | ID hãng taxi          |
| tpep_pickup_datetime  | Thời gian đón khách   |
| tpep_dropoff_datetime | Thời gian trả khách   |
| passenger_count       | Số hành khách         |
| trip_distance         | Khoảng cách chuyến đi |
| PULocationID          | ID vị trí đón         |
| DOLocationID          | ID vị trí trả         |
| fare_amount           | Giá cước              |
| tip_amount            | Tiền tip              |
| total_amount          | Tổng tiền             |

Dữ liệu thô được upload vào bucket S3 Raw.

Ví dụ:

    s3://taxi-data-raw/yellow_tripdata_2024_01.parquet

    s3://taxi-data-raw/yellow_tripdata_2024_02.parquet

S3 đóng vai trò:
- Data Lake raw layer
- Lưu parquet / csv gốc
- Chưa xử lý

## 2. Event Detection – S3 → EventBridge
Khi có file mới trong bucket raw:

    PUT Object → S3 Event

event này được gửi tới Amazon EventBridge.

EventBridge phát hiện:

    ObjectCreated

Ví dụ event:
```
{
 "source": "aws.s3",
 "detail-type": "Object Created",
 "bucket": "taxi-data-raw",
 "object": "yellow_tripdata_2024_01.parquet"
}
```

## 3. EventBridge Trigger → Data Processing Workflow
EventBridge kích hoạt workflow xử lý dữ liệu.

Workflow orchestration nằm trong Step Functions.

Service orchestration giúp:
- Điều phối pipeline
- Retry khi lỗi
- Log trạng thái pipeline

## 4. Data Profiling – AWS Glue DataBrew Profile
Step Function gọi AWS Glue DataBrew để data profiling.

DataBrew Profile sẽ phân tích dataset:

Ví dụ với Yellow Taxi dataset:

| Column          | Insight       |
| --------------- | ------------- |
| passenger_count | max=6         |
| trip_distance   | max≈200 miles |
| fare_amount     | có giá trị âm |
| PULocationID    | 263 giá trị   |

Mục tiêu:
- Detect missing values

- Detect outliers

- Detect data type mismatch
- 
Ví dụ:

`fare_amount < 0`

`trip_distance = 0`

`passenger_count = null`
