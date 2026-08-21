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

Target: v1.2.0 (minor — normative content).

### Form-audit delta-scope calibration

- **PR**: [#9](https://github.com/majodali/methodology/pull/9).
- **Suggested by**: `mtool audit form`
  ([methodology-tools chunk 3](https://github.com/majodali/methodology-tools/pull/5)) —
  implementing the delta modes forced the Article 9 open calibration
  question; the implementation runs per-file content checks
  delta-scoped and repo-wide invariants (existence rules, link
  integrity, declaration-consistency) full-tree on every audit, which
  closes the known deletion blind spot.
- **Impact**: methodology (`methodology-corpus`) — *accommodated*:
  Article 9's parenthetical resolved; the open Backlog item closes.
  All audited C1+ projects — *not affected* in duties: the calibration
  binds how audits run, not what projects must hold.
- **Migration note**: none.

### Audit delivery process

- **PR**: this amendment's PR (link recorded at proposal time).
- **Suggested by**: the owner, 2026-08-21, after the first
  portfolio-wide form audits — whose findings (allegro's K-003
  relocation, in-real-life's W-007 gap) existed only in a PR body and
  session transcript, never delivered to the audited projects
  (evidencing instance:
  [methodology-tools chunk 3](https://github.com/majodali/methodology-tools/pull/5)
  gate runs).
- **Impact**: methodology (`methodology-corpus`) — *accommodated*:
  Article 9 pointer, `docs/audit-process.md` created, sweep entries in
  its Audit log, transitional Risk R5 opened. The Auditor role — bound
  by the delivery MUST. All audited C1+ projects — *accommodated,
  lightly*: they receive delivery PRs on audit-state transitions
  (merging is acknowledgement; `docs/audits.md` is created on first
  delivery); no duty to act is minted.
- **Migration note**: none — the process binds the Auditor and the
  methodology repo; projects merge delivery PRs as ordinary register
  maintenance.

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
