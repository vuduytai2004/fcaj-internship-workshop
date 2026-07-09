---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 4 Objectives:

* Grasp core AWS compute services such as Amazon EC2, AMI, EBS, and Auto Scaling features.
* Learn and configure load balancing (ELB), DNS service (Route 53), and content delivery network (CloudFront).


### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | Module 03-01 - Compute VM on AWS <br> - Amazon EC2 <br> - Elasticity <br> - AMI (Amazon Machine Image) <br> - Instance <br> Module 03-01-01 - Amazon Elastic Compute Cloud (EC2) - Instance type <br> - Instance Family <br> - Compute/Memory/Storage Optimized <br> - Workload <br> - Throughput/IOPS | 11/05/2026 | 11/05/2026 | <https://www.youtube.com/watch?v=e7XeKdOVq40&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=73> <br><br> <https://www.youtube.com/watch?v=-t5h4N6vfBs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=73> |
| 3 | Module 03-01-02 - Amazon Elastic Compute Cloud (EC2) - AMI / Backup / Key Pair <br> - AMI <br> - Snapshot <br> - Key Pair (Public/Private Key) <br> - Deployment <br> Module 03-01-03 - Amazon Elastic Compute Cloud (EC2) - Elastic block store <br> - EBS (Elastic Block Store) <br> - Volume <br> - SSD vs HDD <br> - Snapshot <br> - Availability Zone (AZ) | 12/05/2026 | 12/05/2026 | <https://www.youtube.com/watch?v=yAR6QRT3N1k&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=75> <br><br> <https://www.youtube.com/watch?v=hKr_TfGP7NY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=76> |
| 4 | Module 03-01-04 - Amazon Elastic Compute Cloud (EC2) - Instance store <br> - Instance Store <br> - Ephemeral Storage <br> - High I/O Performance <br> - Data Persistence <br> Module 03-01-05 - Amazon Elastic Compute Cloud (EC2) - User data <br> - User Data <br> - Bootstrapping <br> - Automation <br> - Root Privileges | 13/05/2026 | 13/05/2026 | <https://www.youtube.com/watch?v=6IHNDJ85aoQ&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=76> <br><br> <https://www.youtube.com/watch?v=_v_43Wi7zjo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=78> |
| 5 | Module 03-01-06 - Amazon Elastic Compute Cloud (EC2) - Meta data <br> - Instance Metadata <br> - 169.254.169.254 <br> - Instance ID/Public IP <br> - Dynamic Data <br> Module 03-01-07 - Amazon Elastic Compute Cloud (EC2) - EC2 auto scaling <br> - EC2 Auto Scaling <br> - Scaling Policy <br> - Launch Template <br> - High Availability | 14/05/2026 | 14/05/2026 | <https://www.youtube.com/watch?v=Ew3QRaKJQSA&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=79> <br><br> <https://www.youtube.com/watch?v=bbLcPitXJSY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=80> |
| 6 | Module-03-02 - EC2 Autoscaling - EFS/FSx - Lightsail - MGN <br> - EFS <br> - FSx <br> - AWS Lightsail <br> - AWS MGN <br> - Shared Storage | 15/05/2026 | 15/05/2026 | <https://www.youtube.com/watch?v=hFVYG8WqfU0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=81> |
| 7 | Practice labs in module 3 | 16/05/2026 | 17/05/2026 | <https://000013.awsstudygroup.com/> <br><br> <https://000024.awsstudygroup.com/> <br><br> <https://000057.awsstudygroup.com/> |


### Week 4 Achievements:

* In-depth Understanding and Application of Amazon EC2: Thoroughly grasped the characteristics of EC2 Instances and clearly distinguished between different Instance Families. Developed the ability to evaluate and select the most optimal and suitable Instance type for specific Workloads (Compute Optimized, Memory Optimized, Storage Optimized), while considering detailed calculations for Throughput and IOPS to ensure system performance.
* Mastery of AWS Storage Services: Understood the architecture and practical applications of Elastic Block Store (EBS), including how to choose between drive types (SSD vs HDD) based on actual needs. Explored Instance Store (Ephemeral Storage) deeply for tasks requiring high I/O performance. Learned and differentiated high-level Shared Storage solutions like EFS (Elastic File System) and FSx for complex systems.
* Data Management and Security: Proficiently practiced using Snapshots to safely back up and restore data from Volumes. Understood the working principles of Key Pairs (Public/Private Keys) for authentication and establishing completely secure remote access (SSH) to instances.
* System Deployment and Automation: Mastered the packaging and utilization of Amazon Machine Images (AMIs) to accelerate deployment speed. Understood and successfully applied User Data scripts (Bootstrapping) to automate software installation and instance configuration immediately upon startup with Root Privileges, saving time during mass deployments.
* Establishing High Availability & Auto Scaling: Grasped the operational mechanisms of EC2 Auto Scaling and understood how to set up Horizontal Scaling so the system can automatically scale resources in or out. Gained the ability to define Desired Capacity, configure Scaling Policies, and utilize Launch Templates to guarantee system stability against traffic fluctuations.
* Instance Information Retrieval: Learned how to configure and query Instance Metadata via the special IP address (169.254.169.254) to flexibly collect Dynamic Data such as Instance IDs and Public IPs while applications are running.
* Expanding Knowledge of Other Compute Services: Got acquainted with AWS Lightsail for small-scale or simple web projects requiring rapid deployment. Introduced to AWS Application Migration Service (MGN) for migrating applications to the Cloud.
* Practical Skills: Confidently completed all in-depth Labs for Module 3, directly applying theoretical knowledge to solve problems in real-world AWS environments, thereby significantly reinforcing hands-on experience.
