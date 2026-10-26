# IR: Portfolio register refresh after the 1.5.0 migration round

Reader: RD-1 (human owner, in conversation).
Purpose: report. The register refresh that records the close of the methodology 1.5.0 migration round.
Status: delivered (fourth IR, rendered by the paraphraser 2026-10-25 under disposition D1; revised 2026-10-25 after serverless-web-app-template PR #4 merged: C4, C5, C6, C7, C9, C10, R2 and A1 removed, C15 to C18 and E6 added, C1 and C2 reworded; three review rounds at portfolio-1.5.0-refresh.review.md, round 3 verdict readable, on the third IR; C14 and R3 of the third IR were removed when the round-trip check found C14 absent from the render map; E4 carries what C14 said)
Source: the pinned methodology version observed in nine checkouts on 2026-10-25, and the state of one pull request on GitHub the same day, read twice.

## Terms

T1. Migration round: the set of per-project migration PRs that follows one methodology release. [proposed: this IR]

## Claims

C1. All nine projects listed with a pin in the Portfolio register now pin methodology 1.5.0. evidence: E1, E6. [decided: observed Classifications, 2026-10-25]

C2. The nine projects pinning methodology 1.5.0 are: methodology; methodology-tools; allegro; in-real-life; in-real-life-ops; in-real-life-org; project-orchestrator; project-orchestrator-service; serverless-web-app-template. evidence: E1, E6. [decided: observed Classifications, 2026-10-25]

C3. The Agent bootstrap of each of the nine projects contains the heading "cached from W-008", the heading of the block that W-008 (reports map their deliverables) requires. evidence: E2, E6. [decided: observed bootstraps, 2026-10-25]





C8. In docs/registers/portfolio.md, the rows methodology, methodology-tools, allegro, in-real-life, in-real-life-ops, in-real-life-org, project-orchestrator and project-orchestrator-service now read "pinned 1.5.0". evidence: E5. [proposed: this IR]

C15. serverless-web-app-template PR #4, its 1.5.0 migration PR, was merged on 2026-10-25. evidence: E6. [decided: GitHub, 2026-10-25]

C16. The 1.5.0 migration round is closed. [inferred: R2]

C17. In docs/registers/portfolio.md, the serverless-web-app-template row now reads "pinned 1.5.0". evidence: E5. [proposed: this IR]

C18. The serverless-web-app-template row now records its 1.5.0 migration as closed, with PR #4 opened 2026-09-02 and merged 2026-10-25. evidence: E5. [proposed: this IR]



C11. The allegro row now records that allegro's deviation D-1, its deviation from the per-chunk gate of W-001 (two delivery modes, human-gated), is retired. evidence: E4, E5. [proposed: this IR]

C12. The allegro row now records two methodology proposals in allegro's docs/plans/ with the status draft proposal: documentation-standards-delta.md and conceptual-model-methodology-delta.md. evidence: E4, E5. [proposed: this IR]

C13. The Census line at the top of docs/registers/portfolio.md now records that pins were refreshed from observed Classifications on 2026-10-25. evidence: E5. [proposed: this IR]


## Relations

R1. C8 depends-on C1 because the register copies the pin each Classification declares.

R2. C16 depends-on C1 because a migration round is the set of per-project migration PRs that follows one release, and every project in the set now pins the release.


## Evidence

E1. The Pinned methodology version field of docs/classification.md in each of the nine checkouts, read 2026-10-25.

E2. A search for the string "cached from W-008" in CLAUDE.md of each checkout, 2026-10-25: present in eight, absent in serverless-web-app-template.

E3. https://github.com/majodali/serverless-web-app-template/pull/4: opened 2026-09-02; state open when read on 2026-10-25.

E4. allegro docs/classification.md, deviation D-1's Disposition field, "tracked as B-131"; allegro docs/backlog.md, 2026-10-25, the line "B-131 is closed"; allegro docs/plans/documentation-standards-delta.md and docs/plans/conceptual-model-methodology-delta.md, each with the status line "draft proposal".

E5. The diff of docs/registers/portfolio.md on branch portfolio-1.5.0-refresh: nine rows and the Census line.

E6. serverless-web-app-template at origin/main on 2026-10-25, after the merge of its PR #4: docs/classification.md declares pinned methodology version 1.5.0; CLAUDE.md contains "cached from W-008"; https://github.com/majodali/serverless-web-app-template/pull/4 shows the merge commit c4a8d52.

## Asks

A1. Review and merge this register refresh. Depends: C8, C11, C12, C13, C17, C18.

A2. Ratify or strike the term migration round. Depends: T1.
