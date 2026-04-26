---
title: "Week 1 Worklog"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The following information is for reference only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 1 Objectives (20/04/2026 - 25/04/2026):

* Create and activate an AWS account for hands-on practice.
* Complete core tasks in the credit-earning program.
* Learn cost control basics and resource checks across regions.
* Start writing and publishing weekly worklog on GitHub.

### Daily Worklog:

| Day | Activities | Outcome |
| --- | --- | --- |
| Day 1 (20/04/2026) | Tried creating an AWS account. Account was **suspended**, so onboarding could not continue. | Account creation failed; identified account verification as the main blocker. |
| Day 2 (21/04/2026) | Continued account setup troubleshooting. After multiple attempts, used a rented phone number for verification and finally activated the account. Started the 5-task challenge for 100$ credit and completed **EC2**, **AWS Budgets**, and **AWS Lambda**. | AWS account activated; 3/5 tasks completed. |
| Day 3 (22/04/2026) | Continued with remaining tasks: **RDS Database** and **Amazon Bedrock**. | Completed all 5 tasks planned for the week. |
| Day 4 (23/04/2026) | Studied how to write a proper worklog: structure, daily progress format, issue logging, and lessons learned section. | Established a clear format for writing internship worklogs. |
| Day 5 (24/04/2026) | Checked billing and found unexpected charge on **Relational Database Service: 8.78$** even after deleting main resources. Audited all services and discovered leftover Aurora/RDS resources in **N. California** region. Deleted them immediately. | Stopped extra cost leakage; learned to validate resources in every region used during labs. |
| Day 6 (25/04/2026) | Practiced writing Week 1 worklog and uploaded updates to GitHub. | Completed Week 1 worklog and prepared for Week 2. |

### Week 1 Achievements:

* Successfully activated AWS account after resolving initial suspension issue.
* Completed the 5-task credit track (EC2, AWS Budgets, AWS Lambda, RDS Database, Amazon Bedrock).
* Built initial habit for billing review and cross-region resource cleanup.
* Finished and published Week 1 worklog on GitHub.

### Key Lessons Learned:

* Validate account status early to avoid wasting setup time in the first days.
* After RDS/Aurora labs, always audit resources in **all visited regions**, not only the default one.
* Enable and monitor AWS Budgets early to catch abnormal charges quickly.
* Detailed daily notes make weekly reporting and mentor check-ins much easier.
