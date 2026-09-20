# Spring Boot MVP Ship Readiness Score

Your application works locally.

But how close is it to being ready to ship?

Use this scorecard after completing the
[15 Spring Boot MVP Ship Blockers](15-ship-blockers.md).

This is not a certification or a guarantee that your application is secure or production-ready.

It is a quick way to identify obvious deployment risks before going live.

---

## How to Use This Scorecard

For each applicable item:

- **PASS** — Give yourself the full points
- **FAIL** — Give yourself 0 points
- **N/A** — Remove that item from the total possible score

Your final score is:

```text
Points earned
────────────── × 100
Applicable points
```

Example:

```text
82 points earned
─────────────── × 100 = 91%
90 applicable points
```

---

# Ship Readiness Scorecard

## Build & Tests — 15 points

### 1. Clean Build — 8 points

- [ ] `./gradlew clean build` completes successfully

Score:

```text
___ / 8
```

### 2. Automated Tests — 7 points

- [ ] Existing automated tests pass

Score:

```text
___ / 7
```

---

## Configuration — 20 points

### 3. Production Configuration — 7 points

- [ ] Production does not depend on localhost or local-only paths/settings

Score:

```text
___ / 7
```

### 4. Secrets — 8 points

- [ ] Secrets, passwords, tokens, and API keys are not hardcoded or committed

Score:

```text
___ / 8
```

### 5. Environment Variables — 5 points

- [ ] Required environment variables exist in the deployment environment

Score:

```text
___ / 5
```

---

## Infrastructure & Integrations — 15 points

### 6. Production Database — 8 points

- [ ] The deployed application can connect to and use the production database

Score:

```text
___ / 8
```

### 7. External Services — 7 points

- [ ] Required external APIs and services work from the deployed environment

Score:

```text
___ / 7
```

---

## Application Security — 25 points

### 8. Input Validation — 5 points

- [ ] User-controlled input is validated server-side

Score:

```text
___ / 5
```

### 9. Error Exposure — 5 points

- [ ] Production responses do not expose stack traces or sensitive internal details

Score:

```text
___ / 5
```

### 10. Authentication & Authorization — 6 points

- [ ] Protected resources enforce the correct permissions

Score:

```text
___ / 6
```

Mark N/A if your MVP does not require authentication.

### 11. CORS — 4 points

- [ ] Production CORS configuration has been intentionally reviewed

Score:

```text
___ / 4
```

### 12. File Upload Security — 5 points

- [ ] File size, file type, and uploaded filenames are validated

Score:

```text
___ / 5
```

Mark N/A if your MVP does not accept files.

---

## Production Behavior — 10 points

### 13. Logging — 4 points

- [ ] Production logs do not expose secrets or unnecessary personal data

Score:

```text
___ / 4
```

### 14. Production Startup — 6 points

- [ ] The application starts successfully using the actual production configuration

Score:

```text
___ / 6
```

---

## Post-deployment Verification — 15 points

### 15. Critical User Flow — 15 points

- [ ] The most important end-to-end user flow works after deployment

Score:

```text
___ / 15
```

---

# Calculate Your Score

```text
Build & Tests                    ___ / 15
Configuration                    ___ / 20
Infrastructure & Integrations    ___ / 15
Application Security             ___ / 25
Production Behavior              ___ / 10
Post-deployment Verification     ___ / 15

-----------------------------------------

TOTAL                            ___ / 100
```

If you marked anything as N/A, subtract those points from the applicable category and total possible score before calculating your percentage.

---

# How to Read Your Score

## 90–100% — READY FOR FINAL SMOKE TEST

No obvious blockers were found by this checklist.

Before announcing your launch, run a final smoke test against the deployed application.

---

## 75–89% — REVIEW REQUIRED

Your MVP may be close to shipping, but some deployment or production risks still need review.

Fix failed high-impact items before going live.

---

## Below 75% — BLOCKED

There are enough unresolved items that shipping now may create avoidable failures.

Focus on failed items before continuing deployment.

---

# Critical Override

Your percentage does not override a critical failure.

Even with a high score, treat the project as **BLOCKED** if any of these are true:

```text
[ ] Production build fails
[ ] Application cannot start in production
[ ] Required database cannot connect
[ ] Required external service cannot connect
[ ] Secrets are exposed
[ ] Authentication or authorization is broken
[ ] Critical user flow fails after deployment
```

A 95% score with an exposed API key is not a 95%-ready application.

---

# Next Step

After completing this scorecard, run the:

[AI-assisted Deployment Blocker Review Prompt](../prompts/deployment-blocker-review.md)

Use both results together:

```text
15 Ship Blockers
        ↓
Ship Readiness Score
        ↓
AI Deployment Review
        ↓
Fix Critical Issues
        ↓
Deploy
        ↓
Final Smoke Test
```

---

Part of **Ship Your Spring Boot MVP — Free Edition**.

Built by **Nocklock**.
