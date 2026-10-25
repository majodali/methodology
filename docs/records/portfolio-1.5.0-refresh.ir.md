# IR: Portfolio register refresh after the 1.5.0 migration round

Reader: RD-1 (human owner, in conversation).
Purpose: report. The register refresh that records the state of the methodology 1.5.0 migration round, which closes when the one lagging project's PR merges.
Status: delivered (three review rounds at portfolio-1.5.0-refresh.review.md; round 3 verdict readable; this is the third IR; C14 and R3, added after the third rendering and never rendered, were removed when the round-trip check found C14 absent from the render map, 2026-10-25; E4 carries what C14 said)
Source: the pinned methodology version observed in nine checkouts on 2026-10-25, and the state of one pull request on GitHub the same day.

## Terms

T1. Migration round: the set of per-project migration PRs that follows one methodology release. [proposed: this IR]

## Claims

C1. Eight of the nine projects listed with a pin in the Portfolio register now pin methodology 1.5.0. evidence: E1. [decided: observed Classifications, 2026-10-25]

C2. The eight projects pinning methodology 1.5.0 are: methodology; methodology-tools; allegro; in-real-life; in-real-life-ops; in-real-life-org; project-orchestrator; project-orchestrator-service. evidence: E1. [decided: observed Classifications, 2026-10-25]

C3. The Agent bootstrap of each of the eight projects contains the heading "cached from W-008", the heading of the block that W-008 (reports map their deliverables) requires. evidence: E2. [decided: observed bootstraps, 2026-10-25]

C4. serverless-web-app-template still pins methodology 1.4.0. evidence: E1. [decided: observed Classification, 2026-10-25]

C5. The Agent bootstrap of serverless-web-app-template does not contain the heading "cached from W-008". evidence: E2. [decided: observed bootstrap, 2026-10-25]

C6. The migration PR of serverless-web-app-template, serverless-web-app-template #4, was opened on 2026-09-02. evidence: E3. [decided: GitHub, 2026-10-25]

C7. serverless-web-app-template #4 was still open on 2026-10-25. evidence: E3. [decided: GitHub, 2026-10-25]

C8. In docs/registers/portfolio.md, the rows methodology, methodology-tools, allegro, in-real-life, in-real-life-ops, in-real-life-org, project-orchestrator and project-orchestrator-service now read "pinned 1.5.0". evidence: E5. [proposed: this IR]

C9. In docs/registers/portfolio.md, the serverless-web-app-template row now reads "pinned 1.4.0". evidence: E5. [proposed: this IR]

C10. The serverless-web-app-template row now names serverless-web-app-template #4 as its open migration PR. evidence: E5. [proposed: this IR]

C11. The allegro row now records that allegro's deviation D-1, its deviation from the per-chunk gate of W-001 (two delivery modes, human-gated), is retired. evidence: E4, E5. [proposed: this IR]

C12. The allegro row now records two methodology proposals in allegro's docs/plans/ with the status draft proposal: documentation-standards-delta.md and conceptual-model-methodology-delta.md. evidence: E4, E5. [proposed: this IR]

C13. The Census line at the top of docs/registers/portfolio.md now records that pins were refreshed from observed Classifications on 2026-10-25. evidence: E5. [proposed: this IR]


## Relations

R1. C8 depends-on C1 because the register copies the pin each Classification declares.

R2. C9 depends-on C4 because a row may not show a pin the project does not declare.


## Evidence

E1. The Pinned methodology version field of docs/classification.md in each of the nine checkouts, read 2026-10-25.

E2. A search for the string "cached from W-008" in CLAUDE.md of each checkout, 2026-10-25: present in eight, absent in serverless-web-app-template.

E3. https://github.com/majodali/serverless-web-app-template/pull/4: opened 2026-09-02; state open when read on 2026-10-25.

E4. allegro docs/classification.md, deviation D-1's Disposition field, "tracked as B-131"; allegro docs/backlog.md, 2026-10-25, the line "B-131 is closed"; allegro docs/plans/documentation-standards-delta.md and docs/plans/conceptual-model-methodology-delta.md, each with the status line "draft proposal".

E5. The diff of docs/registers/portfolio.md on branch portfolio-1.5.0-refresh: nine rows and the Census line.

## Asks

A1. Merge serverless-web-app-template PR #4 so the migration round closes. Depends: C4, C5, C7.

A2. Review and merge this register refresh. Depends: C8, C9, C10, C11, C12, C13.

A3. Ratify or strike the term migration round. Depends: T1.
