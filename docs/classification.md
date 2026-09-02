# Classification

The binding declaration for `majodali/methodology`
([Constitution Article 9](constitution.md#article-9--audits): the
methodology repo is itself a project under its own Constitution). Field
definitions and omission defaults:
[vocabulary](vocabulary.md#artifact-types).

- **C-tier**: C1
- **Pinned methodology version**: 1.5.0 (compliance target; migrated
  from 1.4.0 on 2026-09-02 — v1.5.0 carries one migration note, the
  W-008 bootstrap block, which this repo's `CLAUDE.md` and
  [skeletons/CLAUDE.md](../skeletons/CLAUDE.md) already carry from the
  amendment's own diff)
- **S-level**: S0
- **Type**: `methodology-corpus` (reserved singleton, Article 9)
- **Target**: none/local
- **Workflow**: none declared (⇒ `deployed` is false)
- **Family**: methodology (lead) — members reference this repo's
  corpus and change process; see the
  [Portfolio register's Families section](registers/portfolio.md#families)

## Process records

- **Review-round cadence**: N = 3 minor releases — the calibration for
  [Article 8](constitution.md#article-8--amendments-versions-and-migration)'s
  two cycle-based floors (rounds at most N minor releases apart; parked
  items adjudicated within N minor releases of parking). Owner-set
  2026-08-30, replacing the initial quarterly calibration. Review
  round 1 was held 2026-08-30, before the v1.4.0 cut. Two minor
  releases have shipped since (v1.4.0, v1.5.0), so the next round is
  owed by v1.7.0 and no round is due now.
- **Release ceremony** (owner ruling, 2026-08-18): version tags are
  created by the human owner, on `main`, after PR review — never
  pre-merge on a branch, and never by an agent. `main` accepts pushes
  from the owner only; agent work lands by PR from single-use
  outcome-named branches
  ([W-006](rules/working-agreement.md#w-006--names-follow-outcomes-branches-are-single-use)).

## Deviation register

No deviations recorded.

## Custom definitions

No custom definitions.
