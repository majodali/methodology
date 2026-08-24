# Backlog

The single source of progress truth for this repo
([K-003](rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth));
entries update in the same commit as the work they describe
([W-003](rules/working-agreement.md#w-003--documentation-moves-in-the-same-commit-as-the-work)).

## Completed

- [x] **Corpus import** — split *Constitution & Vocabulary draft v0.7*
  into [constitution.md](constitution.md) (with Article 11, the approved
  adoption edit), [vocabulary.md](vocabulary.md), and
  [rules/](rules/README.md) (K-001–K-009, W-001–W-007, M-001–M-003,
  S-001–S-002, one file per section); imported proposal v0.2 as
  [practices.md](practices.md); rewrote all draft-relative links
  repo-relative and verified every relative link and anchor resolves
  (ad-hoc script — transitional, Risk R2); kept the draft changelogs as
  pre-1.0 history.
- [x] **Methodology Classification and Portfolio register** (draft open
  item 6) — first Classification ever written:
  [classification.md](classification.md), `methodology-corpus` / C1 / S0
  / none-local, pinned 1.0.0; Binding block in `CLAUDE.md`;
  [Portfolio register](registers/portfolio.md) seeded from a full
  account census (19 repositories, all implicit C0 except this repo).
  **Census confirmation by the owner is pending at the chunk-1 gate.**
- [x] **Skeletons** — copyable starting files under
  [skeletons/](../skeletons/) per [practices §6](practices.md), scoped
  to the kickoff list: minimal `CLAUDE.md` (Binding block + pointers,
  K-002), `docs/classification.md`, `docs/backlog.md`,
  `docs/decisions.md`, `docs/open-risks.md`, `docs/plans/TEMPLATE.md`
  (encoding the K-007 status-line contract), `pull_request_template.md`
  (D2), `ci-verify.yml` (D3). Radar/hypothesis skeletons from §6's
  sketch deliberately not created (K-005: no empty ceremony ahead of
  need; kickoff list governs).
- [x] **Census confirmed and methodology-tools cross-registered** —
  owner confirmed the census at the chunk-1 gate (2026-08-18), ruling
  the three unobservable practices-§1.1 examples disregarded;
  [methodology-tools](https://github.com/majodali/methodology-tools)
  bootstrapped under v1.0.0 (component/library, C1, S0, package
  registry; founding plan imported, status draft) and its
  [Portfolio entry](registers/portfolio.md) updated from implicit C0 to
  its declared summary (M-001).

- [x] **Bootstrap merged** — PR #1 merged to `main` (2026-08-18) and
  `main` made the default branch. Cross-repo links from
  methodology-tools now resolve.

- [x] **v1.0.0 released** — owner created the annotated tag `v1.0.0`
  on `main` (2026-08-18) and deleted the merged single-use bootstrap
  branch (W-006). Owner rulings adopted as standing process: version
  tags are created by the owner after PR review (the release ceremony),
  and `main` accepts pushes from the owner only — recorded in the
  [Classification's process records](classification.md).

- [x] **Amendment & release process** (amendment; the merge is
  acceptance) — Article 8 amended: interim adjudication minted and the
  release mechanics homed in [release-process.md](release-process.md)
  (Level 2, amendable); [Release register](releases.md) created
  (Keep-a-Changelog shape), seeded with the v1.0.0 section and
  Unreleased entries for this amendment and the audit-log amendment;
  vocabulary: *Interim adjudication*, *Release*, *Release register*,
  *Editorial change*;
  [M-004](rules/mirrors.md#m-004--amendment-prs-carry-their-release-register-entry)
  added. Suggested by the adjudication questions around
  [PR #3](https://github.com/majodali/methodology/pull/3).
- [x] **Audit-log register** (amendment,
  [PR #3](https://github.com/majodali/methodology/pull/3), accepted
  2026-08-20) — [audits.md](audits.md) created, seeded with the
  bootstrap link-check entry; *Audit log* added to the vocabulary's
  Register subtypes. Motivating instance:
  [methodology-tools chunk 1](https://github.com/majodali/methodology-tools/pull/1),
  whose `mtool status` delta-ratio needs a machine-readable
  last-semantic-audit time.
- [x] **v1.1.0 cut** — release PR retitled Unreleased to
  [*v1.1.0 — 2026-08-20*](releases.md): the amendment & release
  process (PR #4) and the audit-log register (PR #3), both accepted at
  the first interim adjudications; the owner creates the annotated tag
  `v1.1.0` after merging (release ceremony). Migration notes: none for
  either amendment — migrations are pin bumps only.

- [x] **Migrated to 1.1.0** — v1.1.0 tagged by the owner 2026-08-20;
  migration PR bumped the [Classification](classification.md) pin and
  the `CLAUDE.md` Binding block, and refreshed this repo's
  [Portfolio row](registers/portfolio.md) (v1.1.0 migration notes:
  none, so the pin bump is the whole migration — release process
  step 5). methodology-tools migrates by its own PR.

- [x] **Risk R2 closed** — link-integrity tooling landed
  (`mtool links check`,
  [methodology-tools chunk 2](https://github.com/majodali/methodology-tools/pull/4));
  first tool-driven run over this tree logged in the
  [Audit log](audits.md) (144 relative links, no findings), the ad-hoc
  bootstrap script retired. Transitional entries R1, R3, R4 remain
  open, so Article 11 stands (its deletion review waits for an empty
  transitional set).

- [x] **Risk R1 closed** — form-audit tooling landed
  (`mtool audit form` + `mtool hooks install`,
  [methodology-tools chunk 3](https://github.com/majodali/methodology-tools/pull/5)).
  This repo's first tool-driven form audit logged in the
  [Audit log](audits.md) (no findings); the first portfolio-wide run
  audited allegro, in-real-life, the template, and both ops repos at
  their declared levels — allegro's findings match its own
  adoption-transition notes, in-real-life has one W-007 gap (no
  README), the implicit-C0 repos audit clean. Portfolio rows for
  allegro and in-real-life refreshed from their observed declarations.
  R3 and R4 remain open, so Article 11 stands.

- [x] **Audit delivery process** (amendment; the merge is acceptance)
  — [audit-process.md](audit-process.md) created (Level 2): audit
  results become machine-comparable finding fingerprints
  (rule/severity/file over violations + warnings; info and message
  text excluded; corpus version recorded, not compared), compared
  against the project's own Audit log, delivered by PR exactly on
  transitions (first delivery creates the register); portfolio sweeps
  recorded centrally in this repo's [Audit log](audits.md). Article 9
  pointer added; vocabulary: *Audit delivery*; Audit-log entry format
  extended; transitional [Risk R5](open-risks.md) opened (manual
  delivery until `mtool` compare-and-deliver, chunk 4).
  Owner-designed 2026-08-21; evidencing instance: the chunk-3 gate
  findings that never reached their projects.

- [x] **v1.2.0 cut** — release PR retitled Unreleased to
  [*v1.2.0 — 2026-08-21*](releases.md): the form-audit delta-scope
  calibration (PR #9) and the audit delivery process (PR #12); the
  owner creates the annotated tag `v1.2.0` after merging (release
  ceremony). Migration notes: none for either amendment — migrations
  are pin bumps only.

- [x] **Migrated to 1.2.0** — v1.2.0 tagged by the owner 2026-08-21;
  pin, Binding block, and Portfolio row bumped (migration notes: none,
  so the pin bump is the whole migration — release process step 5).
  methodology-tools migrates by its own PR.

- [x] **Risks R3 and R5 closed** — census and audit-delivery tooling
  landed
  ([methodology-tools chunk 4](https://github.com/majodali/methodology-tools/pull/7)):
  `mtool census` reconciled all 19 observed repos against the
  [Portfolio register](registers/portfolio.md) on its first run
  (completeness verified; allegro's stale pin refreshed per its drift
  proposal; 12 implicit-C0 spot-check candidates queued for the review
  round), and `mtool audit deliver` mechanizes the
  [audit process](audit-process.md) fingerprint comparison. R4 (links
  move, chunk 5) is the sole remaining transitional entry — Article
  11's deletion review arms when it closes.

- [x] **Links-move external-reference limitation** (amendment; the
  merge is acceptance) — Article 10's tombstone bullet records that,
  until the census maintains an external-reference index, whether a
  document is externally referenced is operator-supplied knowledge
  (`mtool links move` surfaces the duty, `--tombstone` discharges it);
  transitional [Risk R6](open-risks.md) opened. The founding tools
  plan's second promised amendment
  ([methodology-tools chunk 5](https://github.com/majodali/methodology-tools/pull/8)).

## Upcoming
- [ ] **Multi-repo projects** — how to group multiple repositories
  into a single project (e.g. the in-real-life family: app + ops +
  org), and what a family-level Classification or cross-references
  look like (owner-raised, 2026-08-20, at the chunk-3 access ruling).
- [ ] **Template projects' methodology burden** — a project template
  (serverless-web-app-template) carries a different burden than an
  ordinary project: what it ships must keep *derived* projects
  compliant. Think through, perhaps as part of a methodology project
  family (owner-raised, 2026-08-20).
- [ ] **D-/Q-/O- rule extraction pass** — extract the delivery,
  quality, and operations disciplines from
  [practices.md](practices.md) so form audits can see the gap
  analysis's delivery findings (no CI, no PR template, …); each rule
  needs its live motivating instance (Article 6). Deferred out of
  tools chunk 3 by owner ruling, 2026-08-20.
- [ ] **Review-round cadence** — confirm the initial quarterly
  calibration recorded in [classification.md](classification.md), or set
  a different bounded interval (draft open item 3; Article 8).
- [ ] ~~**Form-audit delta scope**~~ **calibration resolved**
  (amendment; this entry merges with its PR): per-file content checks
  delta-scoped, repo-wide invariants full-tree on every audit —
  Article 9's open parenthetical replaced, the deletion blind spot
  closed by construction. Evidencing instance: `mtool audit form`
  (draft open item 1 done).
- [ ] **Semantic-audit auto-trigger calibration** — delta-ratio
  thresholds (initial: 50% at C2, 25% at C3) and whether delta-ratio is
  the right trigger shape at all (draft open item 2; Article 9).
- [ ] **Workflow declaration format** — minimum required structure for
  the stage set and *live* designation in the Classification, and how
  Backlog entries reference stages (draft open item 4).
- [ ] **First review round** — adjudicate the seed's
  [known tensions](rules/README.md#extraction-notes-for-the-first-review-round)
  and the open calibrations above.
