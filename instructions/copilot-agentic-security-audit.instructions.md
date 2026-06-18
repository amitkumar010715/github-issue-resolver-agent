---
applyTo: "**"
---

# Agentic Security Audit for GitHub Copilot

Before helping publish a pull request, run the shared security audit playbook for the contribution.

Use the repository context, changed files, diff, implementation notes, and verification output. Keep the audit scoped to the changed behavior unless the user asks for a broader review.

Block or flag publishing when unresolved `Medium` or `High` findings remain.

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
