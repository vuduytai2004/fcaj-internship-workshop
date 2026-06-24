---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
### Week 7 Objectives:

* Review database concepts (RDBMS, NoSQL) and their applications on AWS.
* Delve into AWS database services such as Amazon RDS, Aurora, Redshift, and ElastiCache.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | Module 06-01 - Database Concepts review <br> - RDBMS / NoSQL <br> - SQL (Structured Query Language) <br> - Scalability | 01/06/2026 | 01/06/2026 | <https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217> |
| 3 | Module 06-02 - Amazon RDS & Amazon Aurora <br> - RDS & Aurora <br> - Database Engine <br> - Multi-AZ Deployment <br> - Read Replicas | 02/06/2026 | 02/06/2026 | <https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218> |
| 4 | Module 06-03 - Redshift - Elasticache <br> - Redshift <br> - ElastiCache <br> - OLAP (Online Analytical Processing) | 03/06/2026 | 03/06/2026 | <https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219> |
| 5 | Practice some labs in module 6 | 04/06/2026 | 06/06/2026 | <https://000005.awsstudygroup.com/> <br><br> <https://000043.awsstudygroup.com/> |


### Week 7 Achievements:

* **Mastered Core Database Concepts:**
  * Reviewed and clearly distinguished between the two main database models: **RDBMS** (Relational Database Management System) and **NoSQL**. Understood the optimal use cases for each type based on data structure and retrieval requirements.
  * Grasped the core concepts of **SQL (Structured Query Language)** and how to perform fundamental queries and data manipulation.
  * Deepened understanding of database **Scalability**: Differentiated between Vertical Scaling (Scale up) and Horizontal Scaling (Scale out), and learned how to apply the appropriate scaling strategy depending on the database engine.

* **Understood and Applied Amazon RDS & Amazon Aurora:**
  * Gained a clear understanding of **Amazon RDS** (Relational Database Service), familiarizing with supported Database Engines such as MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server.
  * Explored **Amazon Aurora**, a high-performance relational database compatible with MySQL and PostgreSQL, specifically optimized for the cloud by AWS to provide superior scalability and availability.
  * Learned how to configure highly available architectures using **Multi-AZ Deployment**, ensuring the database can automatically failover in case of a disruption.
  * Configured and utilized **Read Replicas** to offload read traffic from the Primary DB, enhancing the performance of read-heavy applications.

* **Gained Proficiency in Amazon Redshift & Amazon ElastiCache:**
  * Explored **Amazon Redshift**, a powerful Data Warehouse service designed specifically for **OLAP (Online Analytical Processing)**. Understood how to leverage this service to process and query massive datasets for analytical reporting.
  * Grasped the mechanics of in-memory caching through **Amazon ElastiCache** (featuring Memcached and Redis). Learned how this service significantly optimizes application response times by caching frequently accessed data in memory.

* **Completed Hands-On Labs (Module 6 Labs):**
  * Successfully applied the theoretical knowledge of database management systems to practical scenarios in the AWS environment through comprehensive lab exercises.
  * Directly provisioned, configured, and operated Amazon RDS and ElastiCache systems, gaining practical experience in interacting with these services using Database Clients.
