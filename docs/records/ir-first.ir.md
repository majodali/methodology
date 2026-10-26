# IR: The methodology corpus writes its deliverables IR first

Reader: RD-4 (a fresh agent session) reading W-009 and the intermediate-representation specification; the human owner adjudicates the amendment.
Purpose: document. The amendment that adds W-009, scoped to the methodology-corpus type, and the specification of the intermediate representation it requires, graduated from the communication pipeline's schema v1.2.
Status: reviewed (one stranger review at ir-first.review.md, disposition D3; 49 findings, 43 fixed; verdict before fixes: not readable for RD-4; the specification was rewritten in the methodology's own terms after the review)
Source: the pilot plan's settled decision 2 (2026-10-24) and its exit condition, settled decision 6; the pipeline's ir-schema.md v1.2 and branch-point.md v1.1; the owner's rulings of 2026-10-25 on when an IR is required; the methodology Backlog item "This repository's deliverables go through the communication pipeline".
Normative: yes

## Terms

T1. Intermediate representation (IR): the structured form a reasoning role writes before prose, holding the terms, claims, relations, evidence and asks of one communication, each with an identifier and a provenance status. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-intermediate-representation [decided: owner, 2026-10-24]

T2. Reasoning role: the agent role that does the thinking and writes its output as an IR. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-reasoning-role [decided: owner, 2026-10-24]

T3. Paraphraser: the agent role that renders an IR into prose for a defined reader and adds no claim. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-paraphraser [decided: owner, 2026-10-24]

T4. Stranger: a reviewer with no access to the conversation that produced the text and no content contributions to the project. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-stranger [decided: owner, 2026-10-23]

T5. Provenance status: the tag ending each term, claim and cluster of an IR: decided, proposed or inferred. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/ir-schema.md [decided: owner, 2026-10-25]

T6. Cluster: a declared ordered list of claim identifiers the paraphraser renders as one paragraph. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-cluster [decided: owner, 2026-10-25]

## Claims

### W-009

C1. In a project of type methodology-corpus, a document under docs/, and a report that introduces a term, records a decision, or states a register fact, is written as an IR first. [decided: owner, 2026-10-25]

C23. Prose for RD-4 or RD-5 is rendered from the IR and reviewed by a stranger. [decided: pipeline branch point v1.1, 2026-10-25]

C24. A register fact is a statement about the state of a Register or of a row in one. [proposed: this IR]

C25. The specification gains CK-12, identifier uniqueness, after the stranger review. [proposed: this IR]

C2. The IR sits beside the prose it produces, or under docs/records/ when the prose is a chat message or a PR body. [decided: owner, 2026-10-24]

C3. Prose for a human-owner reader or a delegating agent is rendered from the IR by a paraphraser when the IR exceeds the thresholds of the specification. [decided: owner, 2026-10-24]

C19. Below the thresholds, the IR is delivered as it stands. [decided: owner, 2026-10-24]

C4. Normative text is rendered by its author and reviewed by a stranger. [decided: owner, 2026-10-25]

C5. A report to the human owner or a delegating agent that introduces no term, records no decision and states no register fact may be written as prose directly. [decided: owner, 2026-10-25]

C6. A project of another type may adopt W-009 by declaring it in its Classification. [proposed: this IR]

C7. W-009 applies to the methodology-corpus type only, because the practice has been exercised in two repositories and the evidence for other types does not exist yet. [proposed: this IR]

### The specification

C8. The specification docs/intermediate-representation.md is the pipeline's schema v1.2 with pipeline-local references replaced by methodology ones. [proposed: this IR]

C9. The specification keeps the document form, the six element kinds, the referent rule, the three provenance statuses, the eleven checks CK-01 to CK-11, the rendering rule and the lifecycle rule. [decided: pipeline schema v1.2, 2026-10-25]

C10. The specification carries the rendering thresholds of the pipeline's branch point. [proposed: this IR]

C20. A report to the human owner in conversation is rendered when it has more than six claims, a dependent ask, or a claim over 30 words. [decided: pipeline branch point v1.1, 2026-10-25]

C21. A report to a delegating agent is rendered when it has more than twelve claims or a dependent ask. [decided: pipeline branch point v1.1, 2026-10-25]

C22. A report to the returning owner is always rendered, because only the paraphraser writes its state paragraph. [decided: pipeline branch point v1.1, 2026-10-25]

C11. The branch point's dispositions and its dispatcher stay in the pipeline until the roles move to project-orchestrator. [proposed: this IR]

C12. The checks CK-01 to CK-11 are implemented by methodology-tools as `mtool ir check`. [proposed: this IR]

### Why

C13. The methodology repository is the pipeline's first subject. [decided: owner, 2026-10-24]

C14. Three methodology amendments and one register refresh were written IR first in October 2026. [decided: this repository, PRs #44, #46 and the two stacked below this one]

C15. The reviewer's finding count per thousand words fell from 82.0 to 25.2 over three rounds on the register refresh. [decided: pipeline case 003, 2026-10-25]

C16. W-009 protects provenance, because every claim carries its status, and proportional verification, because the thresholds decide what runs. [decided: owner, 2026-10-24]

C17. The repository archives when the schema and specifications are adopted upstream, the lints have moved to methodology-tools, and the roles have moved to project-orchestrator. [decided: owner, 2026-10-24]

C18. Acceptance of this amendment satisfies the first of the three exit conditions. [inferred: R1]

## Relations

R1. C18 depends-on C17 because the first condition names adoption of the schema upstream, and this amendment is that adoption.

R2. C7 supports C6 because a type-scoped rule needs a way in for other projects.

## Evidence

E1. communication-pipeline docs/ir-schema.md v1.2 and docs/branch-point.md v1.1 on branch chunk-3-measurement.

E2. communication-pipeline docs/plans/pipeline-pilot.md, settled decisions 2 and 6.

E3. communication-pipeline eval/cases/003-live-run-portfolio-refresh-2026-10-25.md: 82.0, 35.2, 25.2 findings per thousand words.

E4. docs/backlog.md, "This repository's deliverables go through the communication pipeline", from 2026-10-24.

## Asks

A1. Adjudicate the amendment: accept, amend, or reject. Depends: C1, C8.

A2. Confirm the type scope of W-009, methodology-corpus only, with adoption by declaration for other projects. Depends: C6, C7.

A3. Record whether acceptance satisfies the first exit condition of the pilot. Depends: C18.
