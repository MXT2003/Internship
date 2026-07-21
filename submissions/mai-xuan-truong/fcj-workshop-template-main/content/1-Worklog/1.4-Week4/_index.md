---
title: "Week 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

**Timeline:** 11/5 → 15/5 (5 working days)

## Day 1 - 11/5: Route 53 and DNS

**Work completed:** I studied Route 53, hosted zones, record types, and how DNS directs users to an application. I reviewed A records, CNAME records, and alias records, especially how AWS commonly uses alias records for CloudFront or ALB targets. This helped me understand the first step of a user request before it reaches the backend.

**Knowledge learned:** DNS is the first entry layer for users, so incorrect DNS can make an application unreachable even when backend services are running.

**Result achieved:** I understood how domains, records, and AWS targets are connected.

**Difficulty and lesson learned:** TTL and propagation time must be considered when debugging domain changes.

## Day 2 - 12/5: CloudFront concepts

**Work completed:** I studied CloudFront as a CDN that delivers content from edge locations closer to users. I focused on origins, behaviors, cache policy, default root object, HTTPS, and invalidation. Cache stood out as a common source of confusion because source files may be updated while the browser still receives old bundles.

**Knowledge learned:** CloudFront improves static delivery, protects the origin, and standardizes HTTPS for frontend hosting.

**Result achieved:** I understood why frontend deployments often need invalidation.

**Difficulty and lesson learned:** Deployment issues should be separated into build errors, upload errors, cache errors, and API-call errors.

## Day 3 - 13/5: WAF and web protection

**Work completed:** I read about AWS WAF, web ACLs, rule groups, and managed rules. I focused on WAF as an edge security layer that can block suspicious HTTP requests before they reach the application. Even without deep hands-on deployment, I documented use cases such as common attack patterns, rate limiting, and public endpoint protection.

**Knowledge learned:** Web security should use multiple layers, and WAF reduces risk at the HTTP edge layer.

**Result achieved:** I understood where WAF sits when placed in front of CloudFront or API Gateway.

**Difficulty and lesson learned:** If WAF is only proposed and not implemented, the report must describe it as a future enhancement, not completed work.

## Day 4 - 14/5: Static web hosting review

**Work completed:** I practiced the idea of hosting a frontend with S3 and distributing it through CloudFront. I reviewed how `index.html`, JavaScript bundles, and static assets are served. I also noted SPA routing issues, where refreshing a child route requires CloudFront/S3 to return `index.html` instead of a 404 page.

**Knowledge learned:** A single-page application needs different hosting behavior from a simple static website because routing happens on the client side.

**Result achieved:** I understood the relationship between S3 buckets, CloudFront origins, and browser cache.

**Difficulty and lesson learned:** Frontend deployment must be tested on the home page, child routes, and static asset paths.

## Day 5 - 15/5: Weekly documentation

**Work completed:** I converted notes about Route 53, CloudFront, WAF, and S3 hosting into short report-ready summaries. I wrote each service by problem solved, position in the architecture, and configuration risks. This helped me choose services more confidently when preparing later project documentation.

**Knowledge learned:** Notes organized by architecture role are easier to reuse than notes organized only by Console menu.

**Result achieved:** I had a list of edge and hosting services that could support frontend deployment.

**Difficulty and lesson learned:** The worklog should connect theory with internship progress instead of becoming a separate textbook.
