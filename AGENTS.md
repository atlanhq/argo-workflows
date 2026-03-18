# AGENTS.md — Atlan AI Agent Guidelines

> **Applies To:** `argo-workflows`
> **Companion file:** See `CLAUDE.md` for the lean summary.

---

## Security

`argo-workflows` contains Atlan's Argo Workflows deployment configuration.

### Security Contact
`#bu-security-and-it` on Slack.

---

### General Invariants

- **[MUST]** Workflow ServiceAccounts: namespace-scoped Role, not ClusterRole.
- **[MUST]** Artifact credentials: Kubernetes `secretKeyRef` only — never inline in workflow YAML.
- **[SHOULD]** Shell script templates: validate `{{inputs.parameters.*}}` before use in shell commands.
- **[SHOULD]** Enable Argo Workflows SSO with Atlan's OIDC provider.
