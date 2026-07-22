---
title: "Week 4 Worklog"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

- Review AWS services already learned and relate them to practical application deployment patterns.
- Prepare knowledge for authentication, APIs, compute, database, and monitoring.
- Record points that can be applied later in the IRMS project.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **Route 53 and DNS**<br>- **Work:** I studied Route 53, hosted zones, record types, and how DNS directs users to an application. I reviewed A records, CNAME records, and alias records, especially how AWS commonly uses alias records for CloudFront or ALB targets. This helped me understand the first step of a user request before it reaches the backend.<br>- **Knowledge:** DNS is the first entry layer for users, so incorrect DNS can make an application unreachable even when backend services are running.<br>- **Result:** I understood how domains, records, and AWS targets are connected.<br>- **Lesson:** TTL and propagation time must be considered when debugging domain changes. | 11/05/2026 | 11/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **CloudFront concepts**<br>- **Work:** I studied CloudFront as a CDN that delivers content from edge locations closer to users. I focused on origins, behaviors, cache policy, default root object, HTTPS, and invalidation. Cache stood out as a common source of confusion because source files may be updated while the browser still receives old bundles.<br>- **Knowledge:** CloudFront improves static delivery, protects the origin, and standardizes HTTPS for frontend hosting.<br>- **Result:** I understood why frontend deployments often need invalidation.<br>- **Lesson:** Deployment issues should be separated into build errors, upload errors, cache errors, and API-call errors. | 12/05/2026 | 12/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **WAF and web protection**<br>- **Work:** I read about AWS WAF, web ACLs, rule groups, and managed rules. I focused on WAF as an edge security layer that can block suspicious HTTP requests before they reach the application. Even without deep hands-on deployment, I documented use cases such as common attack patterns, rate limiting, and public endpoint protection.<br>- **Knowledge:** Web security should use multiple layers, and WAF reduces risk at the HTTP edge layer.<br>- **Result:** I understood where WAF sits when placed in front of CloudFront or API Gateway.<br>- **Lesson:** If WAF is only proposed and not implemented, the report must describe it as a future enhancement, not completed work. | 13/05/2026 | 13/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **Static web hosting review**<br>- **Work:** I practiced the idea of hosting a frontend with S3 and distributing it through CloudFront. I reviewed how `index.html`, JavaScript bundles, and static assets are served. I also noted SPA routing issues, where refreshing a child route requires CloudFront/S3 to return `index.html` instead of a 404 page.<br>- **Knowledge:** A single-page application needs different hosting behavior from a simple static website because routing happens on the client side.<br>- **Result:** I understood the relationship between S3 buckets, CloudFront origins, and browser cache.<br>- **Lesson:** Frontend deployment must be tested on the home page, child routes, and static asset paths. | 14/05/2026 | 14/05/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Weekly documentation**<br>- **Work:** I converted notes about Route 53, CloudFront, WAF, and S3 hosting into short report-ready summaries. I wrote each service by problem solved, position in the architecture, and configuration risks. This helped me choose services more confidently when preparing later project documentation.<br>- **Knowledge:** Notes organized by architecture role are easier to reuse than notes organized only by Console menu.<br>- **Result:** I had a list of edge and hosting services that could support frontend deployment.<br>- **Lesson:** The worklog should connect theory with internship progress instead of becoming a separate textbook. | 15/05/2026 | 15/05/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 4 Achievements:

- **11/05/2026:** I understood how domains, records, and AWS targets are connected. TTL and propagation time must be considered when debugging domain changes.
- **12/05/2026:** I understood why frontend deployments often need invalidation. Deployment issues should be separated into build errors, upload errors, cache errors, and API-call errors.
- **13/05/2026:** I understood where WAF sits when placed in front of CloudFront or API Gateway. If WAF is only proposed and not implemented, the report must describe it as a future enhancement, not completed work.
- **14/05/2026:** I understood the relationship between S3 buckets, CloudFront origins, and browser cache. Frontend deployment must be tested on the home page, child routes, and static asset paths.
- **15/05/2026:** I had a list of edge and hosting services that could support frontend deployment. The worklog should connect theory with internship progress instead of becoming a separate textbook.
