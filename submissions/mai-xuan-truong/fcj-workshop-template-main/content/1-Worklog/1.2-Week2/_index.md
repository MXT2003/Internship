---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

- Strengthen knowledge of VPC, EC2 networking, RDS, and basic serverless components.
- Understand how networking, compute, database, and storage layers work together in AWS architecture.
- Create a checklist for common lab issues and resource cleanup.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **VPC fundamentals**<br>- **Work:** I studied Amazon VPC, subnets, route tables, Internet Gateway, NAT Gateway, Security Groups, and Network ACLs. I treated the VPC as a private network on AWS and practiced separating public and private workloads. During the lab, I created a VPC, split it into subnets, attached an Internet Gateway, and updated route tables to understand how traffic moved.<br>- **Knowledge:** Network design decides which workloads are public, which ones remain private, and how application layers communicate.<br>- **Result:** I understood the role of route tables, gateways, and security groups in allowing or blocking traffic.<br>- **Lesson:** If routing or security rules are wrong, the symptom can look like an application error, so debugging must be done layer by layer. | 27/04/2026 | 27/04/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **EC2 and networking lab**<br>- **Work:** I created an EC2 instance inside the VPC, attached a security group, and tested access from my local machine. I reviewed common issues such as wrong key files, closed ports, incorrect subnet placement, or a route table not pointing to the Internet Gateway. I also read about Session Manager as a safer alternative to direct SSH access.<br>- **Knowledge:** Security Groups protect instances, while subnet and route-table design control the wider network path.<br>- **Result:** I became more confident in checking why an EC2 instance could not be reached from outside.<br>- **Lesson:** Ports should not be opened just to make a lab work; every rule needs a clear purpose and source range. | 28/04/2026 | 28/04/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **RDS and database**<br>- **Work:** I studied Amazon RDS as a managed relational database service. In the lab, I reviewed engine choices, DB subnet groups, dedicated database security groups, backups, snapshots, and connection endpoints. I paid attention to the fact that RDS should usually stay in private subnets and only allow access from the application layer.<br>- **Knowledge:** Managed databases reduce operational work such as patching, backup, and restore, but network and security design are still my responsibility.<br>- **Result:** I understood how applications connect to RDS through endpoints and why app and database security groups should be separated.<br>- **Lesson:** Database resources can generate cost quickly, so instances and snapshots must be checked after a lab. | 29/04/2026 | 29/04/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **Serverless introduction**<br>- **Work:** I started reading about Lambda, API Gateway, DynamoDB, and CloudWatch Logs. The goal was to understand why modern systems can process requests or events without keeping servers running continuously. I compared EC2 and Lambda: EC2 offers more control but requires server operation, while Lambda is lighter for small APIs and event-driven tasks.<br>- **Knowledge:** Serverless works well when the workload can be split into stateless functions that scale with requests.<br>- **Result:** I built a foundation for later weeks involving API Gateway, Lambda, and DynamoDB.<br>- **Lesson:** Serverless still requires good design, timeout handling, and logging; it is not suitable for every workload. | 30/04/2026 | 30/04/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Learning summary**<br>- **Work:** I collected notes from IAM, S3, EC2, VPC, RDS, and serverless into a comparison table. For each service, I wrote its purpose, important settings, common mistakes, and cleanup steps. I also marked services that could be useful in a final project: authentication, API layer, compute, database, storage, monitoring, and cost management.<br>- **Knowledge:** AWS services rarely stand alone; real systems combine multiple services into one architecture.<br>- **Result:** I had cleaner notes to reuse later in the Worklog and Workshop.<br>- **Lesson:** Writing notes immediately after a lab preserves real issues better than only saving links. | 01/05/2026 | 01/05/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 2 Achievements:

- **27/04/2026:** I understood the role of route tables, gateways, and security groups in allowing or blocking traffic. If routing or security rules are wrong, the symptom can look like an application error, so debugging must be done layer by layer.
- **28/04/2026:** I became more confident in checking why an EC2 instance could not be reached from outside. Ports should not be opened just to make a lab work; every rule needs a clear purpose and source range.
- **29/04/2026:** I understood how applications connect to RDS through endpoints and why app and database security groups should be separated. Database resources can generate cost quickly, so instances and snapshots must be checked after a lab.
- **30/04/2026:** I built a foundation for later weeks involving API Gateway, Lambda, and DynamoDB. Serverless still requires good design, timeout handling, and logging; it is not suitable for every workload.
- **01/05/2026:** I had cleaner notes to reuse later in the Worklog and Workshop. Writing notes immediately after a lab preserves real issues better than only saving links.
