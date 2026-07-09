---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Bản đề xuất Dự án DocuFlow AI & Bảng Phân Công Chi Tiết

## 1. Tóm tắt dự án

DocuFlow AI là nền tảng xử lý hóa đơn và biên nhận thông minh trên AWS theo kiến trúc serverless. Hệ thống tự động tiếp nhận file, trích xuất dữ liệu bằng công nghệ OCR (Textract) và API AI bên ngoài (External AI API), chuẩn hóa kết quả thành định dạng JSON và quản lý trạng thái. Dự án trình diễn một luồng workflow end-to-end hoàn chỉnh trong môi trường workshop AWS, được phát triển bởi nhóm 5 thành viên (AeroOps).

## 2. Kiến trúc giải pháp & Luồng hệ thống

![Kiến trúc DocuFlow AI](/images/2-Proposal/architecture_v4.png)

**Luồng demo chính:**
User -> CloudFront/Amplify -> Cognito -> API Gateway -> Lambda Presigned URL -> S3 Raw -> EventBridge -> SQS + DLQ -> Job Starter Lambda -> Step Functions -> Validate Lambda -> Textract -> AI Proxy Lambda -> External AI API ngoài AWS -> Confidence/Status Lambda -> DynamoDB + S3 Processed -> CloudWatch/X-Ray -> SNS/SES Alert.

## 3. Phân công công việc tổng quan

Dự án được chia thành 5 module chính tương ứng với 5 thành viên:
* **Hoàng Trọng Trà (Leader / Integration Owner):** Ingestion, Queue & Workflow Orchestration (S3, EventBridge, SQS + DLQ, Job Starter Lambda, Step Functions).
* **Vũ Duy Tài (AI Owner):** Textract, AI Proxy Lambda & External AI Normalization (Textract AnalyzeExpense, AI Proxy, External AI API, logic tính toán confidence/status).
* **Nguyễn Hữu Tịnh (Frontend/Auth Owner):** Frontend, Auth & User Flow (CloudFront, Amplify, Cognito, API Gateway, UI tải lên/kết quả/review).
* **Lâm Quang Lộc (Data Owner):** Data Persistence & Result Management (DynamoDB, S3 processed JSON, metadata, job state).
* **Phạm Tùng Dương (Ops/Security/IaC Owner):** Observability, Security, IaC & Cost Control (IAM, KMS, Secrets Manager, CloudTrail, SAM, CloudWatch, X-Ray, SNS/SES).

## 4. Trách nhiệm & Service Ownership

Mỗi service trong kiến trúc đều có người chịu trách nhiệm triển khai, lấy evidence (log/screenshot) và cleanup:
* **Edge/Frontend & Auth (Tịnh):** Deploy CloudFront, Amplify, UI routing, login/logout bằng Cognito.
* **API Layer (Trà + Tịnh):** API Gateway routing, thống nhất contract giữa backend và frontend.
* **Ingestion & Workflow (Trà):** S3 Raw, Lambda Presigned URL, EventBridge, SQS + DLQ, Job Starter Lambda, Step Functions state machine, Validate Lambda.
* **AI Extraction & Normalization (Tài):** Tích hợp Textract, viết AI Proxy Lambda gọi External AI, chuẩn hóa JSON, tính điểm tin cậy (confidence score).
* **Data Persistence (Lộc):** Thiết kế table DynamoDB, lưu S3 Processed JSON, tối ưu query.
* **Observability, Security & Cost (Dương):** IAM roles, KMS, Secrets Manager (lưu API key), CloudTrail, CloudWatch, X-Ray, SNS/SES, SAM deployment, Budget alerts.

## 5. Quy tắc chung & Hợp đồng dữ liệu (Contracts)

* **Kiến trúc MVP:** Không tự ý thêm/bớt service sau khi admin đã duyệt. Mọi thay đổi phải thông báo cho toàn team.
* **Data Contract:** Schema thống nhất cho kết quả xử lý, bắt buộc tuân thủ các trường required, metadata, và error fields.
* **Status Model:** `UPLOADED` -> `QUEUED` -> `PROCESSING` -> `EXTRACTED` | `REVIEW_REQUIRED` | `FAILED` -> `CORRECTED` -> `APPROVED`.
* **Bảo mật API Key:** API key của External AI chỉ được lưu trong Secrets Manager. Frontend không gọi trực tiếp ra ngoài; AI Proxy Lambda là lớp duy nhất được phép giao tiếp với External AI.
* **Quy tắc làm việc:** Dùng prefix `docuflow-dev-*` và tag `Project=DocuFlowAI` cho mọi resource. Freeze schema/endpoint trước khi demo và phải đảm bảo có script cleanup xóa toàn bộ resource sau workshop.

## 6. Lộ trình triển khai (12 Tuần)

* **Tuần 1-2:** Chốt thiết kế kiến trúc, API/Status draft, schema DynamoDB, SAM/Security plan. Xây dựng Foundation (S3/EventBridge/SQS, Textract PoC, Cognito/Amplify skeleton).
* **Tuần 3-4:** Upload & Queue (Presigned URL, upload UI, S3/IAM baseline). Hoàn thiện Workflow skeleton (Step Functions happy path, Textract Lambda, UX cơ bản).
* **Tuần 5-6:** Tích hợp AI (Workflow kết nối AI Lambda, AI Proxy + External AI, UI processing). Tích hợp Storage (Lưu DynamoDB/S3, trang chi tiết kết quả).
* **Tuần 7-8:** Luồng Review (Status transition, Reviewer UI, cảnh báo SNS/SES). Xử lý lỗi (Retry/catch/DLQ, test invalid JSON, giao diện lỗi).
* **Tuần 9-10:** Observability (Fix lỗi tích hợp, X-Ray, CloudTrail, Budgets). Kiểm thử E2E toàn hệ thống, thu thập screenshot UI/AI.
* **Tuần 11-12:** Viết tài liệu (Kịch bản demo, hướng dẫn frontend/backend, deploy/cleanup script). Final Demo & Cleanup.

## 7. Đánh giá rủi ro & Điểm dễ vỡ tích hợp

| Rủi ro | Biện pháp giảm thiểu |
| --- | --- |
| Output AI không khớp schema | Chốt JSON schema sớm; validate ngay tại Lambda; dùng chung sample output. |
| Upload xong nhưng status không chạy | Chốt chặt flow từ lúc upload tới queue; ghi log `documentId` ở mọi bước. |
| Lộ External AI API key | Lưu Secrets Manager; không log secret; frontend không gọi trực tiếp. |
| Workflow fail khó debug | Bật Step Functions history, CloudWatch structured logs và X-Ray. |
| DynamoDB query không khớp UI | Chốt response mẫu cho list/detail/review; mock API trước khi code backend. |

## 8. Definition of Done & Bàn giao (Checklist)

* **DoD chung:** Upload thành công ít nhất 3 sample từ frontend. EventBridge/SQS/Step Functions chạy mượt cả happy/failure path. Textract và External AI trả JSON hợp lệ. DynamoDB lưu đúng schema; S3 lưu `result.json`. Log đầy đủ `documentId`, alarm SNS/SES hoạt động. API key được bảo mật, phân quyền IAM chặt chẽ. Xóa sạch resource sau demo.
* **Bàn giao Module:** Từng thành viên phải cung cấp evidence (screenshot, log, file JSON mẫu, file ASL...) chứng minh phần việc của mình đã hoàn tất và tích hợp thành công.