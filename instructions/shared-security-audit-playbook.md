# Shared Security Audit Playbook

Run this review after implementation and before publishing a pull request.

## Scope

Review only the completed contribution, the diff, and the directly affected code paths unless a wider review is requested.

## Required Inputs

- Target repository and issue or PR context.
- Implementation summary.
- Changed files or diff.
- Test and verification results.
- Relevant project security, contribution, and release guidance.

## Checklist

- Authentication, authorization, tenant isolation, and permission boundaries.
- Input validation, output encoding, redirects, path handling, injection, unsafe eval, unsafe deserialization, and command execution.
- Secret handling, environment variables, logs, telemetry, error messages, and personally identifiable information.
- Cryptography, token/session handling, CSRF/CORS, SSRF, uploads/downloads, browser storage, and cache behavior.
- Database queries, migrations, retention, and destructive operations.
- Dependency updates, package scripts, CI workflows, generated files, binary artifacts, vendored code, and provenance.
- Tests and documentation examples that could encourage insecure usage.

## Risk Rating

- `Clear`: no material risk found in the contribution.
- `Low`: minor concern that can be documented or handled later.
- `Medium`: fix should happen before publishing unless the maintainer explicitly accepts the tradeoff.
- `High`: do not publish until fixed.

Publishing should wait when unresolved `Medium` or `High` findings remain.

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
