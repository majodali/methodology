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

Target: v1.4.0 (minor — normative content).

### Prose & presentation rules and the style guide

- **PR**: this amendment's PR (link recorded at proposal time).
- **Suggested by**: the owner, 2026-08-30, after reading across the
  portfolio; confirmed by the documentation review of the same date
  (metrics and instances recorded in the P- rules' Motivated-by
  fields).
- **Impact**: methodology (`methodology-corpus`) — *accommodated*:
  [style guide](style.md) created (Level 2), P- section opened
  (P-001–P-006), rule bodies gain labeled fields, this repo's own
  documents become migration targets. All C1+ projects —
  *accommodated*: the P- rules bind new and edited prose from
  adoption; existing documents migrate by editorial passes on their
  own schedule. methodology-tools — style lint checks queued as
  future tool work (warnings, not violations).
- **Migration note**: none mandatory — no document requires immediate
  rework; editorial passes are scheduled work, not migration duties.

## v1.3.0 — 2026-08-25

Minor — normative content. All four amendments accepted at interim
adjudications (2026-08-24 and 2026-08-25).

### Links-move external-reference limitation

- **PR**: [#16](https://github.com/majodali/methodology/pull/16).
- **Suggested by**: `mtool links move`
  ([methodology-tools chunk 5](https://github.com/majodali/methodology-tools/pull/8))
  — the founding plan's second promised amendment: the tool rewrites
  inbound links and takes `--tombstone`, but cannot itself know
  whether a document is externally referenced.
- **Impact**: methodology (`methodology-corpus`) — *accommodated*:
  Article 10's tombstone bullet gains the transitional parenthetical;
  Risk R6 opened (awaits a census-maintained external-reference
  index). All projects — *not affected* in duties: the tombstone MUST
  already bound movers; this records how it is discharged meanwhile.
- **Migration note**: none.

### Project families

- **PR**: [#19](https://github.com/majodali/methodology/pull/19).
- **Suggested by**: the in-real-life family (app + ops + org — the D6
  split's siblings; the owner's family-wide sweep entry in
  in-real-life's Audit log) and the methodology's own trio
  (methodology + methodology-tools + project-orchestrator);
  owner-raised at the chunk-3 access ruling, design ratified
  2026-08-24.
- **Impact**: all projects — *accommodated, opt-in*: a new optional
  Classification field (**Family**; omission default none) and the
  *Project family* term. The field is outside the Article 4
  decidability basis, so rule selection is untouched. methodology
  (`methodology-corpus`) — declares family lead; the Portfolio
  register gains a Families section; the census reconciles family
  symmetry (within its existing declaration-accuracy remit).
- **Migration note**: none — declaring a Family is optional;
  standalone projects change nothing.

### Template type and Q-001

- **PR**: [#20](https://github.com/majodali/methodology/pull/20).
- **Suggested by**: serverless-web-app-template — the practices'
  reference implementation, whose §5 gap analysis showed derived
  projects start non-compliant unless the template ships compliance;
  owner-raised at the chunk-3 access ruling, ratified 2026-08-24.
- **Impact**: Classification type enum gains `template`
  (amendment-controlled values — this is the designed channel). The
  Q- section opens with Q-001 (template scaffolds stay compliant),
  mechanically checkable via the classify/audit loop.
  serverless-web-app-template — *accommodated*: adopting the type is
  its own Classification decision, made in that repo; until then it
  remains implicit C0 and Q-001 is not in play there. All other
  projects — *not affected*.
- **Migration note**: none — no existing declaration uses the new
  value.

### Custom definitions by citation

- **PR**: [#21](https://github.com/majodali/methodology/pull/21).
- **Suggested by**: project-orchestrator's managed-project enrollment —
  managed projects adopt its *Plan register* and *Cost log* types by
  citing the orchestrator's process specification from their own
  Custom definitions sections, a shape Article 7 homed but did not
  name; ratified 2026-08-24.
- **Impact**: constitutional (one sentence in Article 7, enacted by
  the owner's merge per Article 2). All projects — *accommodated,
  opt-in*: citation-form definitions become legal by name; the citing
  Classification stays the required home, the defining project's
  document stays authoritative, and audits stop reading every
  enrollment as N independent convergent definitions.
  project-orchestrator — its enrollment pattern is now the named
  instance.
- **Migration note**: none.

## v1.2.0 — 2026-08-21

Minor — normative content. Both amendments accepted at interim
adjudications (2026-08-20 and 2026-08-21).

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

- **PR**: [#12](https://github.com/majodali/methodology/pull/12).
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
