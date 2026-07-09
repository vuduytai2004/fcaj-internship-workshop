---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
### Mục tiêu tuần 6:

* Nắm vững mô hình trách nhiệm chia sẻ của AWS và các dịch vụ quản lý truy cập (IAM, Cognito).
* Hiểu và áp dụng các dịch vụ bảo mật dữ liệu (KMS, Security Hub) và các công cụ bảo vệ hệ thống nâng cao (GuardDuty, WAF).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | Module 05-01 - Share Responsibility Model <br> - Shared Responsibility Model <br> - Security OF the Cloud <br> - Security in the Cloud <br> - Compliance | 25/05/2026 | 25/05/2026 | <https://www.youtube.com/watch?v=tsobAlSg19g&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152> |
| 3 | Module 05-02 - Amazon Identity and access management <br> - IAM User/Group/Role/Policy <br> - Least Privilege <br> - MFA (Multi-Factor Authentication) <br> - JSON Policy | 26/05/2026 | 26/05/2026 | <https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152> |
| 4 | Module 05-03 - Amazon Cognito <br> - User Pool <br> - Identity Pool <br> - Social Identity Providers <br> - Web Identity Federation | 27/05/2026 | 27/05/2026 | <https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=153> <br><br> <https://www.youtube.com/watch?v=NW1xrMkNMjU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=155> |
| 5 | Module 05-06 - Amazon Key Management Service <br> - KMS <br> - Customer Managed Key (CMK) <br> - Encryption at Rest <br> - Key Policy <br><br> Module 05-07 - AWS Security Hub <br> - Security Hub <br> - Centralized View <br> - Compliance Checks <br> - Findings | 28/05/2026 | 28/05/2026 | <https://www.youtube.com/watch?v=GMihNQojhZc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=156> <br><br> <https://www.youtube.com/watch?v=clj2E0rNBEs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=157> |
| 6 | Module 05-08 - Hands-on and Additional research <br> - Hands-on Lab <br> - GuardDuty <br> - WAF (Web Application Firewall) <br> - DDoS Protection | 29/05/2026 | 29/05/2026 | <https://www.youtube.com/watch?v=0SdpD2GPYz4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=158> |
| 7 | Thực hành một số bài lab ở module 5 | 30/05/2026 | 31/05/2026 | <https://000018.awsstudygroup.com/> <br><br> <https://000022.awsstudygroup.com/> <br><br> <https://000027.awsstudygroup.com/> <br><br> <https://000028.awsstudygroup.com/> <br><br> <https://000030.awsstudygroup.com/> <br><br> <https://000033.awsstudygroup.com/> <br><br> <https://000044.awsstudygroup.com/> <br><br> <https://000048.awsstudygroup.com/> |


### Kết quả đạt được tuần 6:
- Nắm vững nền tảng về Bảo mật Đám mây (Cloud Security Fundamentals): Hiểu rõ các khái niệm cốt lõi như tính bảo mật, tính toàn vẹn, tính sẵn sàng (CIA Triad), mô hình AAA (Authentication, Authorization, Accounting) và các phương pháp quản lý rủi ro trên AWS.
- Hiểu sâu về Mô hình Trách nhiệm Chia sẻ (Shared Responsibility Model): Phân biệt rõ ràng trách nhiệm bảo mật CỦA đám mây (của AWS) và bảo mật TRONG đám mây (của khách hàng), cùng với các tiêu chuẩn tuân thủ (Compliance).
- Quản lý danh tính và quyền truy cập (IAM): Thành thạo việc tạo và quản lý IAM User, Group, Role, Policy. Áp dụng hiệu quả nguyên tắc đặc quyền tối thiểu (Least Privilege), cấu hình bảo mật đa yếu tố (MFA) và viết/đọc các JSON Policy cơ bản.
- Xác thực ứng dụng với Amazon Cognito: Tìm hiểu và ứng dụng User Pool để quản lý người dùng, Identity Pool để cấp quyền truy cập tài nguyên, cũng như cách tích hợp các nhà cung cấp danh tính xã hội (Social Identity Providers) và Web Identity Federation.
- Quản lý mã hóa và bảo mật dữ liệu: 
  - Nắm bắt cơ chế mã hóa dữ liệu tại chỗ (Encryption at Rest) thông qua Amazon Key Management Service (KMS), bao gồm việc tạo và quản lý các khóa mã hóa do khách hàng quản lý (CMK) và thiết lập Key Policy.
  - Cấu hình AWS Security Hub để có được cái nhìn tập trung (Centralized View) về tình trạng bảo mật, thực hiện kiểm tra tự động các tiêu chuẩn tuân thủ (Compliance Checks) và đánh giá các phát hiện bảo mật (Findings).
- Thực hành các công cụ bảo mật nâng cao: Nghiên cứu và tìm hiểu về các dịch vụ bảo vệ hệ thống như Amazon GuardDuty (phát hiện mối đe dọa), AWS WAF (tường lửa ứng dụng web) và các giải pháp chống DDoS.
- Hoàn thành các bài Lab thực tế: Áp dụng toàn bộ lý thuyết Module 5 vào việc thực hành và củng cố kỹ năng thông qua hàng loạt các bài lab chi tiết.
