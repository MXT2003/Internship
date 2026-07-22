---
title: "Week 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

- Review React, Vite, frontend environment variables, and authenticated API integration.
- Understand common frontend-backend issues such as CORS, tokens, and response formats.
- Prepare a UI integration and web deployment checklist for the final project.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - **Frontend basics**<br>- **Work:** I reviewed React + Vite project structure, component organization, environment files, and production build output. Although I was not responsible for the whole frontend, I needed enough understanding to coordinate API calls and static deployment. I noted the difference between local dev server and production build, especially API base URLs and asset paths.<br>- **Knowledge:** Frontend integration requires API contracts and environment variables to be aligned with the backend.<br>- **Result:** I understood how a React app becomes static files for S3/CloudFront hosting.<br>- **Lesson:** A wrong base URL or build-time variable can make the deployed frontend call the wrong API. | 08/06/2026 | 08/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 2 | - **Authentication flow**<br>- **Work:** I studied how the frontend stores login state, receives a token from Cognito, and sends `Authorization: Bearer <token>` to protected APIs. I also reviewed expired tokens, unauthenticated users, and 401 responses. This prepared me for later Cognito Authorizer testing.<br>- **Knowledge:** Authentication continues beyond the login screen; the token must travel correctly from frontend to API Gateway.<br>- **Result:** I knew what to check when a protected API returned 401 or 403.<br>- **Lesson:** Tokens should not be logged casually in the browser console. | 09/06/2026 | 09/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 3 | - **CORS troubleshooting**<br>- **Work:** I reviewed CORS headers, `OPTIONS` preflight requests, and why browsers may block a request even when backend logic works. I noted important headers such as `Access-Control-Allow-Origin`, `Access-Control-Allow-Headers`, and `Access-Control-Allow-Methods`. This was useful because frontend-backend integration often faces CORS issues.<br>- **Knowledge:** CORS is enforced by browsers, so curl/Postman tests may not reveal the same problem.<br>- **Result:** I had a CORS checklist for API Gateway and Lambda responses.<br>- **Lesson:** Real browser testing is required after deploying an API Gateway stage. | 10/06/2026 | 10/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 4 | - **UI integration notes**<br>- **Work:** I read about turning mockups or generated UI into maintainable React components. I focused on separating display logic from API calls, handling state/loading/error clearly, and avoiding hard-coded endpoints inside components. This later helped me support Stitch AI UI integration.<br>- **Knowledge:** A good-looking UI still needs clean structure to connect with a real backend.<br>- **Result:** I understood the common states for API-driven screens: loading, success, empty, error, and unauthorized.<br>- **Lesson:** If API logic is mixed into components, changing endpoints or auth headers becomes difficult. | 11/06/2026 | 11/06/2026 | AWS Documentation, FCJ labs, internship notes |
| 5 | - **Weekly summary**<br>- **Work:** I summarized frontend/backend integration notes: React build, environment variables, auth token, CORS, and API error handling. I also listed risks to check in a real project, including wrong endpoints, missing headers, expired tokens, cached frontend bundles, and mismatched response formats.<br>- **Knowledge:** Frontend and backend must align from contract to error handling for a demo to be stable.<br>- **Result:** I had an integration checklist to use when the team connected the IRMS frontend and backend.<br>- **Lesson:** Testing should follow real user flows, not only individual API calls. | 12/06/2026 | 12/06/2026 | AWS Documentation, FCJ labs, internship notes |

### Week 8 Achievements:

- **08/06/2026:** I understood how a React app becomes static files for S3/CloudFront hosting. A wrong base URL or build-time variable can make the deployed frontend call the wrong API.
- **09/06/2026:** I knew what to check when a protected API returned 401 or 403. Tokens should not be logged casually in the browser console.
- **10/06/2026:** I had a CORS checklist for API Gateway and Lambda responses. Real browser testing is required after deploying an API Gateway stage.
- **11/06/2026:** I understood the common states for API-driven screens: loading, success, empty, error, and unauthorized. If API logic is mixed into components, changing endpoints or auth headers becomes difficult.
- **12/06/2026:** I had an integration checklist to use when the team connected the IRMS frontend and backend. Testing should follow real user flows, not only individual API calls.
