---
title: "Week 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

**Timeline:** 8/6 → 12/6 (5 working days)

## Day 1 - 8/6: Frontend basics

**Work completed:** I reviewed React + Vite project structure, component organization, environment files, and production build output. Although I was not responsible for the whole frontend, I needed enough understanding to coordinate API calls and static deployment. I noted the difference between local dev server and production build, especially API base URLs and asset paths.

**Knowledge learned:** Frontend integration requires API contracts and environment variables to be aligned with the backend.

**Result achieved:** I understood how a React app becomes static files for S3/CloudFront hosting.

**Difficulty and lesson learned:** A wrong base URL or build-time variable can make the deployed frontend call the wrong API.

## Day 2 - 9/6: Authentication flow

**Work completed:** I studied how the frontend stores login state, receives a token from Cognito, and sends `Authorization: Bearer <token>` to protected APIs. I also reviewed expired tokens, unauthenticated users, and 401 responses. This prepared me for later Cognito Authorizer testing.

**Knowledge learned:** Authentication continues beyond the login screen; the token must travel correctly from frontend to API Gateway.

**Result achieved:** I knew what to check when a protected API returned 401 or 403.

**Difficulty and lesson learned:** Tokens should not be logged casually in the browser console.

## Day 3 - 10/6: CORS troubleshooting

**Work completed:** I reviewed CORS headers, `OPTIONS` preflight requests, and why browsers may block a request even when backend logic works. I noted important headers such as `Access-Control-Allow-Origin`, `Access-Control-Allow-Headers`, and `Access-Control-Allow-Methods`. This was useful because frontend-backend integration often faces CORS issues.

**Knowledge learned:** CORS is enforced by browsers, so curl/Postman tests may not reveal the same problem.

**Result achieved:** I had a CORS checklist for API Gateway and Lambda responses.

**Difficulty and lesson learned:** Real browser testing is required after deploying an API Gateway stage.

## Day 4 - 11/6: UI integration notes

**Work completed:** I read about turning mockups or generated UI into maintainable React components. I focused on separating display logic from API calls, handling state/loading/error clearly, and avoiding hard-coded endpoints inside components. This later helped me support Stitch AI UI integration.

**Knowledge learned:** A good-looking UI still needs clean structure to connect with a real backend.

**Result achieved:** I understood the common states for API-driven screens: loading, success, empty, error, and unauthorized.

**Difficulty and lesson learned:** If API logic is mixed into components, changing endpoints or auth headers becomes difficult.

## Day 5 - 12/6: Weekly summary

**Work completed:** I summarized frontend/backend integration notes: React build, environment variables, auth token, CORS, and API error handling. I also listed risks to check in a real project, including wrong endpoints, missing headers, expired tokens, cached frontend bundles, and mismatched response formats.

**Knowledge learned:** Frontend and backend must align from contract to error handling for a demo to be stable.

**Result achieved:** I had an integration checklist to use when the team connected the IRMS frontend and backend.

**Difficulty and lesson learned:** Testing should follow real user flows, not only individual API calls.
