---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
Tại phần này, bạn cần tóm tắt các nội dung trong workshop mà bạn **dự tính** sẽ làm.

# Bản đề xuất Dự án DocuFlow AI & Module Phân tích Dữ liệu

## 1. Tóm tắt điều hành

DocuFlow AI là nền tảng xử lý hóa đơn và biên nhận thông minh trên AWS theo kiến trúc serverless. Hệ thống được thiết kế để tự động tiếp nhận file, trích xuất dữ liệu bằng công nghệ AI/OCR, chuẩn hóa kết quả thành định dạng JSON và quản lý trạng thái xử lý. Dự án phục vụ mục đích trình diễn một luồng workflow end-to-end hoàn chỉnh trong môi trường workshop AWS.


## 2. Tuyên bố vấn đề

**Vấn đề hiện tại**

* Việc nhập liệu hóa đơn thủ công tốn nhiều thời gian và dễ dẫn đến sai sót ở các thông tin quan trọng như nhà cung cấp, ngày tháng, hay số tiền.
* Chứng từ thường nằm rải trực trong email hoặc thư mục, gây khó khăn cho việc tìm kiếm, kiểm toán và kiểm soát trạng thái.
* Thiếu khả năng hiển thị tổng quan (visibility), khiến nhóm tài chính không biết chính xác chứng từ nào đang bị lỗi và cần can thiệp thủ công.
* Quy trình dễ bị nghẽn vào các đợt cao điểm cuối tháng hoặc quý khi số lượng hóa đơn tăng cao.

**Giải pháp đề xuất**

* Xây dựng cổng tải tài liệu trực tiếp và an toàn thông qua presigned URL.
* Vận hành luồng xử lý serverless hoàn toàn tự động, tích hợp cơ chế retry, theo dõi trạng thái và hàng đợi lỗi (DLQ).
* Tự động trích xuất các trường dữ liệu quan trọng bằng Textract và Bedrock, sau đó lưu trữ siêu dữ liệu vào DynamoDB và kết quả JSON vào S3.

**Lợi ích & Hoàn vốn đầu tư**

* Giảm thiểu thao tác nhập liệu, tăng cường mức độ hiển thị trạng thái và cung cấp đầu ra dữ liệu có cấu trúc.
* Hệ thống tự động gửi cảnh báo khi phát hiện lỗi hoặc độ tin cậy trích xuất thấp, giúp tối ưu hóa thời gian xem xét.


## 3. Kiến trúc giải pháp

Kiến trúc tổng thể của DocuFlow AI được cấu trúc thành 5 lớp chuyên biệt: frontend/auth, ingestion/API, workflow processing, data storage/analytics và observability/security.

**Luồng hệ thống cốt lõi & AI Extraction**

* **Tiếp nhận sự kiện:** Khi người dùng tải file lên S3 Raw Bucket, event sẽ được gửi qua EventBridge vào SQS queue.
* **Điều phối quy trình:** Lambda kích hoạt Step Functions Standard Workflow để điều phối toàn bộ vòng đời của chứng từ.
* **Trích xuất thô (OCR):** Dịch vụ Amazon Textract (AnalyzeExpense) đọc và bóc tách các trường thông tin thô từ hóa đơn/biên nhận.
* **Chuẩn hóa thông minh (GenAI):** Amazon Bedrock nhận dữ liệu thô, phân loại và chuẩn hóa định dạng về một schema JSON duy nhất.
* **Xác thực kết quả:** Lambda thực hiện kiểm tra định dạng JSON, tính toán điểm độ tin cậy (confidence score) và cập nhật trạng thái tương ứng.


## 4. Triển khai kỹ thuật (Tập trung AI Extraction & Classification)

Module Trích xuất & Phân loại AI được đảm nhiệm bởi Member 3, thao tác chủ yếu trên Textract, Bedrock và Lambda.

**Thiết kế thành phần AI**

