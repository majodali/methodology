# Audit log

The Register recording each audit execution
([Article 9](constitution.md#article-9--audits)): one Entry per audit
run. This is the machine-readable source for *time of last semantic
audit*, which the Article 9 delta-ratio auto-trigger — and `mtool
status`'s delta-ratio report — require.

Entry format: `date — kind (form | semantic) — scope — outcome —
findings pointer (or —)`.

- 2026-08-18 — form — full tree at bootstrap: link integrity, ad-hoc
  script (transitional, [Risk R2](open-risks.md)) — pass (115 relative
  links/anchors resolve) — —
