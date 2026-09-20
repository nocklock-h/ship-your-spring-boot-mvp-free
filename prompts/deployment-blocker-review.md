# Spring Boot Deployment Blocker Review

Use this prompt with ChatGPT, Claude, Cursor, Copilot, or another AI coding assistant before deploying your Spring Boot MVP.

The goal is not to refactor the entire project.

The goal is to find issues that could block deployment, expose sensitive data, or break critical functionality after going live.

---

## Prompt

Review this Spring Boot project as if it were going to production today.

Focus on deployment blockers and production risks.

Do not suggest unnecessary refactoring or architecture changes unless they directly affect deployment, security, or reliability.

Review the following areas:

1. Build configuration
2. Java and Gradle versions
3. Environment variables
4. Hardcoded secrets
5. Spring profiles
6. Database configuration
7. External API configuration
8. Input validation
9. Error handling
10. Authentication and authorization
11. CORS configuration
12. File upload security
13. Logging
14. Docker or deployment configuration
15. Health checks
16. Critical post-deployment user flows

For every issue you find, return:

- **Severity:** Critical / High / Medium / Low
- **Location:** File and relevant code or configuration
- **Problem:** What is wrong
- **Why it matters:** What could happen after deployment
- **How to verify:** How I can confirm the issue
- **Recommended fix:** The smallest practical fix

Prioritize issues that could:

- Prevent the application from starting
- Break production functionality
- Expose secrets or sensitive data
- Cause authentication or authorization failures
- Cause database or external API failures
- Make debugging production issues difficult

Do not assume that because the application works on localhost, it will work in production.

At the end, provide:

## Ship Decision

Classify the project as:

- **BLOCKED** — Critical issues should be fixed before deployment
- **REVIEW REQUIRED** — High-risk issues remain
- **READY FOR SMOKE TEST** — No obvious deployment blockers found

Then provide the top 3 things I should verify manually before going live.

---

## Recommended Usage

Run this review after:

1. Your MVP works locally
2. Your automated tests pass
3. Your production environment variables are configured
4. You are preparing for the first real deployment

This prompt is designed to complement the [15 Spring Boot MVP Ship Blockers](../checklist/15-ship-blockers.md).

---

Part of **Ship Your Spring Boot MVP — Free Edition**.

Built by **Nocklock**.
