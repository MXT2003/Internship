---
title: "Week 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

- Practice AWS SAM and describe serverless infrastructure through templates.
- Get familiar with validate, build, deploy, and troubleshooting deployment errors.
- Document naming, IAM permission, and environment-variable practices for the project.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **S3 Evidence Store**<br>- **Work:** I studied S3 more deeply for evidence-file storage. I noted why large files should not pass directly through Lambda and why presigned URLs let the browser upload directly to S3. I also reviewed bucket policy, object keys, versioning, lifecycle rules, and CORS for browser uploads.<br>- **Knowledge:** S3 is suitable as an evidence store because it is durable, permission-aware, and supports presigned URL uploads.<br>- **Result:** I understood the flow where Lambda creates a presigned URL, the browser uploads to S3, and metadata is stored separately.<br>- **Lesson:** Presigned URLs must expire quickly and should not be logged or published. | 25/05/2026 | 25/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **CloudWatch Logs**<br>- **Work:** I practiced reading CloudWatch log groups, log streams, timestamps, and error traces. In serverless systems, logs are the main debugging source because there is no fixed server to access. I wrote notes about logging request IDs, action names, and incident IDs while avoiding sensitive values such as tokens, passwords, or full presigned URLs.<br>- **Knowledge:** CloudWatch helps debug Lambda/API flows, but logs must be written carefully to avoid leaking sensitive data.<br>- **Result:** I learned to search logs by time and read basic stack traces.<br>- **Lesson:** Good logs provide enough context for debugging without exposing credentials or private data. | 26/05/2026 | 26/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **EventBridge**<br>- **Work:** I studied EventBridge event buses, rules, schedules, and event-driven automation. I reviewed two use cases: reacting to AWS service events and running scheduled tasks. I connected this knowledge to possible scheduled reports and security-event processing.<br>- **Knowledge:** EventBridge decouples background tasks from direct user requests and makes a system more flexible.<br>- **Result:** I understood how a rule can trigger Lambda or pass events to another service.<br>- **Lesson:** Event names and rule names need to be clear so debugging does not become confusing later. | 27/05/2026 | 27/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **SNS notification**<br>- **Work:** I studied SNS topics, subscriptions, and message publishing to email or other endpoints. I treated SNS as a simple publish/subscribe layer for sending notifications from Lambda to users or operators. I also noted that real email addresses should not be published in workshop examples unless necessary.<br>- **Knowledge:** SNS separates event detection from notification delivery and prevents Lambda from handling too many channels directly.<br>- **Result:** I understood basic topic/subscription/publish behavior.<br>- **Lesson:** Notifications should contain enough context but must not include sensitive internal data. | 28/05/2026 | 28/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Security notes**<br>- **Work:** I summarized security lessons from IAM, S3, Lambda, CloudWatch, EventBridge, and SNS. The main points were: do not hard-code credentials, do not push secrets to GitHub, restrict IAM permissions, check public access, control log content, and clean up resources after labs. I also created a personal security checklist for future workshop writing.<br>- **Knowledge:** Security appears in every configuration and every documentation example, not only in one separate service.<br>- **Result:** I had a personal checklist for labs and the final project.<br>- **Lesson:** Published reports must remove login emails, passwords, access keys, secret keys, tokens, and API keys. | 29/05/2026 | 29/05/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 6 Achievements:

- **25/05/2026:** I understood the flow where Lambda creates a presigned URL, the browser uploads to S3, and metadata is stored separately. Presigned URLs must expire quickly and should not be logged or published.
- **26/05/2026:** I learned to search logs by time and read basic stack traces. Good logs provide enough context for debugging without exposing credentials or private data.
- **27/05/2026:** I understood how a rule can trigger Lambda or pass events to another service. Event names and rule names need to be clear so debugging does not become confusing later.
- **28/05/2026:** I understood basic topic/subscription/publish behavior. Notifications should contain enough context but must not include sensitive internal data.
- **29/05/2026:** I had a personal checklist for labs and the final project. Published reports must remove login emails, passwords, access keys, secret keys, tokens, and API keys.
