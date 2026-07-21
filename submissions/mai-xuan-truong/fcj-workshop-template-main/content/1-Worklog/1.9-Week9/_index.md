---
title: "Week 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

**Timeline:** 15/6 → 19/6 (5 working days)

## Day 1 - 15/6: Incident management research

**Work completed:** I researched the incident lifecycle: creation, severity classification, status update, assignment, timeline tracking, evidence attachment, and report generation. This was still preparation, not IRMS implementation. I focused on business logic so later API and DynamoDB design would not miss important entities.

**Knowledge learned:** An incident management system needs workflow understanding before service selection.

**Result achieved:** I had a list of core features to discuss with the team before starting the project.

**Difficulty and lesson learned:** If the design starts only from AWS services and ignores workflow, important functions may be missed.

## Day 2 - 16/6: Data model preparation

**Work completed:** I drafted possible entities such as incident, timeline entry, evidence metadata, user, and report. I thought in terms of access patterns: list incidents by status, get details by incidentId, retrieve timeline/evidence by incidentId, and store metadata for quick lookup. This was preparation only, not final design.

**Knowledge learned:** NoSQL data modeling starts from read/write patterns rather than only table names.

**Result achieved:** I had a draft to bring into team discussion about DynamoDB.

**Difficulty and lesson learned:** The model should not become too complex before the demo scope is confirmed.

## Day 3 - 17/6: API design preparation

**Work completed:** I wrote possible API routes for creating incidents, listing incidents, updating status, adding timeline entries, generating evidence presigned URLs, and creating reports. I also noted that request/response formats should be simple, consistent, and easy for the frontend to test. This saved time for the later implementation phase.

**Knowledge learned:** The API contract connects frontend and backend, so it should be aligned early.

**Result achieved:** I had a draft endpoint list for team discussion and adjustment.

**Difficulty and lesson learned:** Too many routes beyond demo scope would make testing and documentation heavier.

## Day 4 - 18/6: Report and alert flow preparation

**Work completed:** I reviewed how a system could generate reports periodically or react to security events. I connected EventBridge with scheduled reports, SNS with notifications, Lambda with processing logic, and S3 with result storage. I also noted that any AI provider secret must stay in Secrets Manager, not in frontend code or the repository.

**Knowledge learned:** Report and alert flows are often background tasks and fit event-driven serverless design.

**Result achieved:** I had an early direction for report generation and alert automation.

**Difficulty and lesson learned:** The report must clearly separate implemented work from proposed extensions.

## Day 5 - 19/6: Project preparation summary

**Work completed:** I combined notes from previous weeks into a pre-project checklist: authentication, API Gateway, Lambda handler, DynamoDB access patterns, S3 evidence, EventBridge/SNS, CloudWatch logs, frontend integration, and deployment. I also prepared questions for team discussion about scope, roles, and timeline.

**Knowledge learned:** Preparation helps the project start faster, but final decisions still require team alignment.

**Result achieved:** I had a technical checklist and discussion questions for the IRMS start in Week 11.

**Difficulty and lesson learned:** The worklog must state clearly that this week was research and preparation, not implementation.
