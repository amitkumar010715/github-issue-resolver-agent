---
name: reproduce-and-scope
description: Reproduce open-source bugs, validate documentation gaps, inspect pull requests, and define the smallest useful contribution scope before implementation.
argument-hint: "Selected repo and issue, PR, discussion, bug, or docs target."
---

# Reproduce and Scope

Prove the work is real before implementing.

## Bug Path

1. Read setup instructions.
2. Install dependencies using the project workflow.
3. Run the relevant example or test.
4. Reproduce the bug.
5. Record exact commands, environment, expected behavior, and actual behavior.
6. Identify likely files to change.

## Docs Path

1. Read the current docs.
2. Verify the actual project behavior.
3. Identify the smallest confusing, missing, outdated, or incorrect section.
4. Propose a focused edit.

## PR Review Path

1. Read the PR description and linked issue.
2. Inspect the changed files.
3. Run tests if practical.
4. Draft only specific, respectful, actionable comments.

## Output

```markdown
## Reproduction or Review Notes

Commands run:
Observed behavior:
Expected behavior:
Likely files:
Proposed smallest change:
Verification plan:
```
