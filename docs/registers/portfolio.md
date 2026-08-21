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
| methodology | github.com/majodali/methodology | C1 / S0 / methodology-corpus / none-local — pinned 1.1.0 | this repo; [Classification](../classification.md) |
| methodology-tools | github.com/majodali/methodology-tools | C1 / S0 / component/library / package registry — pinned 1.1.0 | [Classification](https://github.com/majodali/methodology-tools/blob/main/docs/classification.md); founding plan `methodology-tools-v1` status active (chunk 1 delivered) |
| allegro | github.com/majodali/allegro | implicit C0 | census spot-check: actual state ~C2 per [practices §5](../practices.md) — Classification needed (Article 4 declaration accuracy) |
| in-real-life | github.com/majodali/in-real-life | implicit C0 | spot-check: actual state ~C2/S2 per [practices §5](../practices.md) — Classification needed |
| in-real-life-ops | github.com/majodali/in-real-life-ops (private) | implicit C0 | ops repo for in-real-life |
| in-real-life-org | github.com/majodali/in-real-life-org (private) | implicit C0 | |
| serverless-web-app-template | github.com/majodali/serverless-web-app-template | implicit C0 | reference implementation for the serverless-aws target |
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

Census discrepancy, resolved at the chunk-1 gate: the
`home-infrastructure`, `comms-hub`, and `minecraft-mcp` examples in
[practices §1.1](../practices.md) do not correspond to observable
repositories; the owner ruled to disregard them. The register records
observed repositories only.
