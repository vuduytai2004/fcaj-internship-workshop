---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
### Week 11 Objectives:

* Develop Lambda functions for the AI flow (Textract Parser, AI Proxy, Confidence + Status).
* Set up SNS and SES to send email notifications to users.
* Execute testing and save evidence for various scenarios.
* Finalize the AI flow documentation and review the outcomes.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Create and write code for Textract Parser Lambda to process raw output from Textract Analyze Expense | 06/29/2026 | 06/29/2026 | |
| 3 | Create and write code for AI Proxy Lambda to call External AI API via HTTPS | 06/30/2026 | 06/30/2026 | |
| 4 | Create and write code for Confidence + Status Lambda to handle confidence score calculation and determine document status (EXTRACTED/REVIEW_REQUIRED/FAILED) | 07/01/2026 | 07/01/2026 | |
| 5 | Run tests and save evidence for Lambda scenarios (clear/blurry files, missing fields, Invalid JSON) | 07/02/2026 | 07/02/2026 | |
| 6 | Complete AI flow documentation: verify Lambda outputs match JSON Schema and check Definition of Done | 07/03/2026 | 07/03/2026 | |
| 7 | Set up SNS and SES to send document status email notifications to users | 07/04/2026 | 07/04/2026 | |


### Week 11 Achievements:

* Successfully created and coded the Textract Parser Lambda to process raw output.
* Completed the AI Proxy Lambda code, enabling stable External AI API calls via HTTPS.
* Developed the Confidence + Status Lambda, accurately handling confidence scoring logic and document status decisions.
* Successfully ran tests across various Lambda scenarios (blurry files, missing fields, invalid JSON) and archived comprehensive evidence.
* Finalized all AI flow documentation, ensuring outputs strictly matched the JSON Schema and fulfilled the Definition of Done.
* Successfully configured SNS and SES to automatically send email notifications to users.
