# CLAUDE.md — Atlan AI Agent Guidelines

> **Applies To:** `argo-workflows`
> **Full security policy:** See `AGENTS.md`

---

## Security

`argo-workflows` contains Atlan's Argo Workflows configuration. Key surfaces: workflow RBAC, artifact repository credentials, and workflow templates executing shell commands.

### Security Contact
Security questions → `#bu-security-and-it` on Slack.

### General Invariants
- **[MUST]** Workflow ServiceAccounts: namespace-scoped Role (not ClusterRole), least-privilege.
- **[MUST]** Artifact repository credentials stored in Kubernetes Secrets via `secretKeyRef`.
- **[SHOULD]** Workflow templates executing shell scripts must validate all input parameters.
