# Ship Your Spring Boot MVP — Free Edition

Your Spring Boot app runs on localhost.

That does **not** mean it is ready to ship.

This free edition helps you catch critical release blockers before real users find them — and encourages an evidence-first release habit instead of trusting a green deploy button or an AI answer.

> **AI-assisted. Built for human verification. Evidence-backed.**

## Start here

Use this workflow when your MVP already works locally and you are preparing to deploy it for real users.

**Check → Verify → Save evidence → Make the release decision**

The Free Edition is intentionally focused. It helps you:

- identify obvious ship blockers
- run one evidence-first AI review
- define a production smoke test
- record the release commit and the evidence you actually verified

This is **not** a Spring Boot tutorial, a cloud-provider walkthrough, a security certification, or a guarantee that your app is production-ready.

## Who this is for

Use it if:

- you built a Spring Boot MVP
- it works on localhost
- you used ChatGPT, Claude, Copilot, Cursor, or another AI coding tool during development
- you are preparing for a first or early production deployment
- you keep asking: **“What did I forget?”**

It is probably not for you if you want a complete AWS/Railway/Render tutorial, an enterprise SRE framework, or a ready-made Spring Boot starter codebase.

## What is included

### 1. 15 Critical Spring Boot Ship Blockers

A compact review across:

- build and tests
- configuration and secrets
- database and external integrations
- application security
- deployment and production behavior

Open: **[`15-ship-blockers.md`](./15-ship-blockers.md)**

### 2. Evidence-first AI review

Use AI as a second reviewer — not as the owner of the release decision.

Ask it to:

- cite the files, configuration, logs, or output supporting each claim
- separate evidence from inference
- return `NOT VERIFIED` when evidence is missing
- prioritize release blockers over refactoring advice
- avoid changing code unless you explicitly request it

Example:

```text
Review this Spring Boot MVP for release blockers.

For every finding:
1. State the check.
2. Show the file, config, command output, or other evidence.
3. Mark it VERIFIED or NOT VERIFIED.
4. Explain what would block release.

Do not assume missing evidence is safe.
Do not modify code unless I ask.
```

### 3. Minimal release evidence record

Keep a small record of what you actually verified:

```text
Release commit:
Production URL:
Clean build evidence:
Test evidence:
Production configuration reviewed:
Critical user flow:
Rollback point:
Known unresolved risk:
```

Evidence does not need to be complicated. It just needs to support the claim you are making.

Examples:

```text
./gradlew clean build → BUILD SUCCESSFUL
./gradlew test → expected tests passed
Release commit → a1b2c3d
Deployment ID → platform release identifier
Health check → expected response from production URL
Critical flow → manual test completed against production
Rollback point → previous known-good commit / deployment
```

**Never store passwords, API keys, tokens, secrets, or sensitive user data in an evidence record.**

## 10-minute quick start

1. Open `15-ship-blockers.md`.
2. Mark only checks you have actually verified.
3. Run the AI review against the relevant files, configuration, and logs.
4. Treat missing evidence as `NOT VERIFIED` instead of guessing.
5. Fix release-blocking issues.
6. Deploy.
7. Run your critical production smoke test.
8. Record the deployed commit and rollback point.

## Free Edition vs Interactive Evidence Edition

The **Free Edition** helps answer:

> **What could stop this MVP from shipping?**

The paid **Interactive Evidence Edition** is built for the next step:

> **How do I verify each release stage, save the evidence, and make the final ship decision?**

| Free Edition | Interactive Evidence Edition |
|---|---|
| 15 critical ship blockers | Six-stage release workflow |
| One evidence-first AI review | Full AI review prompt pack |
| Minimal evidence record | Editable evidence fields throughout |
| Basic smoke-test guidance | Detailed verification and failure actions |
| Markdown workflow | Interactive PDF with clickable checkboxes |
| Find blockers | Verify, document, and decide |

The full edition also includes a deployment runbook, release evidence templates, chapter-level decisions, and copy-paste operational templates.

### Interactive Evidence Edition

**Don’t just check the box. Verify it. Save the evidence. Then decide whether to ship.**

> Paid edition: **[View Ship Your Spring Boot MVP — Interactive Evidence Edition](PAID_PRODUCT_URL)**

_Replace `PAID_PRODUCT_URL` with the live Lemon Squeezy product URL before publishing this README._

## Scope and limitations

This repository is an engineering checklist and workflow aid.

It does not guarantee that an application is secure, bug-free, compliant, performant, or production-ready for every use case. Your application may require additional architecture, performance, privacy, legal, compliance, security, or operational review.

---

Built by **Nocklock**.

**AI-assisted. Built for human verification. Evidence-backed.**
