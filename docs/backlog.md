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

## Upcoming

- [ ] Owner confirms the Portfolio census (chunk-1 gate); then tag
  v1.0.0.
- [ ] **Review-round cadence** — confirm the initial quarterly
  calibration recorded in [classification.md](classification.md), or set
  a different bounded interval (draft open item 3; Article 8).
- [ ] **Form-audit delta scope** — how far beyond the day's change
  deltas a form audit must reach, including the known blind spot of
  deletions breaking inbound links in unchanged files (draft open item
  1; Article 9).
- [ ] **Semantic-audit auto-trigger calibration** — delta-ratio
  thresholds (initial: 50% at C2, 25% at C3) and whether delta-ratio is
  the right trigger shape at all (draft open item 2; Article 9).
- [ ] **Workflow declaration format** — minimum required structure for
  the stage set and *live* designation in the Classification, and how
  Backlog entries reference stages (draft open item 4).
- [ ] **Audit-log register** (`docs/audits.md`) — awaits its amendment,
  to be proposed by the
  [methodology-tools plan](https://github.com/majodali/methodology-tools)
  (its chunk 1 motivates it); not created ahead of adjudication
  (Article 8: agents MUST NOT self-apply proposed practice).
- [ ] **First review round** — adjudicate the seed's
  [known tensions](rules/README.md#extraction-notes-for-the-first-review-round)
  and the open calibrations above.
