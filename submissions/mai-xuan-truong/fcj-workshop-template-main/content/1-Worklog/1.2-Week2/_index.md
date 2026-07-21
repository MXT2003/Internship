---
title: "Week 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

**Timeline:** 27/4 → 1/5 (5 working days)

## Day 1 - 27/4: VPC fundamentals

**Work completed:** I studied Amazon VPC, subnets, route tables, Internet Gateway, NAT Gateway, Security Groups, and Network ACLs. I treated the VPC as a private network on AWS and practiced separating public and private workloads. During the lab, I created a VPC, split it into subnets, attached an Internet Gateway, and updated route tables to understand how traffic moved.

**Knowledge learned:** Network design decides which workloads are public, which ones remain private, and how application layers communicate.

**Result achieved:** I understood the role of route tables, gateways, and security groups in allowing or blocking traffic.

**Difficulty and lesson learned:** If routing or security rules are wrong, the symptom can look like an application error, so debugging must be done layer by layer.

## Day 2 - 28/4: EC2 and networking lab

**Work completed:** I created an EC2 instance inside the VPC, attached a security group, and tested access from my local machine. I reviewed common issues such as wrong key files, closed ports, incorrect subnet placement, or a route table not pointing to the Internet Gateway. I also read about Session Manager as a safer alternative to direct SSH access.

**Knowledge learned:** Security Groups protect instances, while subnet and route-table design control the wider network path.

**Result achieved:** I became more confident in checking why an EC2 instance could not be reached from outside.

**Difficulty and lesson learned:** Ports should not be opened just to make a lab work; every rule needs a clear purpose and source range.

## Day 3 - 29/4: RDS and database

**Work completed:** I studied Amazon RDS as a managed relational database service. In the lab, I reviewed engine choices, DB subnet groups, dedicated database security groups, backups, snapshots, and connection endpoints. I paid attention to the fact that RDS should usually stay in private subnets and only allow access from the application layer.

**Knowledge learned:** Managed databases reduce operational work such as patching, backup, and restore, but network and security design are still my responsibility.

**Result achieved:** I understood how applications connect to RDS through endpoints and why app and database security groups should be separated.

**Difficulty and lesson learned:** Database resources can generate cost quickly, so instances and snapshots must be checked after a lab.

## Day 4 - 30/4: Serverless introduction

**Work completed:** I started reading about Lambda, API Gateway, DynamoDB, and CloudWatch Logs. The goal was to understand why modern systems can process requests or events without keeping servers running continuously. I compared EC2 and Lambda: EC2 offers more control but requires server operation, while Lambda is lighter for small APIs and event-driven tasks.

**Knowledge learned:** Serverless works well when the workload can be split into stateless functions that scale with requests.

**Result achieved:** I built a foundation for later weeks involving API Gateway, Lambda, and DynamoDB.

**Difficulty and lesson learned:** Serverless still requires good design, timeout handling, and logging; it is not suitable for every workload.

## Day 5 - 1/5: Learning summary

**Work completed:** I collected notes from IAM, S3, EC2, VPC, RDS, and serverless into a comparison table. For each service, I wrote its purpose, important settings, common mistakes, and cleanup steps. I also marked services that could be useful in a final project: authentication, API layer, compute, database, storage, monitoring, and cost management.

**Knowledge learned:** AWS services rarely stand alone; real systems combine multiple services into one architecture.

**Result achieved:** I had cleaner notes to reuse later in the Worklog and Workshop.

**Difficulty and lesson learned:** Writing notes immediately after a lab preserves real issues better than only saving links.
