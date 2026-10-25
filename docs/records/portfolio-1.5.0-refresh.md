The portfolio register refresh in docs/registers/portfolio.md is ready for your review, and one pull request still needs a merge.

## Asks

1. Merge [serverless-web-app-template #4](https://github.com/majodali/serverless-web-app-template/pull/4) so the migration round closes. A **migration round** is the set of per-project migration PRs that follows one methodology release.
2. Review and merge this register refresh in docs/registers/portfolio.md.
3. Ratify or strike the term migration round.

## What is already covered

- Eight of the nine projects listed with a pin in the Portfolio register now pin methodology 1.5.0.
- The eight projects pinning methodology 1.5.0 are: methodology; methodology-tools; allegro; in-real-life; in-real-life-ops; in-real-life-org; project-orchestrator; project-orchestrator-service.
- The Agent bootstrap of each of the eight projects contains the heading "cached from W-008", the heading of the block that W-008 (reports map their deliverables) requires.
- serverless-web-app-template still pins methodology 1.4.0.
- The Agent bootstrap of serverless-web-app-template does not contain the heading "cached from W-008".
- The migration PR of serverless-web-app-template, serverless-web-app-template #4, was opened on 2026-09-02.
- serverless-web-app-template #4 was still open on 2026-10-25.

## What changed

- docs/registers/portfolio.md, rows methodology, methodology-tools, allegro, in-real-life, in-real-life-ops, in-real-life-org, project-orchestrator and project-orchestrator-service, now read "pinned 1.5.0". Check that each of the eight rows carries that text.
- docs/registers/portfolio.md, row serverless-web-app-template, now reads "pinned 1.4.0". Check that the text matches the pin observed in its Classification.
- docs/registers/portfolio.md, row serverless-web-app-template, now names serverless-web-app-template #4 as its open migration PR. Check the PR number in that row.
- docs/registers/portfolio.md, row allegro, now records that allegro's deviation D-1 is retired. D-1 is allegro's deviation from the per-chunk gate of W-001 (two delivery modes, human-gated). Check the retirement wording in that row.
- docs/registers/portfolio.md, row allegro, now records two methodology proposals in allegro's docs/plans/ with the status draft proposal: documentation-standards-delta.md and conceptual-model-methodology-delta.md. Check both file names and the status in that row.
- docs/registers/portfolio.md, the Census line at the top, now records that pins were refreshed from observed Classifications on 2026-10-25. Check the date and the wording of that line.

## Terms introduced

- **Migration round**: the set of per-project migration PRs that follows one methodology release. Status: proposed.

<!-- render map: C1→What is already covered bullet 1; C2→What is already covered bullet 2; C3→What is already covered bullet 3; C4→What is already covered bullet 4; C5→What is already covered bullet 5; C6→What is already covered bullet 6; C7→What is already covered bullet 7; C8→What changed bullet 1; C9→What changed bullet 2; C10→What changed bullet 3; C11→What changed bullet 4; C12→What changed bullet 5; C13→What changed bullet 6; T1→Asks 1 (definition) and Terms introduced; A1→Asks 1; A2→Asks 2; A3→Asks 3 -->
