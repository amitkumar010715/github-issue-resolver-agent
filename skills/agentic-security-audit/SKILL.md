---
name: agentic-security-audit
description: Audit completed agentic contribution changes for security, privacy, dependency, and supply-chain risks before pull request publication.
argument-hint: "Repository, diff or changed files, issue context, implementation summary, and verification results."
---

# Agentic Security Audit

Use this skill when a contribution is complete and needs a security pass before publishing, especially in an agentic orchestration flow.

Audit only the contribution and the code paths it affects unless the user explicitly requests a wider review.

## Inputs

- Read the scoped issue plan, implementation summary, changed files, tests, and relevant project security guidance.
- Inspect the diff and nearby code for the touched behavior.
- Check dependency, build, workflow, generated, and lockfile changes when present.
- Confirm the PR publisher should not proceed with unresolved `Medium` or `High` findings.

## Review Checklist

- Validate authentication, authorization, tenant isolation, and permission checks.
- Check input parsing, validation, output encoding, redirects, path traversal, injection, unsafe eval, unsafe deserialization, and command execution.
- Check secret handling, environment variables, logs, error messages, telemetry, analytics, and personally identifiable information.
- Check cryptography, token/session handling, CSRF/CORS, SSRF, file upload/download, browser storage, and cache behavior when touched.
- Check database queries, migrations, data retention, and destructive operations.
- Check dependency updates, package scripts, CI workflow changes, binary artifacts, vendored files, and provenance risk.
- Check tests and documentation for examples that could normalize insecure usage.

## Risk Rating

Use one of:

- `Clear`: no material risk found in the contribution.
- `Low`: minor concern that can be documented or handled later.
- `Medium`: fix should happen before publishing unless the maintainer explicitly accepts the tradeoff.
- `High`: do not publish until fixed.

## Output

```markdown
## Security Audit

Changed files reviewed:
Risk rating:
Findings:
Required fixes before PR:
Checks run:
Notes for PR:
```
