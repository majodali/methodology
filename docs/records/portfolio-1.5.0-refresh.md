The portfolio register refresh for the 1.5.0 migration round, meaning the set of per-project migration PRs that follows one methodology release, is ready for your review.

## Asks

1. Merge serverless-web-app-template PR [#4](https://github.com/majodali/serverless-web-app-template/pull/4) so the migration round closes.
2. Review and merge this register refresh.
3. Ratify or strike the term migration round.

## What is already covered

All observations below were made on 2026-10-25.

Eight of the nine projects pinned in the Portfolio register now pin methodology 1.5.0.

The eight are methodology, methodology-tools, allegro, in-real-life, in-real-life-ops, in-real-life-org, project-orchestrator, and project-orchestrator-service.

Each of the eight carries, in its Agent bootstrap, the heading of the block that W-008 (reports map their deliverables) requires.

serverless-web-app-template still pins methodology 1.4.0.

The Agent bootstrap of serverless-web-app-template carries no W-008 block.

The migration PR for serverless-web-app-template, [serverless-web-app-template #4](https://github.com/majodali/serverless-web-app-template/pull/4), was opened 2026-09-02 and was still open on 2026-10-25.

## What changed

All items below are in docs/registers/portfolio.md.

- Eight rows, those of the projects listed above: each now reads "pinned 1.5.0". Review the pin text in each of the eight rows.
- The serverless-web-app-template row: it reads "pinned 1.4.0" and names serverless-web-app-template #4 as open. Review the pin text and the PR reference in this row.
- The allegro row: it records that deviation D-1 (the per-chunk gate deviation against W-001, two delivery modes, human-gated) is retired. Review the retirement entry in this row.
- The allegro row, second entry: it records two methodology proposals awaiting adjudication, allegro's docs/plans/documentation-standards-delta.md and docs/plans/conceptual-model-methodology-delta.md. Review the two file names in this row.
- The Census line at the top: it records that pins were refreshed from observed Classifications on 2026-10-25. Review the date and wording of this line.

## Terms introduced

- **migration round**: the set of per-project migration PRs that follows one methodology release. Provenance: proposed, this IR. Ratification is requested in ask 3.

<!-- render map: T1→lead,Terms A1→Asks.1 A2→Asks.2 A3→Asks.3 C1→covered.¶2 C2→covered.¶3 C3→covered.¶4 C4→covered.¶5 C5→covered.¶6 C6→covered.¶7 C7→changed.b1 C8→changed.b2 C9→changed.b3 C10→changed.b4 C11→changed.b5; note C9 and C10 are marked decided in the IR but are register edits naming a file and row, so they sit under What changed -->
