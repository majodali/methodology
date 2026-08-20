# Release register

The register of amendments and releases
([release process](release-process.md);
[M-004](rules/mirrors.md#m-004--amendment-prs-carry-their-release-register-entry)).
Shape cites [Keep a Changelog](https://keepachangelog.com/): an
*Unreleased* section holding the current release candidate's content,
then one section per release, newest first. Every amendment PR adds its
own entry to Unreleased in its own diff; rejection removes it. Entries
carry: amendment title and PR link · suggested by (evidencing instance)
· impact assessment (per affected Portfolio project) · migration note.

## Unreleased

(empty — the next accepted amendment opens the next candidate)

## v1.1.0 — 2026-08-20

Minor — normative content. Both amendments accepted at the first
interim adjudications (2026-08-20).

### Amendment & release process

- **PR**: [#4](https://github.com/majodali/methodology/pull/4).
- **Suggested by**: the adjudication of the audit-log amendment
  ([PR #3](https://github.com/majodali/methodology/pull/3)) — the
  owner's decision to adjudicate continuously during early adoption
  surfaced that Article 8 named migration notes and acceptance but
  homed no pipeline (evidencing instance: PR #3 and the 2026-08-19
  working session).
- **Impact**: methodology (`methodology-corpus`) — *accommodated*: the
  new duties (M-004, register upkeep, release PRs) bind this repo's
  process. methodology-tools — *not affected* until it migrates;
  `mtool audit` (plan chunk 3) gains M-004 as a mechanically checkable
  rule. All other Portfolio projects — *not affected*: no
  project-facing duty is minted.
- **Migration note**: none — adopting projects inherit no new duties;
  amendment authors follow the process from acceptance onward.

### Audit-log register

- **PR**: [#3](https://github.com/majodali/methodology/pull/3).
- **Suggested by**: methodology-tools chunk 1
  ([PR #1](https://github.com/majodali/methodology-tools/pull/1)) —
  `mtool status` must report delta-ratio since the last semantic audit
  and reports it *unavailable* without a machine-readable
  last-semantic-audit time.
- **Impact**: methodology — *accommodated* (`docs/audits.md` created,
  seeded with the bootstrap link check). C2/C3 projects (none currently
  pinned above 1.0.0) — the Article 9 delta-ratio trigger becomes
  recordable; no new duty minted. All others — *not affected*.
- **Migration note**: none mandatory — on migrating, a project MAY keep
  a `docs/audits.md`; `mtool` reads it when present.
- *Register note*: this entry was seeded by PR #4 rather than in PR
  #3's own diff — M-004 postdates that proposal. Accepted 2026-08-20.

## v1.0.0 — 2026-08-18

The bootstrap release: Constitution (Articles 1–11), vocabulary, seed
rule corpus (K-001–K-009, W-001–W-007, M-001–M-003, S-001–S-002),
imported practice definitions ([practices.md](practices.md)), adopter
skeletons, and the repo's own governance (Classification, Portfolio
register, Risk register). First version — no migration notes; predates
this register (entry reconstructed at the register's creation).
