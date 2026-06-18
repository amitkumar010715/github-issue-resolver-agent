---
name: contribution-triage
description: Fetch and rank contribution opportunities in a GitHub repository, including issues, PRs to review, discussions to answer, bug reproductions, docs gaps, and missing tests.
argument-hint: "Repository and preferred contribution type."
---

# Contribution Triage

Select the smallest useful opportunity with the highest chance of maintainer acceptance.

## Evaluate

For each candidate, check:

- Clear problem statement
- Existing assignee or linked PR
- Maintainer engagement
- Reproducibility
- Estimated setup time
- Estimated change size
- Testability
- Risk of conflicts

## Opportunity Types

- **Issue fix**: choose clear, scoped issues.
- **Bug reproduction**: add exact steps, version, logs, and expected/actual behavior.
- **Docs improvement**: fix a verified missing or confusing instruction.
- **PR review**: review only what can be verified.
- **Discussion answer**: answer only when the user has enough context.
- **Test contribution**: add a missing regression test for known behavior.

## Output

```markdown
## Opportunity Shortlist

| Rank | Type | Link or Ref | Difficulty | Time | Why This One |
| --- | --- | --- | --- | --- | --- |

## Selected Opportunity

Type:
Repo:
Issue/PR/Discussion:
Plan:
Needs maintainer question:
```
