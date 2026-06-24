---
title: "Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
In this section, you need to summarize the contents of the workshop that you **plan** to conduct.

# DocuFlow AI Project Proposal & Data Analytics Module

## 1. Executive Summary

DocuFlow AI is an intelligent invoice and receipt processing platform on AWS based on a serverless architecture. The system is designed to automatically ingest files, extract data using AI/OCR technology, standardize results into JSON format, and manage processing statuses. The project serves the purpose of demonstrating a complete end-to-end workflow within an AWS workshop environment.


## 2. Problem Statement

**Current Problems**

* Manual invoice data entry is time-consuming and prone to errors in crucial information such as vendors, dates, or amounts.
* Documents are often scattered in emails or folders, making it difficult to search, audit, and track statuses.
* Lack of overall visibility makes it hard for the finance team to know exactly which documents have errors and require manual intervention.
* The process is prone to bottlenecks during peak periods at the end of the month or quarter when invoice volumes spike.

**Proposed Solution**

* Build a direct and secure document upload portal via presigned URLs.
* Operate a fully automated serverless workflow, integrating retry mechanisms, status tracking, and Dead Letter Queues (DLQ).
* Automatically extract key data fields using Textract and Bedrock, then store metadata in DynamoDB and JSON results in S3.

**Benefits & Return on Investment (ROI)**

* Minimize manual data entry, enhance status visibility, and provide structured data outputs.
* The system automatically sends alerts when errors are detected or extraction confidence is low, optimizing review time.


## 3. Solution Architecture

The overall architecture of DocuFlow AI is structured into 5 specialized layers: frontend/auth, ingestion/API, workflow processing, data storage/analytics, and observability/security.

**Core System Workflow & AI Extraction**

* **Event Ingestion:** When a user uploads a file to the S3 Raw Bucket, an event is sent via EventBridge to an SQS queue.
* **Workflow Orchestration:** Lambda triggers a Step Functions Standard Workflow to orchestrate the entire document lifecycle.
* **Raw Extraction (OCR):** Amazon Textract (AnalyzeExpense) reads and extracts raw information fields from invoices/receipts.
* **Intelligent Standardization (GenAI):** Amazon Bedrock receives raw data, classifies, and standardizes the format into a single JSON schema.
* **Result Validation:** Lambda performs JSON format checks, calculates the confidence score, and updates the status accordingly.


## 4. Technical Implementation (Focus on AI Extraction & Classification)

The AI Extraction & Classification Module is handled by Member 3, primarily working with Textract, Bedrock, and Lambda.

**AI Component Design**

* **Raw Data Storage:** Must retain all raw results from Textract in the `processed` folder on S3 for debugging purposes when data discrepancies occur.
* **Prompt Design for Bedrock:** Bedrock only accepts reduced raw fields as input for optimization. The prompt must strictly request a valid JSON format according to the schema, absolutely avoiding markdown or explanatory text.
* **Confidence Policy:** Document status is granted as `EXTRACTED` only when `confidenceScore >= 0.80` and the system recognizes all mandatory data fields.
* **Manual Review Redirection:** The system will flag as `REVIEW_REQUIRED` if the confidence score is `< 0.80` or when extraction is missing the vendor name (`vendorName`) and total amount (`totalAmount`).
* **Error Handling:** If Bedrock or Textract encounters a temporary error, Step Functions will initiate retries using a backoff mechanism; if the maximum number of attempts is exceeded, the status will change to `FAILED`.


## 5. Timeline & Milestones

The plan is distributed over 12 weeks with focus objectives:

* **Week 1:** Agree on scope, data contract, overall architecture, and module assignments for each member.
* **Week 4:** Complete the skeleton framework for EventBridge, SQS, Job Starter services, and the Step Functions workflow.
* **Week 5:** Successfully integrate the Textract flow, ensuring raw data extraction capabilities from sample sets.
* **Week 6:** Apply Bedrock to standardize data, validate JSON formats, and store in the S3 `processed` bucket.
* **Week 8:** Finalize error handling mechanisms, DLQs, retry features, and set up SNS alerts for `FAILED` or `REVIEW_REQUIRED` cases.
* **Week 11-12:** Complete E2E testing, prepare demo scripts, finalize runbook documentation, and verify resource clean-up scripts.


## 6. Cost Control & Budgeting

* **Resource Limits:** Constrain file sizes, number of processed pages, and only use about 5-10 sample invoices/receipts during the demo.
* **Model Optimization:** Prioritize low-cost Bedrock models and verify model availability in the account/region before deployment.
* **Budget Alerts:** Set up AWS Budgets alerts at $5 and $10 cost thresholds.
* **Resource Lifecycle:** Require configuring S3 lifecycles or using cleanup scripts to clear stored files after the workshop ends, avoiding ongoing maintenance fees.


## 7. Risk Assessment (AI & Extraction Module)

| Risk | Impact | Mitigation Strategy |
| --- | --- | --- |
| Textract misreads due to blurry images or weird formats | System outputs incorrect or missing data fields | Use sharp sample documents, apply confidence thresholds and `REVIEW_REQUIRED` status. |
| Bedrock outputs malformed JSON data | Causes data parsing errors at the Lambda layer | Write strict prompts, enforce JSON schema validation, and handle retries/fallbacks. |
| Region does not support Bedrock model | The entire AI standardization flow is interrupted | Verify region early on, prepare backup models or cross-region deployment plans. |


## 8. Expected Outcomes (Definition of Done)

* Users can successfully log in and upload sample invoice/receipt files to the system.
* The uploaded files trigger the Step Functions chain to run smoothly through: Textract, Bedrock, JSON validation, and storage.
* The `result.json` data is correctly formatted and stored in the S3 processed bucket according to the data contract.
* The DynamoDB table accurately records the metadata and current status of the document.
* Test cases prove the system works correctly for at least one `EXTRACTED` scenario and one exception scenario (`REVIEW_REQUIRED` or `FAILED`).