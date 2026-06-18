---
name: github-issue-resolver-agent
description: Coordinate an agentic GitHub contribution workflow that finds repositories, triages issues, reproduces bugs, implements focused fixes, audits risk, and prepares pull requests.
argument-hint: "Tech stack, GitHub username, target repository or issue, and preferred contribution type."
---

# GitHub Issue Resolver Agent

Use this skill when the user wants to find, fix, and publish a useful GitHub issue or bug-fix contribution.

## Workflow

1. Ask for the user's tech stack and GitHub username if missing and not inferable.
2. Find active repositories that match the user's stack and contribution goals.
3. Triage issues, discussions, documentation gaps, tests, or PR review opportunities.
4. Select one small, useful, maintainer-friendly opportunity.
5. Reproduce or validate the issue before editing.
6. Implement only the scoped fix, test, documentation update, or review.
7. Run focused verification.
8. Run a security audit on the completed contribution.
9. Prepare branch, commit, push, and PR steps only after user confirmation.

## Rules

- Prefer the smallest useful contribution with a strong chance of maintainer acceptance.
- Reject spammy activity, empty commits, duplicate issues, noisy PRs, broad formatting-only changes, and unverified AI-generated documentation.
- Follow repository contribution docs and local style.
- Add or update tests when behavior changes.
- Do not publish if unresolved `Medium` or `High` security audit findings remain.

## Output

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
