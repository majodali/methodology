# The audit delivery process

How an audit's results reach the audited project, and when. This is a
Methodology-level (Level 2) document under
[Article 9](constitution.md#article-9--audits), amendable through
[Article 8](constitution.md#article-8--amendments-versions-and-migration).
Normative keywords per BCP 14 (constitution preamble).

The gap it closes (informative): audits run centrally — an agent
session, later a scheduled sweep — and their findings otherwise live
only in terminal output and PR bodies. The audited project never
durably learns its own result. Delivery is delta-triggered so that
frequent runs produce rare deliveries: runs are cheap, state
transitions are the news.

## Results are machine-comparable

Every audit run of a project produces: the audit kind (form |
semantic), the audited commit, the methodology version audited
against, and the **finding fingerprint** — the sorted set of
`(rule ID, severity, file)` over findings of severity *violation* and
*warning*. Three exclusions are deliberate:

- *info* findings are outside the fingerprint (sandbox ages tick
  without the project's state changing);
- message text is outside the fingerprint (tool wording is not
  project state);
- the corpus version is recorded but not compared (a migration that
  changes no findings is not a transition — the project's migration PR
  is its own record).

## The baseline is the project's own log

The comparison baseline for a run is the newest same-kind entry in the
project's own [Audit log](vocabulary.md#defined-terms)
(`docs/audits.md`). No central cache of per-project results exists: a
project's audit history MUST be readable from its own documentation
alone.

## Delivery on transition

When the fingerprint differs from the baseline — or the project has no
same-kind baseline — the Auditor MUST deliver a new entry: a PR
appending the entry to the project's `docs/audits.md`, **creating the
register if the project has none** (first delivery is how a project
acquires its Audit log; none is created ahead of need). Delivery is
**always by PR, never a direct push** — uniform across projects,
compatible with protected mainlines, and the merge is the project's
acknowledgement of its audit state. Delivery PRs are register
maintenance, not amendments; the full report travels in the PR body.

When the fingerprint matches the baseline, nothing is delivered.

## Sweeps are recorded centrally

A portfolio sweep — one run over multiple projects — is recorded as a
single entry in the methodology repo's own Audit log (scope:
*portfolio*, naming the repos swept and the deliveries made), whether
or not any delivery occurred. The methodology logs *that audits ran*;
each project logs *its own transitions* — so silence in a project's
log genuinely means "no change since the last entry."

## Entry format

```
date — kind (form | semantic) — scope — audited <short-sha> against
methodology <version> — outcome (pass | <v> violations / <w> warnings
/ <i> info) — findings digest (rule + file one-liners) or —
```

Entries predating this format remain valid history.

## Transitional discharge

Until `mtool` grows compare-and-deliver support (planned alongside
`mtool census`, methodology-tools chunk 4), delivery is discharged
manually and best-effort by the running agent — transitional
[Risk R5](open-risks.md) per
[Article 11](constitution.md#article-11--transitional-provisions).
