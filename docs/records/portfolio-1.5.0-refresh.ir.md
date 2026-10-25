# IR: Portfolio register refresh after the 1.5.0 migration round

Reader: RD-1 (human owner, in conversation).
Purpose: report. The register refresh that closes the 1.5.0 migration round, and the one project still lagging.
Status: draft
Source: the owner's merges of the nine migration PRs opened 2026-09-02; checkouts of the nine repositories read 2026-10-25.

## Terms

T1. Migration round: the set of per-project migration PRs that follows a methodology release. defined-at: https://github.com/majodali/methodology/blob/v1.5.0/docs/release-process.md [decided: methodology release process, step 5]

## Claims

C1. Eight of the nine projects pinned in the Portfolio register now pin methodology 1.5.0. evidence: E1. [decided: observed Classifications, 2026-10-25]

C2. The eight are: methodology; methodology-tools; allegro; in-real-life; in-real-life-ops; in-real-life-org; project-orchestrator; project-orchestrator-service. evidence: E1. [decided: observed Classifications, 2026-10-25]

C3. Each of the eight carries W-008's required reporting block in its Agent bootstrap. evidence: E2. [decided: observed bootstraps, 2026-10-25]

C4. serverless-web-app-template still pins 1.4.0 and carries no reporting block. evidence: E1, E2. [decided: observed Classification and bootstrap, 2026-10-25]

C5. The template's migration PR, serverless-web-app-template #4, has been open since 2026-09-02. evidence: E3. [decided: GitHub, 2026-10-25]

C6. The register's nine pinned rows now read 1.5.0, except the template's row, which reads 1.4.0 and names its open PR. [proposed: this IR]

C7. allegro's row records that deviation D-1 against W-001 (two delivery modes, human-gated) is retired and that two methodology proposals await adjudication in its docs/plans/. evidence: E4. [decided: allegro Backlog B-131 closed; allegro docs/plans/, 2026-10-25]

C8. The census note records that pins were refreshed from observed Classifications on 2026-10-25. [proposed: this IR]

C9. A PR body and a Backlog entry are rendered from this IR by the communication pipeline's paraphraser, as the pipeline's first live run on a methodology deliverable. [decided: pilot plan, chunk 2, 2026-10-24]

## Relations

R1. C6 depends-on C1 because the register caches what the Classifications declare.

R2. C6 depends-on C4 because a row may not claim a pin the project does not declare.

## Evidence

E1. The Pinned methodology version field of docs/classification.md in each of the nine checkouts, read 2026-10-25.

E2. grep for "cached from W-008" in CLAUDE.md of each checkout, 2026-10-25: present in eight, absent in serverless-web-app-template.

E3. https://github.com/majodali/serverless-web-app-template/pull/4, opened 2026-09-02, state open on 2026-10-25.

E4. allegro docs/backlog.md, 2026-10-25: "B-131 is closed"; allegro docs/plans/documentation-standards-delta.md and conceptual-model-methodology-delta.md, both status draft proposal.

## Asks

A1. Merge serverless-web-app-template PR #4 so the round closes. Depends: C4, C5.

A2. Review and merge this register refresh. Depends: C6.
