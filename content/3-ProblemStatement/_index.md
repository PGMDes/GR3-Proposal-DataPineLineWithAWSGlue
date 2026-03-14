---
title: "Problem Statement"
date: "2025-11-09"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---



## What's the Problem?
Currently, finding and booking badminton courts mainly relies on manual contact methods (phone or social media). Booking schedules are not updated in real time, and users lack visibility on court coverage and distance estimation. Meanwhile, court owners face difficulties in managing and arranging court schedules as well as generating efficient revenue reports.

## The Solution
This platform automates the entire process of searching, booking, and management for both users and court owners.

Users can find courts near their location using Amazon Location Service, view real-time availability through Amazon DynamoDB, and receive personalized recommendations via Amazon Personalize.

Court owners can register and update court information, receive automated booking confirmation emails through Amazon SES, and view revenue analytics on a custom dashboard built with AWS Amplify, Lambda, and Chart.js using data from DynamoDB/S3.

The web interface is hosted on AWS Amplify with Amazon Cognito handling user authentication.

## Benefits and Return on Investment
+ **For Players**: Easily find and book suitable courts within seconds, receive personalized recommendations based on behavior and location, and get automated confirmation emails. Court search time is reduced by 90% (from 30 minutes to 3 minutes), and booking confirmation time decreases from 2–24 hours to just 5 minutes.

+ **For Court Owners**: Automatically manage courts, schedules, and bookings via a centralized dashboard, reducing manual operations by 80%. The system provides visualized reports on revenue, booking frequency, and average ratings to support data-driven decisions.

+ **For Developers**: Fully serverless architecture ensures minimal operational cost (< $1/month initially, estimated $8–15/month after Free Tier). The system serves as both a practical solution and a valuable learning environment, providing real-world data for research in AI, Vietnamese NLP, and recommendation systems.