---
title: "Risk Assessment"
date: "2025-11-09"
weight: 8
chapter: false
pre: " <b> 8. </b> "
---


## Risk Matrix
- **Internet connectivity loss**: Medium impact, medium probability
- **Unauthorized access**: High impact, low probability
- **Budget overrun**: Low impact, low probability
- **AI recommendation errors**: Medium impact, low probability

## Mitigation Strategies
- **Network**: Automatic retry on connection loss
- **Security**: Apply MFA via Cognito, WAF for attack prevention
- **Cost**: AWS Budgets alerts, optimize query frequency
- **AI**: Monitor and update Personalize model periodically

## Contingency Plans
- Allow temporary offline booking and sync when online
- Rollback CodePipeline if deployment errors occur or costs exceed budget

## Expected Outcomes

### Technical Improvements
The application provides real-time court search and booking capabilities, personalized recommendations, and visual reports that optimize operations for both players and court owners.

### Long-term Value
The platform can be expanded to other sports (tennis, basketball, gyms), serving as a framework template for smart sports solutions based on AWS Serverless and AI. Additionally, this is an ideal practice project for students or research groups wanting to apply AWS in developing intelligent systems.