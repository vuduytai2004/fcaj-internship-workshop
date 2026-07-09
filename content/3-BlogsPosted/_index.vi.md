---
title: "Các bài blogs đã đăng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---


###  [Blog 1 - Building a scalable user search layer on top of Amazon Cognito](3.1-Blog1/)
Đây là một bài viết chia sẻ giải pháp kỹ thuật thực chiến trên AWS, hướng dẫn cách "độ" thêm một bộ máy tìm kiếm cực mạnh và đồng bộ dữ liệu tự động cho dịch vụ quản lý người dùng Amazon Cognito. Giải pháp này sử dụng sự kết hợp linh hoạt giữa các dịch vụ hoàn toàn không máy chủ (Serverless) như AWS Lambda, Amazon DynamoDB, và Amazon OpenSearch Service, giúp mở khóa các tính năng tìm kiếm nâng cao (như tìm kiếm mờ, lọc đa điều kiện) với tốc độ phản hồi cực nhanh và khả năng tự động mở rộng theo lưu lượng.

###  [Blog 2 - Xây dựng Cơ chế Retry Thông minh cho Serverless Queue Consumer trên AWS](3.2-Blog2/)
Đây là một bài viết hướng dẫn kiến trúc (Architecture Guide) chia sẻ giải pháp thực tế giúp hệ thống Serverless hoạt động bền bỉ, có khả năng tự phục hồi lỗi (fault-tolerant) cao bằng cách kết hợp khéo léo các dịch vụ có sẵn của AWS. Giải pháp đi sâu vào việc xử lý các tình huống lỗi tạm thời hay khi downstream service bị throttle bằng cách sử dụng bộ ba dịch vụ AWS Lambda, Amazon SQS và Amazon EventBridge Scheduler. Cơ chế này tách biệt hoàn toàn logic retry khỏi business logic, cung cấp khả năng kiểm soát thời gian retry chính xác và tích hợp chặt chẽ với Dead Letter Queue (DLQ) để tránh mất mát dữ liệu.

###  [Blog 3 - Cách ALS GeoAnalytics LITHOLENS™ Cách Mạng Hóa Việc Ghi Chép Mẫu Lõi Khoan Bằng Machine Learning Trên Amazon EKS](3.3-Blog3/)
Bài viết là minh chứng rõ nét cho việc kết hợp sức mạnh phân tích của Machine Learning với hạ tầng tính toán linh hoạt (Amazon EKS) để giải quyết triệt để một bài toán đắt đỏ, tốn thời gian và nặng tính thủ công trong ngành công nghiệp nặng. Bằng việc phát triển nền tảng LITHOLENS™, ALS GeoAnalytics đã tự động hóa hoàn toàn quy trình phân tích và ghi chép mẫu lõi khoan vật lý, từ đó nâng cao tính nhất quán của dữ liệu. Cấu trúc Serverless và Container hóa trên AWS không chỉ tối ưu hóa chi phí mà còn giúp hệ thống dễ dàng mở rộng, sẵn sàng ứng dụng cho nhiều lĩnh vực kỹ thuật khác nhau.

###  [Blog 4 - XÂY DỰNG DASHBOARD THEO DÕI PATCH COMPLIANCE TRÊN NHIỀU AWS ACCOUNT VỚI KIRO SPECS](3.4-Blog4/)
Bài viết này chia sẻ giải pháp xây dựng một dashboard theo dõi tình trạng cập nhật bản vá (patch compliance) trên quy mô lớn, bao quát nhiều AWS account và Region. Giải pháp sử dụng AWS Systems Manager kết hợp với Amazon S3, AWS Lambda và EventBridge để tự động hóa quá trình thu thập, xử lý và lưu trữ dữ liệu cache. Điểm đặc biệt là bài viết ứng dụng Kiro Specs để thiết kế quy trình từ Yêu cầu -> Kiến trúc -> Task triển khai, giúp dashboard đảm bảo các tiêu chí về bảo mật (không mở public endpoint), hiệu năng (đọc từ cache), và dễ dàng mở rộng.