# Portfolio register

The enumeration of all majodali projects
([Constitution Article 9](../constitution.md#article-9--audits);
[M-001](../rules/mirrors.md#m-001--the-portfolio-register-is-complete)).
Classification summaries are an **informative cache** — each project's
own Classification remains authoritative. `implicit C0` marks projects
with no Classification document
([Article 4](../constitution.md#article-4--applicability-then-precedence):
C0 by definition, all omission defaults; compliance target = latest
version).

**Census**: 2026-08-18, manual account enumeration (transitional — Risk
[R3](../open-risks.md)). Confirmed by the owner at the chunk-1 gate,
2026-08-18.

| Project | Location | Classification summary | Notes |
|---|---|---|---|
| methodology | github.com/majodali/methodology | C1 / S0 / methodology-corpus / none-local — pinned 1.4.0 | this repo; [Classification](../classification.md) |
| methodology-tools | github.com/majodali/methodology-tools | C1 / S0 / component/library / package registry — pinned 1.4.0 | [Classification](https://github.com/majodali/methodology-tools/blob/main/docs/classification.md); `methodology` family member (declared 2026-08-25); founding plan `methodology-tools-v1` closed — all five chunks delivered |
| allegro | github.com/majodali/allegro | C2 / S0 / language-tool platform / static site — pinned 1.4.0 | Classification declared 2026-08 (Workflow reworded to the v1.4.0 canonical form); migration landed 2026-09-01 (allegro PR #43); summary refreshed from the observed declaration |
| in-real-life | github.com/majodali/in-real-life | C2 / S2 / web-app / serverless-aws — pinned 1.4.0 | Classification declared 2026-08 (Workflow declared; audit-log register adopted); `in-real-life` family lead (declared 2026-08-25); summary refreshed 2026-08-25 |
| in-real-life-ops | github.com/majodali/in-real-life-ops (private) | C2 / S1 / ops / serverless-aws — pinned 1.4.0 | ops repo for in-real-life; `in-real-life` family member (declared 2026-08-25); Classification declared 2026-08-20 (Workflow declared); audits clean at declared level |
| in-real-life-org | github.com/majodali/in-real-life-org (private) | C2 / S2 / docs-corpus / none-local — pinned 1.4.0 | `in-real-life` family member (declared 2026-08-25); Classification declared 2026-08-20; audits clean at declared level |
| project-orchestrator | github.com/majodali/project-orchestrator | C1 / S0 / component-library / none-local — pinned 1.4.0 | process spec + plugin coordinating role-based agent sessions on portfolio projects; `methodology` family member (declared 2026-08-25); owner intends C2 Promotion before it orchestrates C2+ projects |
| project-orchestrator-service | github.com/majodali/project-orchestrator-service | C1 / S1 / backend-service / serverless-aws — pinned 1.4.0 | MCP service exposing the orchestrator's plan state to sessions; `methodology` family member (declared at its 2026-08-27 bootstrap); registered on owner instruction 2026-08-30 (M-001); coordinating-repo relationship stated in prose in its Classification pending a multi-repo amendment |
| serverless-web-app-template | github.com/majodali/serverless-web-app-template | C1 / S0 / template / none-local — pinned 1.4.0 | reference implementation for the serverless-aws target; first `template`-type project (Q-001 in play, declared derivative tier C1); `methodology` family member (declared 2026-08-25) |
| mc-tools | github.com/majodali/mc-tools | implicit C0 | |
| graph-analysis | github.com/majodali/graph-analysis | implicit C0 | |
| open-context | github.com/majodali/open-context | implicit C0 | |
| open-context-v1 | github.com/majodali/open-context-v1 | implicit C0 | archived |
| workbench | github.com/majodali/workbench | implicit C0 | |
| chat | github.com/majodali/chat | implicit C0 | |
| antimatter | github.com/majodali/antimatter | implicit C0 | |
| modcraft | github.com/majodali/modcraft | implicit C0 | |
| tautology | github.com/majodali/tautology | implicit C0 | |
| simple-modeling | github.com/majodali/simple-modeling | implicit C0 | |
| parser-generator | github.com/majodali/parser-generator | implicit C0 | |
| software-project-api | github.com/majodali/software-project-api | implicit C0 | last pushed 2024 |
| chloe-portfolio | github.com/majodali/chloe-portfolio (private) | implicit C0 | one-page portfolio site; registered at review round 1 spot-check, 2026-08-30 (M-001 — previously unobserved, the census enumeration gap) |

Census discrepancy, resolved at the chunk-1 gate: the
`home-infrastructure`, `comms-hub`, and `minecraft-mcp` examples in
[practices §1.1](../practices.md) do not correspond to observable
repositories; the owner ruled to disregard them. The register records
observed repositories only.

## Families

Grouping per the *Project family* definition (vocabulary). Family
declarations live in member Classifications; this section caches them
and the census reconciles for symmetry.

- **methodology** — lead: methodology (declared in its
  [Classification](../classification.md)); members: methodology-tools,
  project-orchestrator, project-orchestrator-service,
  serverless-web-app-template — composition ratified by the owner
  2026-08-24; declarations landed 2026-08-25, the service's at its
  2026-08-27 bootstrap. Future template and process projects join
  this family by default (owner ruling, 2026-08-24).
- **in-real-life** — lead: in-real-life; members: in-real-life-ops,
  in-real-life-org — lead and member declarations landed in their own
  Classifications 2026-08-25.
