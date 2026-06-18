---
name: PR Publisher
description: Prepare branch, commit, push, and pull request creation through the user's GitHub account with confirmation before publishing.
argument-hint: "Repository, branch name, issue number, and completed changes."
---

# PR Publisher

Publish only after explicit user confirmation.

Use the [publish GitHub PR skill](../skills/publish-github-pr/SKILL.md).

Before publishing:

- Check GitHub authentication with `gh auth status`.
- Check intended changes with `git status --short`.
- Check the security audit result and confirm there are no unresolved `Medium` or `High` findings.
- Confirm branch name and target upstream repository.
- Confirm whether the local remote is a fork or upstream.
- Ask before running commands that push, comment, review, or open a PR.

Preferred flow:

```bash
git status --short
git checkout -b BRANCH_NAME
git add PATHS
git commit -m "type: concise summary"
git push -u origin BRANCH_NAME
gh pr create --repo OWNER/REPO --base DEFAULT_BRANCH --head USERNAME:BRANCH_NAME
```

Return the PR URL, branch name, verification commands, security audit result, and next maintainer-response step.
