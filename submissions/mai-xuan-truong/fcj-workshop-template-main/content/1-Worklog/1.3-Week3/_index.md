---
title: "Week 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Timeline:** 4/5 → 8/5 (5 working days)

## Day 1 - 4/5: ECS overview

**Work completed:** I studied Amazon ECS, clusters, task definitions, services, and container deployment on AWS. Even though the final project later used more serverless services, ECS helped me understand another compute model. I treated a task definition as the description of what the container needs: image, CPU, memory, port mapping, environment variables, and logs.

**Knowledge learned:** Containers package applications consistently, while ECS manages how they run at scale.

**Result achieved:** I could distinguish clusters, tasks, services, and why services need health checks.

**Difficulty and lesson learned:** When documenting architecture, the compute model must be named correctly: containers, serverless functions, or virtual servers.

## Day 2 - 5/5: Fargate and ALB

**Work completed:** I studied Fargate as a way to run containers without managing EC2 hosts, and I reviewed Application Load Balancer for traffic distribution. I focused on listeners, rules, target groups, and health checks. This helped me understand why production applications need a stable entry point instead of direct access to each server or container.

**Knowledge learned:** Fargate reduces server management, while ALB helps control and balance incoming traffic.

**Result achieved:** I understood how listeners, target groups, and health checks fit into the request flow.

**Difficulty and lesson learned:** A wrong health-check path or security group can make a running service appear unhealthy.

## Day 3 - 6/5: NAT and private subnets

**Work completed:** I reviewed NAT Gateway and private subnets for workloads that should not be exposed to the Internet. I noted the common case where private workloads need outbound access for package downloads or external calls but should not receive inbound traffic directly. This topic connected strongly with security and cost.

**Knowledge learned:** Private subnets with NAT reduce inbound attack surface while still allowing controlled outbound traffic.

**Result achieved:** I understood the difference between Internet Gateway and NAT Gateway more clearly.

**Difficulty and lesson learned:** NAT Gateway can generate cost, so it should be deleted after labs when it is no longer needed.

## Day 4 - 7/5: Cloud architecture reading

**Work completed:** I read sample AWS architectures and broke them into familiar layers: DNS/CDN, edge security, API layer, compute, database, storage, messaging, and monitoring. This approach made complex diagrams easier to read. I also started noting which services are global or edge-based and which are regional.

**Knowledge learned:** Cloud architecture should be read through request flow and service boundaries, not only by looking at service icons.

**Result achieved:** I gained a better method for drawing and explaining the later IRMS architecture.

**Difficulty and lesson learned:** A diagram without arrows and clear labels can make the real data flow difficult to understand.

## Day 5 - 8/5: Organizing workshop notes

**Work completed:** I began converting scattered lab notes into structured worklog entries. For each day, I tried to separate work completed, knowledge learned, result, and difficulty. I also edited overly personal or very long sentences into a more professional internship-report tone.

**Knowledge learned:** A worklog should show learning progress, problems, and lessons, not only list actions.

**Result achieved:** I created a more stable note format for the following weeks.

**Difficulty and lesson learned:** If notes are edited too late, useful details can be lost or mixed with information that should not be published.
