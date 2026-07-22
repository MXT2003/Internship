---
title: "Week 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

- Strengthen cloud security, logging, cost management, and application operations knowledge.
- Connect AWS learning outcomes with the requirements of an incident response management system.
- Prepare a review mindset for documentation and end-user flow testing.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **Incident management research**<br>- **Work:** I researched the incident lifecycle: creation, severity classification, status update, assignment, timeline tracking, evidence attachment, and report generation. This was still preparation, not IRMS implementation. I focused on business logic so later API and DynamoDB design would not miss important entities.<br>- **Knowledge:** An incident management system needs workflow understanding before service selection.<br>- **Result:** I had a list of core features to discuss with the team before starting the project.<br>- **Lesson:** If the design starts only from AWS services and ignores workflow, important functions may be missed. | 15/06/2026 | 15/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **Data model preparation**<br>- **Work:** I drafted possible entities such as incident, timeline entry, evidence metadata, user, and report. I thought in terms of access patterns: list incidents by status, get details by incidentId, retrieve timeline/evidence by incidentId, and store metadata for quick lookup. This was preparation only, not final design.<br>- **Knowledge:** NoSQL data modeling starts from read/write patterns rather than only table names.<br>- **Result:** I had a draft to bring into team discussion about DynamoDB.<br>- **Lesson:** The model should not become too complex before the demo scope is confirmed. | 16/06/2026 | 16/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **API design preparation**<br>- **Work:** I wrote possible API routes for creating incidents, listing incidents, updating status, adding timeline entries, generating evidence presigned URLs, and creating reports. I also noted that request/response formats should be simple, consistent, and easy for the frontend to test. This saved time for the later implementation phase.<br>- **Knowledge:** The API contract connects frontend and backend, so it should be aligned early.<br>- **Result:** I had a draft endpoint list for team discussion and adjustment.<br>- **Lesson:** Too many routes beyond demo scope would make testing and documentation heavier. | 17/06/2026 | 17/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **Report and alert flow preparation**<br>- **Work:** I reviewed how a system could generate reports periodically or react to security events. I connected EventBridge with scheduled reports, SNS with notifications, Lambda with processing logic, and S3 with result storage. I also noted that any AI provider secret must stay in Secrets Manager, not in frontend code or the repository.<br>- **Knowledge:** Report and alert flows are often background tasks and fit event-driven serverless design.<br>- **Result:** I had an early direction for report generation and alert automation.<br>- **Lesson:** The report must clearly separate implemented work from proposed extensions. | 18/06/2026 | 18/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Project preparation summary**<br>- **Work:** I combined notes from previous weeks into a pre-project checklist: authentication, API Gateway, Lambda handler, DynamoDB access patterns, S3 evidence, EventBridge/SNS, CloudWatch logs, frontend integration, and deployment. I also prepared questions for team discussion about scope, roles, and timeline.<br>- **Knowledge:** Preparation helps the project start faster, but final decisions still require team alignment.<br>- **Result:** I had a technical checklist and discussion questions for the IRMS start in Week 11.<br>- **Lesson:** The worklog must state clearly that this week was research and preparation, not implementation. | 19/06/2026 | 19/06/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 9 Achievements:

- **15/06/2026:** I had a list of core features to discuss with the team before starting the project. If the design starts only from AWS services and ignores workflow, important functions may be missed.
- **16/06/2026:** I had a draft to bring into team discussion about DynamoDB. The model should not become too complex before the demo scope is confirmed.
- **17/06/2026:** I had a draft endpoint list for team discussion and adjustment. Too many routes beyond demo scope would make testing and documentation heavier.
- **18/06/2026:** I had an early direction for report generation and alert automation. The report must clearly separate implemented work from proposed extensions.
- **19/06/2026:** I had a technical checklist and discussion questions for the IRMS start in Week 11. The worklog must state clearly that this week was research and preparation, not implementation.
