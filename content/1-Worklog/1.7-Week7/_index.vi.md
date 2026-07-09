---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
### Mục tiêu tuần 7:

* Ôn tập các khái niệm cơ sở dữ liệu (RDBMS, NoSQL) và ứng dụng trên AWS.
* Tìm hiểu chi tiết các dịch vụ cơ sở dữ liệu của AWS như Amazon RDS, Aurora, Redshift và ElastiCache.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | Module 06-01 - Database Concepts review <br> - RDBMS / NoSQL <br> - SQL (Structured Query Language) <br> - Scalability | 01/06/2026 | 01/06/2026 | <https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217> |
| 3 | Module 06-02 - Amazon RDS & Amazon Aurora <br> - RDS & Aurora <br> - Database Engine <br> - Multi-AZ Deployment <br> - Read Replicas | 02/06/2026 | 02/06/2026 | <https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218> |
| 4 | Module 06-03 - Redshift - Elasticache <br> - Redshift <br> - ElastiCache <br> - OLAP (Online Analytical Processing) | 03/06/2026 | 03/06/2026 | <https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219> |
| 5 | Thực hành một số bài lab ở module 6 | 04/06/2026 | 06/06/2026 | <https://000005.awsstudygroup.com/> <br><br> <https://000043.awsstudygroup.com/> |


### Kết quả đạt được tuần 7:

* Nắm vững các khái niệm cơ sở dữ liệu (Database Concepts):
  * Ôn tập và phân biệt rõ ràng giữa hai mô hình cơ sở dữ liệu chính là RDBMS (Relational Database Management System) và NoSQL. Hiểu được các trường hợp sử dụng tối ưu cho từng loại hình cơ sở dữ liệu dựa trên cấu trúc dữ liệu và yêu cầu truy xuất.
  * Nắm vững các khái niệm cốt lõi của ngôn ngữ truy vấn cấu trúc SQL (Structured Query Language), cách thực hiện các câu lệnh thao tác với dữ liệu.
  * Hiểu sâu về khái niệm Khả năng mở rộng (Scalability) trong cơ sở dữ liệu: Phân biệt giữa mở rộng theo chiều dọc (Vertical Scaling - Scale up) và chiều ngang (Horizontal Scaling - Scale out), đồng thời biết áp dụng phương pháp mở rộng nào cho phù hợp với loại hình Database đang sử dụng.

* Hiểu và ứng dụng các dịch vụ Amazon RDS & Amazon Aurora:
  * Hiểu rõ khái niệm và cấu trúc của dịch vụ quản lý cơ sở dữ liệu quan hệ Amazon RDS, làm quen với các loại Database Engine được hỗ trợ như MySQL, PostgreSQL, MariaDB, Oracle, và SQL Server.
  * Khám phá Amazon Aurora, giải pháp cơ sở dữ liệu quan hệ tương thích với MySQL và PostgreSQL do AWS thiết kế tối ưu, cung cấp hiệu suất và khả năng mở rộng vượt trội.
  * Tìm hiểu cách cấu hình kiến trúc có tính sẵn sàng cao thông qua Multi-AZ Deployment, đảm bảo cơ sở dữ liệu có khả năng tự động chuyển đổi dự phòng (failover) trong trường hợp xảy ra sự cố.
  * Cấu hình và sử dụng Read Replicas để giảm tải áp lực đọc dữ liệu lên cơ sở dữ liệu chính (Primary DB), giúp nâng cao hiệu suất cho các ứng dụng có lượng truy vấn đọc cao.

* Hiểu và vận dụng kiến thức về Amazon Redshift & Amazon ElastiCache:
  * Khám phá Amazon Redshift, dịch vụ kho dữ liệu (Data Warehouse) mạnh mẽ dành cho các tác vụ phân tích trực tuyến OLAP (Online Analytical Processing). Hiểu cách sử dụng dịch vụ này để xử lý và truy vấn khối lượng dữ liệu khổng lồ phục vụ cho việc lập báo cáo phân tích.
  * Nắm bắt cơ chế lưu trữ đệm trong bộ nhớ (In-memory caching) thông qua dịch vụ Amazon ElastiCache (với Memcached và Redis). Hiểu cách dịch vụ này hỗ trợ tối ưu hóa thời gian phản hồi của ứng dụng bằng cách lưu trữ tạm thời các dữ liệu thường xuyên được truy xuất.

* Hoàn thành các bài Lab thực hành (Module 6 Labs):
  * Đã áp dụng toàn bộ những kiến thức lý thuyết về các hệ quản trị cơ sở dữ liệu vào môi trường thực tế trên AWS thông qua các bài thực hành chuyên sâu.
  * Trực tiếp triển khai, cấu hình và vận hành các hệ thống Amazon RDS, ElastiCache, và trải nghiệm quá trình tương tác trực tiếp bằng các công cụ Database Clients.


