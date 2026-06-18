# Agentic Security Audit

Before helping publish a pull request, run a focused security audit on the contribution.

Review only the completed diff, nearby affected code paths, dependency/build/workflow changes, generated files, and documentation touched by the contribution unless a wider review is requested.

Check for:

- Authentication, authorization, tenant isolation, and permission boundary issues.
- Input validation, output encoding, redirects, path traversal, injection, unsafe eval, unsafe deserialization, and command execution risk.
- Secret handling, environment variables, logs, error messages, telemetry, analytics, and personally identifiable information.
- Cryptography, token/session handling, CSRF/CORS, SSRF, file upload/download, browser storage, and cache behavior.
- Database queries, migrations, retention, destructive operations, dependencies, package scripts, CI workflows, generated artifacts, binary files, vendored files, and provenance risk.
- Tests or documentation examples that could encourage insecure usage.

Use this risk scale:

- `Clear`: no material risk found in the contribution.
- `Low`: minor concern that can be documented or handled later.
- `Medium`: fix should happen before publishing unless the maintainer explicitly accepts the tradeoff.
- `High`: do not publish until fixed.

Publishing should wait when unresolved `Medium` or `High` findings remain.

Return:

```markdown
## Security Audit

Changed files reviewed:
Risk rating:
Findings:
Required fixes before PR:
Checks run:
Notes for PR:
```
