# Risk register

Transitional entries per
[Constitution Article 11](constitution.md#article-11--transitional-provisions):
audit duties whose tooling does not yet exist are discharged manually and
best-effort until the named tooling lands (the `mtool` CLI planned in
[methodology-tools](https://github.com/majodali/methodology-tools)).
Transitional status ends per entry when its tooling lands; Article 11 is
reviewed for deletion once no transitional entries remain.

- **R1** — Daily form audits
  ([Article 9](constitution.md#article-9--audits)) are manual and
  best-effort — awaited `mtool audit form` — **closed 2026-08-20**: the
  tooling landed with
  [methodology-tools chunk 3](https://github.com/majodali/methodology-tools/pull/5)
  (full, `--staged`, and `--changed-since` modes plus the git
  pre-commit mirror via `mtool hooks install`); this repo's first
  tool-driven form audit is recorded in the [Audit log](audits.md), and
  the first portfolio-wide run audited allegro, in-real-life, the
  template, and both ops repos against their declared classifications.
  Per Article 11, transitional status for this gap has ended.
- **R2** — Link-integrity checking (Articles 9–10) is manual — the
  bootstrap verification ran via an ad-hoc script, not kept tooling —
  awaited `mtool links check` — **closed 2026-08-20**: the tooling
  landed with
  [methodology-tools chunk 2](https://github.com/majodali/methodology-tools/pull/4);
  first run over this tree recorded in the [Audit log](audits.md)
  (144 relative links, no findings — matching the retired script). Per
  Article 11, transitional status for this gap has ended.
- **R3** — The Portfolio census
  ([M-002](rules/mirrors.md#m-002--the-review-round-audit-and-census-run))
  is manual — first census run by hand at bootstrap via account
  enumeration — awaits `mtool census` (methodology-tools chunk 4) — open.
- **R4** — Move/rename obligations
  ([Article 10](constitution.md#article-10--naming-moves-and-traceability):
  automatic inbound-link rewrite, heavy-linkage warnings, tombstones for
  externally referenced documents) are manual — awaits `mtool links move`
  (methodology-tools chunk 5) — open.
- **R5** — Audit delivery
  ([audit-process.md](audit-process.md)) is manual — the running agent
  compares finding fingerprints against each project's Audit log and
  raises delivery PRs by hand — awaits `mtool` compare-and-deliver
  (planned alongside `mtool census`, methodology-tools chunk 4) — open.
