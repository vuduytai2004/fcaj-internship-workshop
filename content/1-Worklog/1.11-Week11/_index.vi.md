---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
### Mục tiêu tuần 11:

* Phát triển các Lambda functions để xử lý luồng AI (Textract Parser, AI Proxy, Confidence + Status).
* Thiết lập SNS và SES để gửi email thông báo cho người dùng.
* Thực hiện kiểm thử (test) và lưu trữ bằng chứng (evidence) cho các kịch bản.
* Hoàn thiện tài liệu luồng AI và rà soát kết quả.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tạo và viết code cho Textract Parser Lambda để xử lý raw output của Textract Analyze Expense | 29/06/2026 | 29/06/2026 | |
| 3 | Tạo và viết code cho AI Proxy Lambda để gọi External AI API qua giao thức HTTPS | 30/06/2026 | 30/06/2026 | |
| 4 | Tạo và viết code cho Confidence + Status Lambda xử lý tính điểm tin cậy và quyết định trạng thái tài liệu (EXTRACTED/REVIEW_REQUIRED/FAILED) | 01/07/2026 | 01/07/2026 | |
| 5 | Chạy test và lưu evidence các kịch bản Lambda (file rõ/mờ, missing field, Invalid JSON) | 02/07/2026 | 02/07/2026 | |
| 6 | Hoàn thiện tài liệu luồng AI: rà soát output Lambda khớp JSON Schema và kiểm tra Definition of Done | 03/07/2026 | 03/07/2026 | |
| 7 | Thiết lập SNS và SES để gửi email thông báo trạng thái tài liệu về cho người dùng | 04/07/2026 | 04/07/2026 | |


### Kết quả đạt được tuần 11:

* Đã tạo và viết code thành công cho Textract Parser Lambda để xử lý raw output.
* Hoàn thiện code AI Proxy Lambda cho phép gọi External AI API qua HTTPS ổn định.
* Phát triển xong Confidence + Status Lambda, xử lý logic tính điểm tin cậy và quyết định trạng thái tài liệu chính xác.
* Chạy test thành công các kịch bản Lambda đa dạng (file mờ, thiếu trường, invalid JSON) và lưu trữ đầy đủ evidence.
* Hoàn thiện toàn bộ tài liệu luồng AI, rà soát output khớp hoàn toàn với JSON Schema và đạt Definition of Done.
* Đã thiết lập thành công SNS và SES để tự động gửi email thông báo cho người dùng.
