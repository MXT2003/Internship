---
title: "Week 1 Worklog"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives:

- Get familiar with AWS Console, the internship account, and basic account security settings.
- Practice foundational services such as IAM, S3, and EC2 with cost control in mind.
- Build the habit of documenting work, checking resources, and cleaning up after each lab.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **AWS account setup**<br>- **Work:** I started by preparing the AWS learning environment, checking access, and getting familiar with the AWS Console. Because this was the beginning of the internship, I spent time reviewing billing, region selection, and basic account security. During account activation, I ran into several access-related issues, so I reviewed the verification steps and how AWS handles account status. I selected `ap-southeast-1` as the main region for later labs.<br>- **Knowledge:** Account management, billing alerts, and root account protection are important foundations before working with AWS services.<br>- **Result:** The learning environment became stable enough for the first AWS labs.<br>- **Lesson:** The root account should not be used for daily work, and cost alerts should be enabled early. | 20/04/2026 | 20/04/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **IAM fundamentals**<br>- **Work:** I studied IAM users, groups, policies, roles, MFA, and least privilege. Instead of only following the lab steps, I practiced reading JSON policies to understand which actions were allowed. I also noted the difference between users for real people, roles for services or temporary access, and groups for managing permissions across multiple users.<br>- **Knowledge:** IAM is the central access-control layer in AWS, and policies should be based on real needs instead of broad permissions.<br>- **Result:** I understood permission design better and why services such as Lambda or EC2 need their own IAM roles.<br>- **Lesson:** Start with minimum permissions and only add more access when there is a clear reason. | 21/04/2026 | 21/04/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **S3 and storage basics**<br>- **Work:** I practiced creating S3 buckets, uploading objects, checking block public access, enabling versioning, and cleaning up after the lab. I paid extra attention to access control because S3 can become public by mistake if bucket policies and object permissions are not understood. I also read about static website hosting and object keys.<br>- **Knowledge:** S3 is object storage, not a traditional folder system; access control and lifecycle should be designed carefully.<br>- **Result:** I could create and review buckets more safely and clean up resources after use.<br>- **Lesson:** Public access should never be enabled casually; if public delivery is needed, it should be designed properly with CloudFront/WAF. | 22/04/2026 | 22/04/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **EC2 introduction**<br>- **Work:** I studied EC2 instances, AMIs, instance types, key pairs, security groups, and SSH access to Linux servers. The hands-on part helped me understand EC2 as a cloud server surrounded by AWS networking and permission settings. I also reviewed common mistakes such as using the wrong key pair, leaving port 22 closed, or opening security groups too broadly.<br>- **Knowledge:** EC2 feels close to a traditional server, but its security and cost depend heavily on networking and lifecycle configuration.<br>- **Result:** I understood the basic flow of creating, connecting to, checking, and deleting an EC2 instance.<br>- **Lesson:** Avoid opening SSH to the whole Internet and stop/delete instances when they are no longer needed. | 23/04/2026 | 23/04/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Weekly review and cost check**<br>- **Work:** I summarized the first week, checked resources across regions, and reviewed billing to avoid forgotten services. This helped me notice that lab resources can still generate cost if they are created in another region or not fully deleted. I wrote down a cleanup routine: review Billing, check each region, delete running resources, and record the cause.<br>- **Knowledge:** AWS cost can come from resources outside the current region, so cleanup must include multiple regions and service types.<br>- **Result:** I created my first cleanup checklist and started writing worklog notes in a clearer structure.<br>- **Lesson:** Learning AWS must go together with cost checking and resource cleanup habits. | 24/04/2026 | 24/04/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 1 Achievements:

- **20/04/2026:** The learning environment became stable enough for the first AWS labs. The root account should not be used for daily work, and cost alerts should be enabled early.
- **21/04/2026:** I understood permission design better and why services such as Lambda or EC2 need their own IAM roles. Start with minimum permissions and only add more access when there is a clear reason.
- **22/04/2026:** I could create and review buckets more safely and clean up resources after use. Public access should never be enabled casually; if public delivery is needed, it should be designed properly with CloudFront/WAF.
- **23/04/2026:** I understood the basic flow of creating, connecting to, checking, and deleting an EC2 instance. Avoid opening SSH to the whole Internet and stop/delete instances when they are no longer needed.
- **24/04/2026:** I created my first cleanup checklist and started writing worklog notes in a clearer structure. Learning AWS must go together with cost checking and resource cleanup habits.
