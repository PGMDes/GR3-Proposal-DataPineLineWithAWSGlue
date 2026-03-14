---
title: "Solution Architecture"
date: "2025-11-09"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---



The proposed platform leverages an AWS Serverless Data Pipeline architecture to ensure operational stability, seamless scalability, and optimized cost-efficiency. All raw datasets from the Yellow Taxi Trip Records are centrally stored in Amazon S3, serving as a highly durable Data Lake. The orchestration of data flows and business logic is handled by AWS Lambda, ensuring a decoupled and efficient execution environment.

Data cleansing and standardization are automated through AWS Glue DataBrew Recipe Jobs, transforming complex raw trip records into structured, analytics-ready formats. The refined data is then ingested into Amazon Redshift, providing a high-performance Data Warehouse for large-scale analytical queries.

To drive business insights, AWS QuickSight delivers custom dashboards that visualize key performance indicators such as trip trends, passenger density, and revenue patterns in real-time. The entire ecosystem is strictly monitored by Amazon CloudWatch and fully automated via Amazon EventBridge to maintain a robust and self-healing pipeline.

![Cloud Racket Platform Architecture](/images/2-Proposal/aws_architect.jpg)

## AWS Services Used
- **AWS QuickSight**: Provides a Business Intelligence (BI) platform to visualize data through interactive dashboards, enabling deep analysis of taxi trip trends and financial performance.
- **AWS Lambda**: Handles business logic, data extraction (Extract), and orchestrates the workflow between AWS services in a serverless environment.
- **Amazon Redshift**: A high-performance, serverless Data Warehouse that enables complex SQL queries on massive taxi trip datasets with sub-second latency.
- **Amazon S3**: Acts as the central Data Lake, providing secure and durable storage for both raw and refined datasets.
- **Amazon EventBridge**: A serverless event bus used for event-driven orchestration, automatically triggering the daily data processing pipeline at scheduled intervals.
- **AWS Glue DataBrew (Recipe Jobs)**: A visual data preparation service that automates the cleaning and transformation of taxi data based on pre-defined processing recipes.
