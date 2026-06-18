---
name: solve-open-source-issue
description: Implement a focused open-source contribution after scope is verified, including code fixes, tests, and documentation improvements that follow repository conventions.
argument-hint: "Scoped plan, target repository, and verification instructions."
---

# Solve Open Source Issue

Implement a small, maintainable contribution.

## Before Editing

- Read `README`, `CONTRIBUTING`, issue comments, PR template, and test instructions.
- Create or suggest a focused branch name.
- Confirm the change solves one problem.

## Implementation Rules

- Follow existing style and local helpers.
- Make the smallest useful change.
- Add or update tests when behavior changes.
- Keep documentation edits verified and specific.
- Avoid unrelated refactors.
- Avoid formatting-only diffs unless maintainers requested them.
- Do not change generated files or lock files unless required.

## Verification

Run the narrowest relevant test first. Run lint, format, or broader tests only when the project asks for them or the change risk requires it.

## Output

```markdown
## Implementation Summary

Changed files:
What changed:
Tests/checks run:
Result:
Remaining risk:
```
