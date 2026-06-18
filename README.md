# GitHub Issue Resolver Agent

A reusable agent workflow and plugin package for finding GitHub issues, reproducing bugs, implementing focused fixes, auditing the result, and preparing pull requests.

Use it for practical open-source contribution work: discover a repo, triage a useful issue, validate the problem, make the smallest maintainable fix, run checks, complete a security audit, and prepare the PR.

## What This Includes

- Agent orchestration files: `.github/agents/*.agent.md`
- Agent support skills: `.github/skills/*/SKILL.md`
- Copilot repository instructions: `.github/copilot-instructions.md`
- Copilot path-specific instructions: `.github/instructions/github-issue-resolver-agent.instructions.md`
- Codex plugin manifest: `.codex-plugin/plugin.json`
- Codex issue resolver skill: `skills/github-issue-resolver-agent/SKILL.md`
- Codex skill: `skills/agentic-security-audit/SKILL.md`
- GitHub Copilot custom instruction file: `instructions/copilot-github-issue-resolver-agent.instructions.md`
- Claude project/chat instruction file: `instructions/claude-github-issue-resolver-agent.md`
- Shared audit playbook: `instructions/shared-security-audit-playbook.md`

## What It Does

- Finds active GitHub repositories that match the user's stack.
- Triages open issues, discussions, docs gaps, tests, and PR review opportunities.
- Reproduces or validates the selected issue before editing.
- Implements the smallest useful fix or improvement.
- Runs focused verification.
- Performs a scoped security, privacy, dependency, and supply-chain audit.
- Prepares a pull request after user confirmation.

## Security Audit Step

The workflow still includes a security audit before publishing. It reviews:

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

- `Find and fix a suitable GitHub issue.`
- `Resolve this GitHub bug and prepare a PR.`
- `Audit my fix before publishing the pull request.`

The main Codex skill lives at:

```text
skills/github-issue-resolver-agent/SKILL.md
```

The security audit support skill lives at:

```text
skills/agentic-security-audit/SKILL.md
```

## Agent Orchestration Usage

The `.github/agents` folder contains a complete open-source contribution workflow:

- `open-source-contributor.agent.md` coordinates the full flow.
- `repo-finder.agent.md` finds suitable repositories.
- `contribution-triage.agent.md` ranks useful opportunities.
- `reproducer-planner.agent.md` validates the issue and scope.
- `issue-solver.agent.md` implements the focused change.
- `security-auditor.agent.md` reviews the completed change before publishing.
- `pr-publisher.agent.md` prepares the PR after confirmation.

The matching `.github/skills` folder is included because the agents reference those skills directly.

## GitHub Copilot Usage

This repo includes Copilot-compatible instruction entrypoints:

```text
.github/copilot-instructions.md
.github/instructions/github-issue-resolver-agent.instructions.md
```

You can also use this standalone file as custom instructions:

```text
instructions/copilot-github-issue-resolver-agent.instructions.md
```

For repository-local Copilot instructions, copy or reference its contents from your Copilot instructions setup. It tells Copilot to run the same pre-PR audit and block or flag publishing when unresolved `Medium` or `High` findings remain.

## Claude Usage

Use this file as Claude project instructions, or paste it into Claude before asking it to help resolve a GitHub issue:

```text
instructions/claude-github-issue-resolver-agent.md
```

It gives Claude the same issue-resolution workflow plus the scoped audit role, checklist, risk scale, and output format.

## Default Contribution Output

```markdown
## Contribution Report

Repository:
Contribution type:
Issue/PR/Discussion:
Branch:
Files changed:
Verification:
Security audit:
Published PR/comment:
Next maintainer step:
```

## Security Audit Output

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
