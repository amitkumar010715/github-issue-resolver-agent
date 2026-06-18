# Agentic Security Audit

A reusable security audit plugin and instruction pack for agentic contribution workflows.

Use it before publishing a pull request to review the code paths touched by an AI-assisted or multi-agent contribution. The audit is intentionally scoped: it checks the completed diff, nearby behavior, dependencies, workflows, and documentation without turning every contribution into a full-project penetration test.

## What This Includes

- Codex plugin manifest: `.codex-plugin/plugin.json`
- Codex skill: `skills/agentic-security-audit/SKILL.md`
- GitHub Copilot custom instruction file: `instructions/copilot-agentic-security-audit.instructions.md`
- Claude project/chat instruction file: `instructions/claude-agentic-security-audit.md`
- Shared audit playbook: `instructions/shared-security-audit-playbook.md`

## What It Reviews

- Authentication, authorization, tenant isolation, and permission boundaries.
- Input validation, output encoding, redirects, path traversal, injection, unsafe eval, unsafe deserialization, and command execution.
- Secret handling, environment variables, logs, error messages, telemetry, analytics, and personally identifiable information.
- Cryptography, token/session handling, CSRF/CORS, SSRF, file upload/download, browser storage, and cache behavior.
- Database queries, migrations, data retention, and destructive operations.
- Dependency updates, package scripts, CI workflow changes, binary artifacts, vendored files, and provenance risk.
- Tests and documentation examples that could encourage insecure usage.

## Risk Ratings

- `Clear`: no material risk found in the contribution.
- `Low`: minor concern that can be documented or handled later.
- `Medium`: fix should happen before publishing unless the maintainer explicitly accepts the tradeoff.
- `High`: do not publish until fixed.

Publishing should wait when unresolved `Medium` or `High` findings remain.

## Codex Usage

This repository is structured as a Codex plugin root. After installing or adding it to a Codex plugin marketplace, use prompts like:

- `Security-audit my current contribution diff.`
- `Review these changed files before I publish a PR.`
- `Check this agentic workflow for supply-chain risk.`

The Codex skill lives at:

```text
skills/agentic-security-audit/SKILL.md
```

## GitHub Copilot Usage

Use this file as Copilot custom instructions:

```text
instructions/copilot-agentic-security-audit.instructions.md
```

For repository-local Copilot instructions, copy or reference its contents from your Copilot instructions setup. It tells Copilot to run the same pre-PR audit and block or flag publishing when unresolved `Medium` or `High` findings remain.

## Claude Usage

Use this file as Claude project instructions, or paste it into Claude before asking for a security review:

```text
instructions/claude-agentic-security-audit.md
```

It gives Claude the same scoped audit role, checklist, risk scale, and output format.

## Default Output

```markdown
## Security Audit

Changed files reviewed:
Risk rating:
Findings:
Required fixes before PR:
Checks run:
Notes for PR:
```

## Suggested Agentic Workflow

1. Reproduce or validate the issue.
2. Implement the smallest useful change.
3. Run tests or checks.
4. Run Agentic Security Audit.
5. Fix unresolved `Medium` or `High` findings.
6. Publish the PR only after the audit is clear or the remaining risk is explicitly documented.

## License

MIT
