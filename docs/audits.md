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
