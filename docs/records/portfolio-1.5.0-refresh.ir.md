# IR: Portfolio register refresh after the 1.5.0 migration round

Reader: RD-1 (human owner, in conversation).
Purpose: report. The register refresh that closes the 1.5.0 migration round, and the one project still lagging.
Status: reviewed (round 1 review at portfolio-1.5.0-refresh.review.md; this is the amended IR)
Source: the owner's merges of eight of the nine migration PRs opened 2026-09-02; checkouts of the nine repositories read 2026-10-25.

## Terms

T1. Migration round: the set of per-project migration PRs that follows one methodology release. [proposed: this IR]

## Claims

C1. Eight of the nine projects pinned in the Portfolio register now pin methodology 1.5.0. evidence: E1. [decided: observed Classifications, 2026-10-25]

C2. The eight are: methodology; methodology-tools; allegro; in-real-life; in-real-life-ops; in-real-life-org; project-orchestrator; project-orchestrator-service. evidence: E1. [decided: observed Classifications, 2026-10-25]

C3. Each of the eight carries, in its Agent bootstrap, the heading of the block that W-008 (reports map their deliverables) requires. evidence: E2. [decided: observed bootstraps, 2026-10-25]

C4. serverless-web-app-template still pins methodology 1.4.0. evidence: E1. [decided: observed Classification, 2026-10-25]

C5. serverless-web-app-template's Agent bootstrap carries no W-008 block. evidence: E2. [decided: observed bootstrap, 2026-10-25]

C6. The template's migration PR, serverless-web-app-template #4, was opened 2026-09-02 and was still open on 2026-10-25. evidence: E3. [decided: GitHub, 2026-10-25]

C7. In docs/registers/portfolio.md, the eight rows named in C2 now read "pinned 1.5.0". evidence: E5. [proposed: this IR]

C8. In docs/registers/portfolio.md, the serverless-web-app-template row reads "pinned 1.4.0" and names serverless-web-app-template #4 as open. evidence: E5. [proposed: this IR]

C9. In docs/registers/portfolio.md, the allegro row records that deviation D-1 (the per-chunk gate deviation against W-001, two delivery modes, human-gated) is retired. evidence: E4, E5. [decided: allegro Backlog, B-131 closed, 2026-10-25]

C10. The allegro row also records two methodology proposals awaiting adjudication: allegro's docs/plans/documentation-standards-delta.md and docs/plans/conceptual-model-methodology-delta.md. evidence: E4, E5. [decided: allegro docs/plans/, 2026-10-25]

C11. The Census line at the top of docs/registers/portfolio.md records that pins were refreshed from observed Classifications on 2026-10-25. evidence: E5. [proposed: this IR]

## Relations

R1. C7 depends-on C1 because the register copies the pin each Classification declares.

R2. C8 depends-on C4 because a row may not show a pin the project does not declare.

## Evidence

E1. The Pinned methodology version field of docs/classification.md in each of the nine checkouts, read 2026-10-25.

E2. A search for the heading "cached from W-008" in CLAUDE.md of each checkout, 2026-10-25: present in eight, absent in serverless-web-app-template.

E3. https://github.com/majodali/serverless-web-app-template/pull/4, opened 2026-09-02, state open on 2026-10-25.

E4. allegro docs/backlog.md, 2026-10-25, line "B-131 is closed". allegro docs/plans/, 2026-10-25, two files with status draft proposal.

E5. The diff of docs/registers/portfolio.md on branch portfolio-1.5.0-refresh: nine rows and the Census line.

## Asks

A1. Merge serverless-web-app-template PR #4 so the migration round closes. Depends: C4, C5, C6.

A2. Review and merge this register refresh. Depends: C7, C8, C11.

A3. Ratify or strike the term migration round. Depends: T1.
