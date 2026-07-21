---
title: "Week 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

**Timeline:** 1/6 → 5/6 (5 working days)

## Day 1 - 1/6: AWS SAM overview

**Work completed:** I started learning AWS SAM to understand serverless infrastructure as code. I reviewed project structure, `template.yaml`, function folders, `requirements.txt`, parameters, outputs, and resource definitions. I compared SAM with manual Console configuration: SAM is harder at first but makes deployment repeatable and easier to review.

**Knowledge learned:** Infrastructure as Code reduces manual mistakes and makes deployment documentation clearer.

**Result achieved:** I understood the basic structure of a SAM project and the role of `template.yaml`.

**Difficulty and lesson learned:** Resource names, parameters, and outputs should be consistent from the beginning.

## Day 2 - 2/6: sam validate practice

**Work completed:** I practiced `sam validate` to check templates before build and deployment. I read syntax errors, YAML indentation problems, and missing resource properties. This showed me how a small template issue can prevent CloudFormation from creating a stack.

**Knowledge learned:** Early validation catches template errors before resources are deployed to AWS.

**Result achieved:** I learned how to read several common SAM/CloudFormation errors.

**Difficulty and lesson learned:** YAML indentation is sensitive, so templates should be formatted carefully.

## Day 3 - 3/6: sam build practice

**Work completed:** I studied `sam build` and how SAM packages Lambda dependencies. I checked where build artifacts are created, why Python dependencies belong in `requirements.txt`, and why the build environment should match the runtime. I also noted that external libraries should be checked before deployment.

**Knowledge learned:** Build is important because Lambda must receive both source code and dependencies.

**Result achieved:** I understood why code can run locally but fail in Lambda if dependencies are not packaged correctly.

**Difficulty and lesson learned:** Runtime versions and dependencies should be reviewed before deployment.

## Day 4 - 4/6: sam deploy practice

**Work completed:** I studied `sam deploy --guided`, stack names, regions, capabilities, and CloudFormation outputs. I noted how SAM uploads artifacts to S3, creates or updates a stack, and returns values such as API endpoints. I also learned to check stack state after major changes.

**Knowledge learned:** SAM deployment is clearer when I understand the CloudFormation stack underneath.

**Result achieved:** I understood the validate-build-deploy-output flow.

**Difficulty and lesson learned:** When deployment fails, CloudFormation events should be reviewed instead of only reading the final terminal error.

## Day 5 - 5/6: Deployment checklist

**Work completed:** I created a deployment checklist: verify AWS profile and region, run validate, build, deploy, save outputs, test APIs, inspect CloudWatch Logs, and clean up test resources. This checklist was prepared before the real project phase to reduce mistakes when many services are connected.

**Knowledge learned:** A deployment checklist makes the process more stable, especially in a team project.

**Result achieved:** I had a personal deployment process to apply later in IRMS.

**Difficulty and lesson learned:** Deployment should not rely on memory; commands and checks should be written down.
