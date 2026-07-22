---
title: "Week 3 Worklog"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

- Study ECS, Fargate, ALB, NAT Gateway, and private subnets to broaden cloud architecture knowledge.
- Practice reading architecture diagrams by request flow and service boundaries.
- Organize learning notes into a clearer worklog structure.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **ECS overview**<br>- **Work:** I studied Amazon ECS, clusters, task definitions, services, and container deployment on AWS. Even though the final project later used more serverless services, ECS helped me understand another compute model. I treated a task definition as the description of what the container needs: image, CPU, memory, port mapping, environment variables, and logs.<br>- **Knowledge:** Containers package applications consistently, while ECS manages how they run at scale.<br>- **Result:** I could distinguish clusters, tasks, services, and why services need health checks.<br>- **Lesson:** When documenting architecture, the compute model must be named correctly: containers, serverless functions, or virtual servers. | 04/05/2026 | 04/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **Fargate and ALB**<br>- **Work:** I studied Fargate as a way to run containers without managing EC2 hosts, and I reviewed Application Load Balancer for traffic distribution. I focused on listeners, rules, target groups, and health checks. This helped me understand why production applications need a stable entry point instead of direct access to each server or container.<br>- **Knowledge:** Fargate reduces server management, while ALB helps control and balance incoming traffic.<br>- **Result:** I understood how listeners, target groups, and health checks fit into the request flow.<br>- **Lesson:** A wrong health-check path or security group can make a running service appear unhealthy. | 05/05/2026 | 05/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **NAT and private subnets**<br>- **Work:** I reviewed NAT Gateway and private subnets for workloads that should not be exposed to the Internet. I noted the common case where private workloads need outbound access for package downloads or external calls but should not receive inbound traffic directly. This topic connected strongly with security and cost.<br>- **Knowledge:** Private subnets with NAT reduce inbound attack surface while still allowing controlled outbound traffic.<br>- **Result:** I understood the difference between Internet Gateway and NAT Gateway more clearly.<br>- **Lesson:** NAT Gateway can generate cost, so it should be deleted after labs when it is no longer needed. | 06/05/2026 | 06/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **Cloud architecture reading**<br>- **Work:** I read sample AWS architectures and broke them into familiar layers: DNS/CDN, edge security, API layer, compute, database, storage, messaging, and monitoring. This approach made complex diagrams easier to read. I also started noting which services are global or edge-based and which are regional.<br>- **Knowledge:** Cloud architecture should be read through request flow and service boundaries, not only by looking at service icons.<br>- **Result:** I gained a better method for drawing and explaining the later IRMS architecture.<br>- **Lesson:** A diagram without arrows and clear labels can make the real data flow difficult to understand. | 07/05/2026 | 07/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Organizing workshop notes**<br>- **Work:** I began converting scattered lab notes into structured worklog entries. For each day, I tried to separate work completed, knowledge learned, result, and difficulty. I also edited overly personal or very long sentences into a more professional internship-report tone.<br>- **Knowledge:** A worklog should show learning progress, problems, and lessons, not only list actions.<br>- **Result:** I created a more stable note format for the following weeks.<br>- **Lesson:** If notes are edited too late, useful details can be lost or mixed with information that should not be published. | 08/05/2026 | 08/05/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 3 Achievements:

- **04/05/2026:** I could distinguish clusters, tasks, services, and why services need health checks. When documenting architecture, the compute model must be named correctly: containers, serverless functions, or virtual servers.
- **05/05/2026:** I understood how listeners, target groups, and health checks fit into the request flow. A wrong health-check path or security group can make a running service appear unhealthy.
- **06/05/2026:** I understood the difference between Internet Gateway and NAT Gateway more clearly. NAT Gateway can generate cost, so it should be deleted after labs when it is no longer needed.
- **07/05/2026:** I gained a better method for drawing and explaining the later IRMS architecture. A diagram without arrows and clear labels can make the real data flow difficult to understand.
- **08/05/2026:** I created a more stable note format for the following weeks. If notes are edited too late, useful details can be lost or mixed with information that should not be published.
