---
title: "Week 7 Worklog"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

- Study EventBridge, SNS, CloudWatch, and monitoring/alerting mechanisms on AWS.
- Understand event-driven flows and how a system reacts to generated events.
- Prepare checklists for alerting, logging, and testing in IRMS.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **AWS SAM overview**<br>- **Work:** I started learning AWS SAM to understand serverless infrastructure as code. I reviewed project structure, `template.yaml`, function folders, `requirements.txt`, parameters, outputs, and resource definitions. I compared SAM with manual Console configuration: SAM is harder at first but makes deployment repeatable and easier to review.<br>- **Knowledge:** Infrastructure as Code reduces manual mistakes and makes deployment documentation clearer.<br>- **Result:** I understood the basic structure of a SAM project and the role of `template.yaml`.<br>- **Lesson:** Resource names, parameters, and outputs should be consistent from the beginning. | 01/06/2026 | 01/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **sam validate practice**<br>- **Work:** I practiced `sam validate` to check templates before build and deployment. I read syntax errors, YAML indentation problems, and missing resource properties. This showed me how a small template issue can prevent CloudFormation from creating a stack.<br>- **Knowledge:** Early validation catches template errors before resources are deployed to AWS.<br>- **Result:** I learned how to read several common SAM/CloudFormation errors.<br>- **Lesson:** YAML indentation is sensitive, so templates should be formatted carefully. | 02/06/2026 | 02/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **sam build practice**<br>- **Work:** I studied `sam build` and how SAM packages Lambda dependencies. I checked where build artifacts are created, why Python dependencies belong in `requirements.txt`, and why the build environment should match the runtime. I also noted that external libraries should be checked before deployment.<br>- **Knowledge:** Build is important because Lambda must receive both source code and dependencies.<br>- **Result:** I understood why code can run locally but fail in Lambda if dependencies are not packaged correctly.<br>- **Lesson:** Runtime versions and dependencies should be reviewed before deployment. | 03/06/2026 | 03/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **sam deploy practice**<br>- **Work:** I studied `sam deploy --guided`, stack names, regions, capabilities, and CloudFormation outputs. I noted how SAM uploads artifacts to S3, creates or updates a stack, and returns values such as API endpoints. I also learned to check stack state after major changes.<br>- **Knowledge:** SAM deployment is clearer when I understand the CloudFormation stack underneath.<br>- **Result:** I understood the validate-build-deploy-output flow.<br>- **Lesson:** When deployment fails, CloudFormation events should be reviewed instead of only reading the final terminal error. | 04/06/2026 | 04/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Deployment checklist**<br>- **Work:** I created a deployment checklist: verify AWS profile and region, run validate, build, deploy, save outputs, test APIs, inspect CloudWatch Logs, and clean up test resources. This checklist was prepared before the real project phase to reduce mistakes when many services are connected.<br>- **Knowledge:** A deployment checklist makes the process more stable, especially in a team project.<br>- **Result:** I had a personal deployment process to apply later in IRMS.<br>- **Lesson:** Deployment should not rely on memory; commands and checks should be written down. | 05/06/2026 | 05/06/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 7 Achievements:

- **01/06/2026:** I understood the basic structure of a SAM project and the role of `template.yaml`. Resource names, parameters, and outputs should be consistent from the beginning.
- **02/06/2026:** I learned how to read several common SAM/CloudFormation errors. YAML indentation is sensitive, so templates should be formatted carefully.
- **03/06/2026:** I understood why code can run locally but fail in Lambda if dependencies are not packaged correctly. Runtime versions and dependencies should be reviewed before deployment.
- **04/06/2026:** I understood the validate-build-deploy-output flow. When deployment fails, CloudFormation events should be reviewed instead of only reading the final terminal error.
- **05/06/2026:** I had a personal deployment process to apply later in IRMS. Deployment should not rely on memory; commands and checks should be written down.
