---
name: publish-github-pr
description: Prepare and publish a GitHub pull request from the user's account after confirming authentication, branch, remotes, commit contents, target repository, security audit status, and user approval.
argument-hint: "Repo, branch, issue number, and completed changes."
---

# Publish GitHub PR

Publish only after the user explicitly approves actions that use their GitHub account.

## Preflight

Run or ask to run:

```bash
gh auth status
git status --short
git remote -v
git branch --show-current
```

Confirm:

- The user is authenticated.
- The working tree contains only intended changes.
- The security audit is complete and has no unresolved `Medium` or `High` findings.
- The branch name is clear.
- The remote target is correct.
- The PR will target upstream, not only the user's fork.

## PR Flow

```bash
git checkout -b BRANCH_NAME
git add PATHS
git commit -m "type: concise summary"
git push -u origin BRANCH_NAME
gh pr create --repo OWNER/REPO --base DEFAULT_BRANCH --head USERNAME:BRANCH_NAME
```

Ask before `git push`, `gh pr create`, `gh pr review`, or `gh issue comment`.

## PR Body

```markdown
## Summary

- 

## Related Issue

Fixes #

## Verification

- 

## Notes

- 

## Security Audit

- 
```

## Output

Return the PR URL, branch name, verification commands, security audit result, and next maintainer-response step.
