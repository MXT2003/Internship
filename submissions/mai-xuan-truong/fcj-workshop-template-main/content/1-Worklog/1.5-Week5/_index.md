---
title: "Week 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

- Focus on core serverless services: Cognito, API Gateway, Lambda, DynamoDB, and S3.
- Understand authentication, API contracts, business logic processing, and secure file storage.
- Prepare the technical foundation for my AWS infrastructure work in IRMS.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **Cognito study**<br>- **Work:** I studied Amazon Cognito User Pools, App Clients, hosted UI, JWT tokens, and the difference between authentication and authorization. I focused on how a user logs in, receives a token, and uses that token to call protected APIs. I also reviewed common JWT claims such as `sub`, `email`, groups, and expiration time.<br>- **Knowledge:** Cognito provides user authentication without requiring the application to build the full login and password system from scratch.<br>- **Result:** I understood the roles of User Pool, App Client, and JWT in a serverless architecture.<br>- **Lesson:** Client secrets must not be placed in frontend code, and expired-token errors need clear handling. | 18/05/2026 | 18/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **API Gateway study**<br>- **Work:** I reviewed REST APIs, routes, methods, stages, CORS, request/response format, and Lambda integration. I paid close attention to preflight requests because frontend-backend integration often fails at this point. I also studied how an authorizer can be attached to routes so only valid JWT requests continue to the backend.<br>- **Knowledge:** API Gateway is the entry point of serverless backend services and can handle routing, authentication, CORS, and throttling.<br>- **Result:** I learned to check routes, methods, stage deployment, and response headers when an API fails.<br>- **Lesson:** After API Gateway configuration changes, the stage often needs to be redeployed. | 19/05/2026 | 19/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **Lambda study**<br>- **Work:** I read about Lambda handlers, event objects, context, environment variables, IAM roles, and CloudWatch Logs. I compared Lambda with EC2: Lambda removes server operation but requires stateless code and clear timeout/error handling. I also noted how separate functions could handle CRUD, evidence upload, or report generation.<br>- **Knowledge:** Lambda fits request-based or event-driven tasks, but it needs good logs because there is no server to SSH into.<br>- **Result:** I understood how Lambda receives events from API Gateway and returns responses to the frontend.<br>- **Lesson:** Secrets should not be hard-coded; configuration should use environment variables or Secrets Manager. | 20/05/2026 | 20/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **DynamoDB study**<br>- **Work:** I studied partition keys, sort keys, items, query, scan, and NoSQL design by access pattern. Unlike relational databases, DynamoDB requires thinking about how the application will read and write data before designing tables. I drafted simple examples for incidents, timeline entries, and evidence metadata.<br>- **Knowledge:** DynamoDB works well when access patterns are clear, but poor key design makes queries difficult and costly.<br>- **Result:** I learned the difference between query and scan and why scan should not be used frequently in APIs.<br>- **Lesson:** NoSQL data modeling must be discussed together with API design, not left until the end. | 21/05/2026 | 21/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Service mapping notes**<br>- **Work:** I created a note connecting Cognito, API Gateway, Lambda, DynamoDB, S3, and CloudWatch into a basic serverless model. The goal was to understand a request passing from frontend to API Gateway, being checked by Cognito Authorizer, processed by Lambda, stored in DynamoDB/S3, and logged in CloudWatch. This was preparation knowledge, not the start of IRMS implementation.<br>- **Knowledge:** A real serverless system needs multiple services to work together instead of treating each service separately.<br>- **Result:** I created my first service-mapping note for later team discussion.<br>- **Lesson:** The report must clearly separate preparation knowledge from features that were actually implemented. | 22/05/2026 | 22/05/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 5 Achievements:

- **18/05/2026:** I understood the roles of User Pool, App Client, and JWT in a serverless architecture. Client secrets must not be placed in frontend code, and expired-token errors need clear handling.
- **19/05/2026:** I learned to check routes, methods, stage deployment, and response headers when an API fails. After API Gateway configuration changes, the stage often needs to be redeployed.
- **20/05/2026:** I understood how Lambda receives events from API Gateway and returns responses to the frontend. Secrets should not be hard-coded; configuration should use environment variables or Secrets Manager.
- **21/05/2026:** I learned the difference between query and scan and why scan should not be used frequently in APIs. NoSQL data modeling must be discussed together with API design, not left until the end.
- **22/05/2026:** I created my first service-mapping note for later team discussion. The report must clearly separate preparation knowledge from features that were actually implemented.
