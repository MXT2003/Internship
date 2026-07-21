---
title: "Week 1"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

**Timeline:** 20/4 → 24/4 (5 working days)

## Day 1 - 20/4: AWS account setup

**Work completed:** I started by preparing the AWS learning environment, checking access, and getting familiar with the AWS Console. Because this was the beginning of the internship, I spent time reviewing billing, region selection, and basic account security. During account activation, I ran into several access-related issues, so I reviewed the verification steps and how AWS handles account status. I selected `ap-southeast-1` as the main region for later labs.

**Knowledge learned:** Account management, billing alerts, and root account protection are important foundations before working with AWS services.

**Result achieved:** The learning environment became stable enough for the first AWS labs.

**Difficulty and lesson learned:** The root account should not be used for daily work, and cost alerts should be enabled early.

## Day 2 - 21/4: IAM fundamentals

**Work completed:** I studied IAM users, groups, policies, roles, MFA, and least privilege. Instead of only following the lab steps, I practiced reading JSON policies to understand which actions were allowed. I also noted the difference between users for real people, roles for services or temporary access, and groups for managing permissions across multiple users.

**Knowledge learned:** IAM is the central access-control layer in AWS, and policies should be based on real needs instead of broad permissions.

**Result achieved:** I understood permission design better and why services such as Lambda or EC2 need their own IAM roles.

**Difficulty and lesson learned:** Start with minimum permissions and only add more access when there is a clear reason.

## Day 3 - 22/4: S3 and storage basics

**Work completed:** I practiced creating S3 buckets, uploading objects, checking block public access, enabling versioning, and cleaning up after the lab. I paid extra attention to access control because S3 can become public by mistake if bucket policies and object permissions are not understood. I also read about static website hosting and object keys.

**Knowledge learned:** S3 is object storage, not a traditional folder system; access control and lifecycle should be designed carefully.

**Result achieved:** I could create and review buckets more safely and clean up resources after use.

**Difficulty and lesson learned:** Public access should never be enabled casually; if public delivery is needed, it should be designed properly with CloudFront/WAF.

## Day 4 - 23/4: EC2 introduction

**Work completed:** I studied EC2 instances, AMIs, instance types, key pairs, security groups, and SSH access to Linux servers. The hands-on part helped me understand EC2 as a cloud server surrounded by AWS networking and permission settings. I also reviewed common mistakes such as using the wrong key pair, leaving port 22 closed, or opening security groups too broadly.

**Knowledge learned:** EC2 feels close to a traditional server, but its security and cost depend heavily on networking and lifecycle configuration.

**Result achieved:** I understood the basic flow of creating, connecting to, checking, and deleting an EC2 instance.

**Difficulty and lesson learned:** Avoid opening SSH to the whole Internet and stop/delete instances when they are no longer needed.

## Day 5 - 24/4: Weekly review and cost check

**Work completed:** I summarized the first week, checked resources across regions, and reviewed billing to avoid forgotten services. This helped me notice that lab resources can still generate cost if they are created in another region or not fully deleted. I wrote down a cleanup routine: review Billing, check each region, delete running resources, and record the cause.

**Knowledge learned:** AWS cost can come from resources outside the current region, so cleanup must include multiple regions and service types.

**Result achieved:** I created my first cleanup checklist and started writing worklog notes in a clearer structure.

**Difficulty and lesson learned:** Learning AWS must go together with cost checking and resource cleanup habits.
