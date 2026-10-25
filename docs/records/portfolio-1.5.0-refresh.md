# Portfolio register refresh after the 1.5.0 migration round

Eight of the nine projects pinned in the Portfolio register now pin methodology 1.5.0.

## Asks

1. Merge [serverless-web-app-template #4](https://github.com/majodali/serverless-web-app-template/pull/4) so the migration round closes.
2. Review and merge this Portfolio register refresh.

## What is already covered

The projects that pin methodology 1.5.0 are methodology, methodology-tools, allegro, in-real-life, in-real-life-ops, in-real-life-org, project-orchestrator, and project-orchestrator-service. Each project that pins methodology 1.5.0 carries the reporting block that W-008 (reports map their deliverables) requires, in its Agent bootstrap. serverless-web-app-template still pins methodology 1.4.0 and carries no reporting block. The migration PR for serverless-web-app-template, [serverless-web-app-template #4](https://github.com/majodali/serverless-web-app-template/pull/4), has been open since 2026-09-02. The allegro row records deviation D-1 against W-001 (two delivery modes, human-gated) as retired and two methodology proposals as awaiting adjudication in allegro docs/plans/. The communication pipeline's paraphraser renders a PR body and a Backlog entry from the claims list behind this report, as the pipeline's first live run on a methodology deliverable.

## What changed

In the Portfolio register, the nine pinned rows read 1.5.0, except the serverless-web-app-template row, which reads 1.4.0 and names serverless-web-app-template #4. The census note records that pins were refreshed from observed Classifications on 2026-10-25. The register rows depend on the pins observed in Classifications, because the register caches what the Classifications declare. The serverless-web-app-template row depends on its observed 1.4.0 pin, because a row may not claim a pin that the project does not declare.

## Terms introduced

**Migration round**: the set of per-project migration PRs that follows a methodology release. It is defined in step 5 of the [methodology release process](https://github.com/majodali/methodology/blob/v1.5.0/docs/release-process.md).

<!-- render map: C1→¶1 C2→¶3 C3→¶3 C4→¶3 C5→¶3 C6→¶4 C7→¶3 C8→¶4 C9→¶3 R1→¶4 R2→¶4 A1→¶2 A2→¶2 T1→¶5 -->
