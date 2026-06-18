---
name: repo-discovery
description: Find active GitHub repositories that match a user's tech stack and are suitable for useful open-source contributions. Use when selecting repositories for issues, docs, tests, PR reviews, or discussions.
argument-hint: "Tech stack, interests, difficulty, and available time."
---

# Repo Discovery

Find repositories that are active, welcoming, and realistic for the user's stack.

## Inputs

- Tech stack or inferred workspace stack
- Preferred difficulty
- Preferred contribution type
- Available time
- GitHub username if relevant

## Search Signals

Prefer repositories with:

- Recent commits, releases, or merged PRs
- Maintainer replies in issues or PRs
- Clear `README` and `CONTRIBUTING` files
- Good setup instructions
- Tests, examples, or docs
- Labels like `good first issue`, `help wanted`, `documentation`, `bug`, `beginner friendly`, or `first-timers-only`

Avoid repositories with:

- No maintainer activity
- Many stale PRs
- Unclear license
- Hostile discussions
- Huge setup cost for a small contribution

## Output

```markdown
## Candidate Repositories

| Rank | Repository | Stack Match | Activity | Best Opportunity | Risk |
| --- | --- | --- | --- | --- | --- |

## Recommended Target

Repository:
Reason:
Next step:
```
