---
title: "Week 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

**Timeline:** 25/5 → 29/5 (5 working days)

## Day 1 - 25/5: S3 Evidence Store

**Work completed:** I studied S3 more deeply for evidence-file storage. I noted why large files should not pass directly through Lambda and why presigned URLs let the browser upload directly to S3. I also reviewed bucket policy, object keys, versioning, lifecycle rules, and CORS for browser uploads.

**Knowledge learned:** S3 is suitable as an evidence store because it is durable, permission-aware, and supports presigned URL uploads.

**Result achieved:** I understood the flow where Lambda creates a presigned URL, the browser uploads to S3, and metadata is stored separately.

**Difficulty and lesson learned:** Presigned URLs must expire quickly and should not be logged or published.

## Day 2 - 26/5: CloudWatch Logs

**Work completed:** I practiced reading CloudWatch log groups, log streams, timestamps, and error traces. In serverless systems, logs are the main debugging source because there is no fixed server to access. I wrote notes about logging request IDs, action names, and incident IDs while avoiding sensitive values such as tokens, passwords, or full presigned URLs.

**Knowledge learned:** CloudWatch helps debug Lambda/API flows, but logs must be written carefully to avoid leaking sensitive data.

**Result achieved:** I learned to search logs by time and read basic stack traces.

**Difficulty and lesson learned:** Good logs provide enough context for debugging without exposing credentials or private data.

## Day 3 - 27/5: EventBridge

**Work completed:** I studied EventBridge event buses, rules, schedules, and event-driven automation. I reviewed two use cases: reacting to AWS service events and running scheduled tasks. I connected this knowledge to possible scheduled reports and security-event processing.

**Knowledge learned:** EventBridge decouples background tasks from direct user requests and makes a system more flexible.

**Result achieved:** I understood how a rule can trigger Lambda or pass events to another service.

**Difficulty and lesson learned:** Event names and rule names need to be clear so debugging does not become confusing later.

## Day 4 - 28/5: SNS notification

**Work completed:** I studied SNS topics, subscriptions, and message publishing to email or other endpoints. I treated SNS as a simple publish/subscribe layer for sending notifications from Lambda to users or operators. I also noted that real email addresses should not be published in workshop examples unless necessary.

**Knowledge learned:** SNS separates event detection from notification delivery and prevents Lambda from handling too many channels directly.

**Result achieved:** I understood basic topic/subscription/publish behavior.

**Difficulty and lesson learned:** Notifications should contain enough context but must not include sensitive internal data.

## Day 5 - 29/5: Security notes

**Work completed:** I summarized security lessons from IAM, S3, Lambda, CloudWatch, EventBridge, and SNS. The main points were: do not hard-code credentials, do not push secrets to GitHub, restrict IAM permissions, check public access, control log content, and clean up resources after labs. I also created a personal security checklist for future workshop writing.

**Knowledge learned:** Security appears in every configuration and every documentation example, not only in one separate service.

**Result achieved:** I had a personal checklist for labs and the final project.

**Difficulty and lesson learned:** Published reports must remove login emails, passwords, access keys, secret keys, tokens, and API keys.
