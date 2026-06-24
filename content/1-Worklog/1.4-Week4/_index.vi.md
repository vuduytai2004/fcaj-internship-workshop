---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Mục tiêu tuần 4:

* Nắm bắt các dịch vụ tính toán cốt lõi của AWS như Amazon EC2, AMI, EBS và tính năng Auto Scaling.
* Tìm hiểu và cấu hình cân bằng tải (ELB), dịch vụ DNS (Route 53) và mạng phân phối nội dung (CloudFront).


### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | Module 03-01 - Compute VM on AWS <br> - Amazon EC2 <br> - Elasticity <br> - AMI (Amazon Machine Image) <br> - Instance <br> Module 03-01-01 - Amazon Elastic Compute Cloud (EC2) - Instance type <br> - Instance Family <br> - Compute/Memory/Storage Optimized <br> - Workload <br> - Throughput/IOPS | 11/05/2026 | 11/05/2026 | <https://www.youtube.com/watch?v=e7XeKdOVq40&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=73> <br><br> <https://www.youtube.com/watch?v=-t5h4N6vfBs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=73> |
| 3 | Module 03-01-02 - Amazon Elastic Compute Cloud (EC2) - AMI / Backup / Key Pair <br> - AMI <br> - Snapshot <br> - Key Pair (Public/Private Key) <br> - Deployment <br> Module 03-01-03 - Amazon Elastic Compute Cloud (EC2) - Elastic block store <br> - EBS (Elastic Block Store) <br> - Volume <br> - SSD vs HDD <br> - Snapshot <br> - Availability Zone (AZ) | 12/05/2026 | 12/05/2026 | <https://www.youtube.com/watch?v=yAR6QRT3N1k&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=75> <br><br> <https://www.youtube.com/watch?v=hKr_TfGP7NY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=76> |
| 4 | Module 03-01-04 - Amazon Elastic Compute Cloud (EC2) - Instance store <br> - Instance Store <br> - Ephemeral Storage <br> - High I/O Performance <br> - Data Persistence <br> Module 03-01-05 - Amazon Elastic Compute Cloud (EC2) - User data <br> - User Data <br> - Bootstrapping <br> - Automation <br> - Root Privileges | 13/05/2026 | 13/05/2026 | <https://www.youtube.com/watch?v=6IHNDJ85aoQ&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=76> <br><br> <https://www.youtube.com/watch?v=_v_43Wi7zjo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=78> |
| 5 | Module 03-01-06 - Amazon Elastic Compute Cloud (EC2) - Meta data <br> - Instance Metadata <br> - 169.254.169.254 <br> - Instance ID/Public IP <br> - Dynamic Data <br> Module 03-01-07 - Amazon Elastic Compute Cloud (EC2) - EC2 auto scaling <br> - EC2 Auto Scaling <br> - Scaling Policy <br> - Launch Template <br> - High Availability | 14/05/2026 | 14/05/2026 | <https://www.youtube.com/watch?v=Ew3QRaKJQSA&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=79> <br><br> <https://www.youtube.com/watch?v=bbLcPitXJSY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=80> |
| 6 | Module-03-02 - EC2 Autoscaling - EFS/FSx - Lightsail - MGN <br> - EFS <br> - FSx <br> - AWS Lightsail <br> - AWS MGN <br> - Shared Storage | 15/05/2026 | 15/05/2026 | <https://www.youtube.com/watch?v=hFVYG8WqfU0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=81> |
| 7 | Thực hành các bài lab ở module 3 | 16/05/2026 | 17/05/2026 | <https://000013.awsstudygroup.com/> <br><br> <https://000024.awsstudygroup.com/> <br><br> <https://000057.awsstudygroup.com/> |


### Kết quả đạt được tuần 4:

* **Hiểu và ứng dụng chuyên sâu về Amazon EC2:** Nắm bắt cặn kẽ các đặc tính của EC2 Instance, phân biệt rõ các Instance Family. Có khả năng đánh giá và lựa chọn loại Instance phù hợp và tối ưu nhất cho từng loại Workload cụ thể (Compute Optimized, Memory Optimized, Storage Optimized), đồng thời tính toán chi tiết về Throughput và IOPS để đảm bảo hiệu suất hệ thống.
* **Làm chủ các dịch vụ lưu trữ trên AWS:** Hiểu rõ kiến trúc và tính ứng dụng của Elastic Block Store (EBS), bao gồm việc lựa chọn giữa các loại ổ cứng (SSD vs HDD) dựa trên nhu cầu thực tế. Khám phá sâu về Instance Store (Ephemeral Storage) cho các tác vụ cần I/O tốc độ cao. Tìm hiểu và phân biệt các giải pháp Shared Storage cấp độ cao như EFS (Elastic File System) và FSx cho các hệ thống phức tạp.
* **Quản lý dữ liệu và bảo mật:** Thực hành thành thạo tính năng Snapshot để sao lưu và phục hồi dữ liệu từ Volume một cách an toàn. Hiểu nguyên lý hoạt động của Key Pair (Public/Private Key) trong việc xác thực và thiết lập quyền truy cập từ xa (SSH) vào các instance một cách bảo mật tuyệt đối.
* **Triển khai và Tự động hóa hệ thống (Automation):** Nắm vững cách đóng gói và sử dụng Amazon Machine Image (AMI) để tăng tốc độ triển khai. Hiểu và áp dụng thành công kịch bản User Data (Bootstrapping) để tự động hóa việc cài đặt phần mềm và cấu hình instance ngay khi khởi động dưới quyền Root Privileges, giúp tiết kiệm thời gian triển khai hàng loạt.
* **Thiết lập Tính sẵn sàng cao (High Availability) & Auto Scaling:** Nắm vững cơ chế hoạt động của EC2 Auto Scaling, hiểu cách thiết lập Horizontal Scaling để hệ thống tự động mở rộng hoặc thu hẹp tài nguyên. Có khả năng định nghĩa Desired Capacity, cấu hình các Scaling Policy và sử dụng Launch Template để đảm bảo hệ thống luôn ổn định trước các biến động lưu lượng truy cập.
* **Truy xuất thông tin Instance:** Biết cách cấu hình và truy vấn Instance Metadata thông qua địa chỉ IP đặc biệt (169.254.169.254) để thu thập linh hoạt các Dynamic Data như Instance ID, Public IP trong quá trình ứng dụng đang chạy.
* **Mở rộng kiến thức về các dịch vụ điện toán khác:** Làm quen với AWS Lightsail dành cho các dự án web quy mô nhỏ hoặc đơn giản cần triển khai nhanh chóng. Biết đến AWS Application Migration Service (MGN) phục vụ cho quá trình di chuyển ứng dụng lên Cloud.
* **Kỹ năng thực hành:** Tự tin hoàn thành toàn bộ các bài Lab chuyên sâu của Module 3, áp dụng trực tiếp lý thuyết vào việc giải quyết các bài toán trên môi trường AWS thực tế, qua đó củng cố kinh nghiệm thực chiến một cách rõ rệt.
