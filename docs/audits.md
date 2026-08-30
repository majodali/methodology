# Audit log

The Register recording each audit execution
([Article 9](constitution.md#article-9--audits)): one Entry per audit
run. This is the machine-readable source for *time of last semantic
audit*, which the Article 9 delta-ratio auto-trigger — and `mtool
status`'s delta-ratio report — require.

Entry format (per the [audit process](audit-process.md)): `date — kind
(form | semantic) — scope — audited <short-sha> against methodology
<version> — outcome (pass | <v> violations / <w> warnings / <i> info)
— findings digest or —`. Entries below predating the format extension
remain valid history. Entries arrive by *Audit delivery* on state
transitions; portfolio sweeps are recorded here with scope
*portfolio*.

- 2026-08-18 — form — full tree at bootstrap: link integrity, ad-hoc
  script (transitional, [Risk R2](open-risks.md)) — pass (115 relative
  links/anchors resolve) — —
- 2026-08-20 — form — full tree: link integrity, `mtool links check`
  (first tool-driven run; closes [Risk R2](open-risks.md)) — pass (24
  files, 144 relative links/anchors resolve, 31 external skipped) — —
- 2026-08-20 — form — full tree: `mtool audit form` (first full form
  audit of this repo; closes [Risk R1](open-risks.md)) — pass (15
  in-play rules, no findings, no version lag, no deviations) — —
- 2026-08-21 — form — portfolio sweep (allegro, in-real-life,
  methodology, methodology-tools) — audited against methodology 1.2.0
  — deliveries per the [audit process](audit-process.md):
  [allegro PR #17](https://github.com/majodali/allegro/pull/17) and
  [in-real-life PR #63](https://github.com/majodali/in-real-life/pull/63)
  (both lag transitions after the v1.2.0 release; both repos' prior
  violations confirmed resolved) — methodology clean at pinned 1.2.0
  on its migration branch (no transition from its baseline);
  baseline-establishing deliveries for the clean repos without
  same-kind entries (methodology-tools; template/ops/org pending
  baseline check) deferred to the mechanized sweep (R5, best-effort)
- 2026-08-30 — semantic — full tree — audited f8dfa03 against
  methodology 1.3.0 (v1.4.0 candidate) — pass — review round 1
  ([plans/review-round-1.md](plans/review-round-1.md)): eleven
  interim adjudications confirmed, three seed tensions resolved
  editorially, Workflow-format amendment ratified; first semantic
  baseline for the Article 9 delta-ratio trigger
- 2026-08-30 — form — portfolio sweep (eight governed checkouts +
  three implicit-C0 spot-checks: workbench, graph-analysis,
  chloe-portfolio) — audited against methodology 1.3.0 — clean
  except allegro (Article 8 warning: 1.2.0 lag) and the known
  Workflow-format info on three projects; spot-checks clean at C0;
  chloe-portfolio registered on first observation (M-001) —
  deliveries pending: allegro, in-real-life
