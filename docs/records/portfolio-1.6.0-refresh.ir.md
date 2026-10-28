# IR: Portfolio register refresh for methodology 1.6.0

Reader: RD-1
Purpose: report. The register refresh that closes the 1.6.0 migration round: every pinned project observed at 1.6.0 with the amended W-008 block, the Portfolio register's rows and census line updated.
Status: rendered (paraphraser, 2026-10-28, disposition D1 by BP-07; round trip 11 of 11; declared 3, changed 3, surprises 0, misses 0)
Source: the owner's instruction of 2026-10-28 ("All merged - go ahead with the register refresh"); the ten merged migration PRs; the observed Classifications and bootstraps of ten checkouts on 2026-10-28.
Footprint: docs/registers/portfolio.md; docs/records/portfolio-1.6.0-refresh.ir.md; docs/records/portfolio-1.6.0-refresh.md

## Terms

T1. Migration round. defined-at: ../vocabulary.md#def-migration-round [decided: owner, 2026-10-26]

## Claims

C1. All ten projects with a pin in the Portfolio register pin methodology 1.6.0, observed in their Classifications on 2026-10-28. evidence: E1. [decided: the ten checkouts, 2026-10-28]

C2. The ten projects are methodology, methodology-tools, allegro, in-real-life, in-real-life-ops, in-real-life-org, project-orchestrator, project-orchestrator-service, serverless-web-app-template and communication-pipeline. [decided: Portfolio register]

C3. The Agent bootstrap of each of the ten projects carries the amended W-008 block with its fourth part, Terms introduced. evidence: E1. [decided: the ten checkouts, 2026-10-28]

C4. The 1.6.0 migration round is closed. [decided: owner, 2026-10-28]

C5. The ten migration PRs were merged on 2026-10-28, the day the release was tagged. evidence: E2. [decided: the ten repositories]

C6. The Portfolio register's ten pinned rows now read "pinned 1.6.0". [decided: this refresh]

C7. The register's census line now records that pins were refreshed on 2026-10-28 from the observed Classifications of ten checkouts. [decided: this refresh]

C8. The methodology row now records its migration to 1.6.0 on 2026-10-28 by PR #60. [decided: this refresh]

C9. The project-orchestrator row now records the Paraphraser and Reviewer (stranger) roles, accepted on 2026-10-26 and revised with the pipeline's branch point v1.5 and v1.6. [decided: this refresh]

C10. The communication-pipeline row now records its evaluation corpus as cases 001 to 008 and its branch point at v1.6. [decided: this refresh]

C11. mc-tools has no pin and no bootstrap, so the round had no PR for it. [decided: Portfolio register]

## Relations

R1. C4 depends-on C1 because the round closes when every pinned project pins the release.

R2. C6 depends-on C1 because the rows record what was observed.

## Evidence

E1. The ten checkouts under /home/user on 2026-10-28: `docs/classification.md` reads "Pinned methodology version: 1.6.0" and `CLAUDE.md` holds "Terms introduced" in each.

E2. Merge commits on each main: methodology #60, methodology-tools #20, allegro #105, in-real-life #88, in-real-life-ops #24, in-real-life-org #16, project-orchestrator #11, project-orchestrator-service #16, serverless-web-app-template #5, communication-pipeline #17.

## Asks

A1. Review and merge this register refresh. Depends: C6, C7, C8, C9, C10.
