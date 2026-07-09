---
title: "Blogs Posted"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---


###  [Blog 1 - Building a scalable user search layer on top of Amazon Cognito](3.1-Blog1/)
This is an article sharing a practical technical solution on AWS, guiding how to "mod" a powerful search engine and automatic data synchronization for the Amazon Cognito user management service. This solution uses a flexible combination of fully Serverless services such as AWS Lambda, Amazon DynamoDB, and Amazon OpenSearch Service, helping to unlock advanced search features (like fuzzy search, complex filtering) with ultra-fast response times and automatic scaling based on traffic.

###  [Blog 2 - Building a Smart Retry Mechanism for Serverless Queue Consumer on AWS](3.2-Blog2/)
This is an Architecture Guide sharing a practical solution that helps Serverless systems operate durably, with high fault-tolerance by cleverly combining available AWS services. The solution dives into handling temporary errors or throttled downstream services by utilizing the trio of AWS Lambda, Amazon SQS, and Amazon EventBridge Scheduler. This mechanism completely decouples the retry logic from the core business logic, providing precise retry timing control and tight integration with Dead Letter Queues (DLQ) to prevent data loss.

###  [Blog 3 - How ALS GeoAnalytics LITHOLENS™ Revolutionizes Drill Core Logging Using Machine Learning on Amazon EKS](3.3-Blog3/)
The article is a clear demonstration of combining the analytical power of Machine Learning with flexible computing infrastructure (Amazon EKS) to thoroughly solve an expensive, time-consuming, and highly manual problem in heavy industry. By developing the LITHOLENS™ platform, ALS GeoAnalytics has fully automated the process of analyzing and logging physical drill core samples, thereby enhancing data consistency. The Serverless and Containerized architecture on AWS not only optimizes costs but also enables the system to scale seamlessly, ready to be applied across various engineering sectors.

###  [Blog 4 - BUILDING A MULTI-ACCOUNT PATCH COMPLIANCE DASHBOARD WITH KIRO SPECS](3.4-Blog4/)
This article shares a solution for building a dashboard to track patch compliance at scale, covering multiple AWS accounts and Regions. The solution uses AWS Systems Manager combined with Amazon S3, AWS Lambda, and EventBridge to automate the process of collecting, processing, and storing cache data. Notably, the article applies Kiro Specs to design the workflow from Requirements -> Architecture -> Implementation Tasks, ensuring the dashboard meets criteria for security (no public endpoints), performance (reading from cache), and easy scalability.