* **Lưu trữ dữ liệu thô:** Phải lưu giữ toàn bộ kết quả raw từ Textract vào thư mục processed trên S3 nhằm mục đích phục vụ gỡ lỗi (debug) khi có dữ liệu sai lệch.
* **Thiết kế Prompt cho Bedrock:** Bedrock chỉ nhận đầu vào là các trường raw đã được rút gọn để tối ưu hóa. Yêu cầu prompt trả về đúng định dạng JSON hợp lệ theo schema, tuyệt đối không sử dụng markdown hay thêm văn bản giải thích.
* **Cơ chế đánh giá (Confidence Policy):** Trạng thái chứng từ được cấp thành `EXTRACTED` chỉ khi `confidenceScore >= 0.80` và hệ thống nhận diện đủ các trường dữ liệu bắt buộc.
* **Chuyển hướng đánh giá thủ công:** Hệ thống sẽ gắn cờ `REVIEW_REQUIRED` nếu điểm tin cậy `< 0.80` hoặc khi trích xuất bị thiếu tên nhà cung cấp (vendorName) và tổng tiền (totalAmount).
* **Xử lý lỗi (Error Handling):** Trong trường hợp Bedrock hoặc Textract gặp lỗi tạm thời, Step Functions sẽ tiến hành retry theo cơ chế backoff; nếu vượt quá số lần thử, trạng thái sẽ chuyển thành `FAILED`.


## 5. Lộ trình & Mốc triển khai

Kế hoạch phân bổ trong 12 tuần với các mục tiêu trọng tâm:

* **Tuần 1:** Thống nhất phạm vi (scope), data contract, kiến trúc tổng quát và phân công module cho từng thành viên.
* **Tuần 4:** Hoàn thành bộ khung skeleton cho các dịch vụ EventBridge, SQS, Job Starter và luồng Step Functions.
* **Tuần 5:** Tích hợp thành công luồng Textract, đảm bảo khả năng trích xuất dữ liệu thô từ bộ mẫu.
* **Tuần 6:** Áp dụng Bedrock để chuẩn hóa dữ liệu, xác thực định dạng JSON và lưu trữ vào S3 processed bucket.
* **Tuần 8:** Hoàn thiện cơ chế xử lý lỗi, hàng đợi DLQ, tính năng retry và thiết lập cảnh báo SNS cho các case `FAILED` hoặc `REVIEW_REQUIRED`.
* **Tuần 11-12:** Hoàn tất kiểm thử E2E, chuẩn bị kịch bản demo, hoàn thiện tài liệu runbook và xác minh các tập lệnh dọn dẹp tài nguyên (clean-up).


## 6. Kiểm soát chi phí & Ngân sách

* **Giới hạn tài nguyên:** Ràng buộc kích thước file, số lượng trang xử lý và chỉ sử dụng khoảng 5-10 hóa đơn/biên nhận mẫu trong quá trình demo.
* **Tối ưu hóa Model:** Ưu tiên lựa chọn các mô hình Bedrock có chi phí thấp và phải xác minh tính khả dụng của mô hình trong tài khoản/region trước khi triển khai.
* **Cảnh báo ngân sách:** Thiết lập hệ thống AWS Budgets alert ở các ngưỡng chi phí $5 và $10.
* **Vòng đời tài nguyên:** Yêu cầu thiết lập S3 lifecycle hoặc sử dụng script cleanup để dọn dẹp các tệp tin lưu trữ sau khi workshop kết thúc, tránh phát sinh phí duy trì.


## 7. Đánh giá rủi ro (Module AI & Extraction)

| Rủi ro | Ảnh hưởng | Biện pháp giảm thiểu |
| --- | --- | --- |
| Textract đọc sai do ảnh mờ hoặc format lạ | Hệ thống xuất ra dữ liệu sai hoặc thiếu trường thông tin | Sử dụng tài liệu mẫu sắc nét, áp dụng ngưỡng độ tin cậy và trạng thái `REVIEW_REQUIRED`. |
| Bedrock xuất dữ liệu JSON sai định dạng | Gây lỗi parse dữ liệu ở tầng Lambda | Viết prompt nghiêm ngặt, bắt buộc validate JSON schema và xử lý retry/fallback. |
| Region không hỗ trợ model Bedrock | Toàn bộ luồng chuẩn hóa AI bị gián đoạn | Xác minh region ngay từ đầu, chuẩn bị model dự phòng hoặc kế hoạch triển khai cross-region. |


## 8. Kết quả kỳ vọng (Definition of Done)

* Người dùng có khả năng đăng nhập thành công và tải các tập tin hóa đơn/biên nhận mẫu lên hệ thống.
* Tập tin kích hoạt chuỗi Step Functions vận hành trơn tru qua các bước: Textract, Bedrock, JSON validation và lưu trữ.
* Dữ liệu `result.json` được định dạng và lưu vào S3 processed chuẩn xác theo data contract.
* Bảng DynamoDB ghi nhận chính xác metadata và trạng thái hiện tại của tài liệu.
* Kịch bản kiểm thử (Test cases) chứng minh được hệ thống hoạt động đúng cho ít nhất một trường hợp `EXTRACTED` và một trường hợp ngoại lệ (`REVIEW_REQUIRED` hoặc `FAILED`).