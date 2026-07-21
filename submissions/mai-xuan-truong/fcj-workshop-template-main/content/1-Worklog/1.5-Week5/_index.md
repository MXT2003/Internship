---
title: "Week 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

**Timeline:** 18/5 → 22/5 (5 working days)

## Day 1 - 18/5: Cognito study

**Work completed:** I studied Amazon Cognito User Pools, App Clients, hosted UI, JWT tokens, and the difference between authentication and authorization. I focused on how a user logs in, receives a token, and uses that token to call protected APIs. I also reviewed common JWT claims such as `sub`, `email`, groups, and expiration time.

**Knowledge learned:** Cognito provides user authentication without requiring the application to build the full login and password system from scratch.

**Result achieved:** I understood the roles of User Pool, App Client, and JWT in a serverless architecture.

**Difficulty and lesson learned:** Client secrets must not be placed in frontend code, and expired-token errors need clear handling.

## Day 2 - 19/5: API Gateway study

**Work completed:** I reviewed REST APIs, routes, methods, stages, CORS, request/response format, and Lambda integration. I paid close attention to preflight requests because frontend-backend integration often fails at this point. I also studied how an authorizer can be attached to routes so only valid JWT requests continue to the backend.

**Knowledge learned:** API Gateway is the entry point of serverless backend services and can handle routing, authentication, CORS, and throttling.

**Result achieved:** I learned to check routes, methods, stage deployment, and response headers when an API fails.

**Difficulty and lesson learned:** After API Gateway configuration changes, the stage often needs to be redeployed.

## Day 3 - 20/5: Lambda study

**Work completed:** I read about Lambda handlers, event objects, context, environment variables, IAM roles, and CloudWatch Logs. I compared Lambda with EC2: Lambda removes server operation but requires stateless code and clear timeout/error handling. I also noted how separate functions could handle CRUD, evidence upload, or report generation.

**Knowledge learned:** Lambda fits request-based or event-driven tasks, but it needs good logs because there is no server to SSH into.

**Result achieved:** I understood how Lambda receives events from API Gateway and returns responses to the frontend.

**Difficulty and lesson learned:** Secrets should not be hard-coded; configuration should use environment variables or Secrets Manager.

## Day 4 - 21/5: DynamoDB study

**Work completed:** I studied partition keys, sort keys, items, query, scan, and NoSQL design by access pattern. Unlike relational databases, DynamoDB requires thinking about how the application will read and write data before designing tables. I drafted simple examples for incidents, timeline entries, and evidence metadata.

**Knowledge learned:** DynamoDB works well when access patterns are clear, but poor key design makes queries difficult and costly.

**Result achieved:** I learned the difference between query and scan and why scan should not be used frequently in APIs.

**Difficulty and lesson learned:** NoSQL data modeling must be discussed together with API design, not left until the end.

## Day 5 - 22/5: Service mapping notes

**Work completed:** I created a note connecting Cognito, API Gateway, Lambda, DynamoDB, S3, and CloudWatch into a basic serverless model. The goal was to understand a request passing from frontend to API Gateway, being checked by Cognito Authorizer, processed by Lambda, stored in DynamoDB/S3, and logged in CloudWatch. This was preparation knowledge, not the start of IRMS implementation.

**Knowledge learned:** A real serverless system needs multiple services to work together instead of treating each service separately.

**Result achieved:** I created my first service-mapping note for later team discussion.

**Difficulty and lesson learned:** The report must clearly separate preparation knowledge from features that were actually implemented.
