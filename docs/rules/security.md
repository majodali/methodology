# S — Security & privacy (C0 baseline pair)

Seed extraction v0.1 — see the [rule corpus organization and import
notes](README.md).

### S-001 — No secrets in repositories, ever
Applies: [C0+]
Keywords: MUST NOT
Motivated-by: [proposal E1](../practices.md); the template repo's OIDC-only deploys; discharges the Article 7 secret-hygiene placeholder
Cites: —

Secrets, credentials, and long-lived keys MUST NOT appear in any
repository content or history, at any tier — public exploration repos
most of all. CI authenticates via OIDC role assumption; runtime secrets
live in managed secret stores or the ops surface, never in code, config
files, or environment files committed to the repo.

### S-002 — Exposure means rotate and purge, immediately
Applies: [C0+]
Keywords: MUST
Motivated-by: [proposal E1](../practices.md); standard incident practice, adopted as baseline in the founding sessions
Cites: —

On any secret exposure, the credential MUST be rotated immediately and
the exposure purged from history; the event MUST be recorded (Risk
register at C2+, README or Backlog note below that). Rotation is not
optional even if the exposure window seems brief — history is forever.
