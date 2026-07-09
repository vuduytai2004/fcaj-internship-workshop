---
title: "Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# DocuFlow AI Project Proposal & Team Work Assignment

## 1. Executive Summary

DocuFlow AI is an intelligent invoice and receipt processing platform on AWS based on a serverless architecture. The system is designed to automatically ingest files, extract data using OCR (Textract) and an External AI API, standardize results into JSON format, and manage processing statuses. The project serves the purpose of demonstrating a complete end-to-end workflow within an AWS workshop environment, built by a 5-member team (AeroOps).

## 2. Solution Architecture & Main Workflow

![DocuFlow AI Architecture](/images/2-Proposal/architecture_v4.png)

**Main Demo Flow:**
User -> CloudFront/Amplify -> Cognito -> API Gateway -> Lambda Presigned URL -> S3 Raw -> EventBridge -> SQS + DLQ -> Job Starter Lambda -> Step Functions -> Validate Lambda -> Textract -> AI Proxy Lambda -> External AI API outside AWS -> Confidence/Status Lambda -> DynamoDB + S3 Processed -> CloudWatch/X-Ray -> SNS/SES Alert.

## 3. Overall Team Assignment

The project is divided among 5 members with specific roles and modules:
* **Hoang Trong Tra (Leader / Integration Owner):** Ingestion, Queue & Workflow Orchestration (S3, EventBridge, SQS + DLQ, Job Starter Lambda, Step Functions).
* **Vu Duy Tai (AI Owner):** Textract, AI Proxy Lambda & External AI Normalization (Textract AnalyzeExpense, AI Proxy, External AI API, confidence/status logic).
* **Nguyen Huu Tinh (Frontend/Auth Owner):** Frontend, Auth & User Flow (CloudFront, Amplify, Cognito, API Gateway, upload/result/review UI).
* **Lam Quang Loc (Data Owner):** Data Persistence & Result Management (DynamoDB, S3 processed JSON, document metadata, job state).
* **Pham Tung Duong (Ops/Security/IaC Owner):** Observability, Security, IaC & Cost Control (IAM, KMS, Secrets Manager, CloudTrail, AWS SAM, CloudWatch, X-Ray, SNS/SES).

## 4. Service Ownership & Responsibilities

To avoid orphaned services, every component has a designated owner responsible for deployment, evidence collection (logs/screenshots), and cleanup:
* **Edge/Frontend & Auth (Tinh):** CloudFront, Amplify, Cognito deployment, routing, UI build, login/logout, JWT handling.
* **API Layer (Tra + Tinh):** API Gateway routing, backend/frontend contract.
* **Ingestion & Workflow (Tra):** S3 Raw bucket, Lambda Presigned URL, EventBridge routing, SQS+DLQ, Job Starter Lambda, Step Functions state machine, Validate Lambda.
* **AI Extraction & Normalization (Tai):** Textract integration, AI Proxy Lambda (calling external AI), JSON schema normalization, confidence score calculation.
* **Data Persistence (Loc):** DynamoDB tables, S3 Processed JSON, query optimization.
* **Observability, Security & Cost (Duong):** IAM roles, KMS encryption, Secrets Manager (API keys), CloudTrail, CloudWatch logs/alarms, X-Ray, SNS/SES alerts, SAM deployment, Budgets.

## 5. General Rules & Mandatory Contracts

* **Architecture MVP:** No unauthorized addition/removal of services after admin approval. All changes must be communicated.
* **Data Contract:** Unified JSON schema for document results, required fields, review fields, metadata, and error fields.
* **Status Model:** `UPLOADED` -> `QUEUED` -> `PROCESSING` -> `EXTRACTED` | `REVIEW_REQUIRED` | `FAILED` -> `CORRECTED` -> `APPROVED`.
* **API Key Security:** External AI API keys must be stored in Secrets Manager. Frontend cannot call the external AI directly; the AI Proxy Lambda is the only layer allowed to communicate with it.
* **Team Rules:** Do not hard-code API keys. Prefix all resources with `docuflow-dev-*` and tag them with `Project=DocuFlowAI`. Freeze schema, endpoints, and status models before demo.

## 6. Implementation Timeline (12 Weeks)

* **Week 1-2:** Finalize architecture design, API drafts, UI/API requirements, DynamoDB schema, SAM/security plans. Build Foundation (S3/EventBridge/SQS, Textract PoC, Cognito/Amplify skeleton).
* **Week 3-4:** Upload & Queue (Presigned URL, event/queue, upload UI, S3/IAM baseline). Workflow skeleton (Step Functions happy path, Textract parser Lambda, Start process UX).
* **Week 5-6:** AI integration (Connect workflow, AI Proxy + External AI normalize, processing UI, Secrets Manager). Storage integration (Save DynamoDB/S3 result, detail result page, IAM refinement).
* **Week 7-8:** Review flow (Status transition, review reasons, reviewer UI, SNS/SES alerts). Error handling (Retry/catch/failure path, invalid JSON tests, UI error states, Alarms + DLQ).
* **Week 9-10:** Observability & Report (Integration fixes, AI edge cases, UI polish, X-Ray/CloudTrail/Budgets). E2E testing (End-to-end test owner, AI test cases, UI screenshots, Security/cost checklist).
* **Week 11-12:** Documentation & Final Demo (Demo script, AI explanation, frontend/data model guides, deploy/cleanup guides, demo integration).

## 7. Integration Risks & Mitigation

| Risk | Mitigation Strategy |
| --- | --- |
| External AI output schema mismatch | Finalize JSON schema early; validate via Lambda; use common sample outputs. |
| Frontend upload finishes but status hangs | Finalize flow (upload -> S3 -> event -> queue -> workflow); log documentId at each step. |
| External AI API key leak | Store in Secrets Manager; no direct frontend access; no logging of secrets. |
| Workflow fails and is hard to debug | Enable Step Functions history, CloudWatch structured logs, and X-Ray tracing. |
| DynamoDB queries don't match UI | Finalize response models for list/detail/review; mock data before backend is ready. |

## 8. Definition of Done & Handover Checklists

* **General DoD:** Upload at least 3 sample invoices/receipts from the frontend. EventBridge/SQS/Step Functions execute correctly for both happy and failure paths. Textract extracts main fields and External AI API returns valid JSON. DynamoDB stores correct schema; S3 processed holds `result.json`. CloudWatch logs trace `documentId` with active alarms. Secrets Manager secures API keys with proper IAM scoping. Clean up all resources after the demo.
* **Module Deliverables:** Each member must provide evidence (screenshots, logs, or equivalent documentation) for their respective components, such as workflow diagrams, execution histories, normalized JSON samples, API responses, SAM deploy templates, and budget alert screenshots.