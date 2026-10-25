# IR: W-008 gains a fourth report part, terms introduced

Reader: RD-4 (a fresh agent session) reading the amended rule; the human owner adjudicates the amendment.
Purpose: document. The amendment to W-008 (reports map their deliverables) that adds the part terms introduced, its bootstrap block, its style guide section, and its release-register entry.
Status: reviewed (one stranger review of the rendered rule text at w008-terms-introduced.review.md, disposition D3; 36 findings, 10 fixed, the rest pre-existing wording left to the editorial pass or accepted by design; verdict not readable for RD-4 before the fixes)
Source: the owner's ruling at the pilot's chunk 2 gate, 2026-10-24; the pilot's term lifecycle, approved 2026-10-25; the owner's "Convergence and Divergence", 2026-10-22; the pilot's case 001.
Normative: yes

## Terms

T1. Terms introduced: the part of a report that lists each term the report or its deliverable uses with a meaning that neither the methodology vocabulary nor the project's own vocabulary defines. [proposed: this IR]

## Claims

### The rule

C1. A report addressed to the human owner carries four parts in this order: asks; what is already covered; what changed; terms introduced. [decided: owner, 2026-10-24]

C2. Each term under terms introduced is listed with one sentence giving its meaning. evidence: E1. [decided: owner, 2026-10-25]

C3. A term is introduced when the report or its deliverable uses it with a meaning that neither the methodology vocabulary nor the project's own vocabulary defines. [proposed: this IR]

C4. An empty terms-introduced part is stated as "No terms introduced". [inferred: R1]

C20. Each empty-part statement is tied to its part, in the part's own words. [proposed: this IR]

C5. The asks part requests the ratification or striking of each introduced term. evidence: E1. [decided: owner, 2026-10-25]

C6. On ratification the agent adds a row for the term to the project's vocabulary. evidence: E1. [decided: owner, 2026-10-25]

C19. A struck term is removed from the deliverable. evidence: E1. [decided: owner, 2026-10-25]

C7. A report addressed to a delegating agent lists its terms introduced when it has any. [proposed: this IR]

C8. A report addressed to a delegating agent keeps its existing duties: it states its status, maps its deliverable, carries the asks, and may omit what is already covered and what changed. [decided: owner, 2026-09-01]

### The mirrors of the rule

C9. The required bootstrap block gains the fourth part and the fourth empty statement. [inferred: R2]

C10. Every project with an Agent bootstrap replaces its copy of the block with the amended block, in one copy action per project. [inferred: R3]

C11. The style guide's section Reports and summaries gains the fourth part. [inferred: R4]

C12. The amendment is normative content, so the release that carries it is a minor release. [decided: release process, docs/releases.md]

### Why

C13. Unratified vocabulary is one of the three indicators of divergence in the owner's "Convergence and Divergence". evidence: E3. [decided: owner, 2026-10-22]

C14. A term coined in a session and never surfaced enters documents with no definition the owner ratified. evidence: E3. [decided: owner, 2026-10-22]

C15. The pilot's case 001 found the term "fold" in a report to the owner, with no source in the conversation or in any vocabulary. evidence: E2. [decided: owner, 2026-10-23]

C16. The report is the cheapest moment for the owner to rule on a coinage, because the report is already the owner's index into the deliverable. [proposed: this IR]

C17. Listing introduced terms in a report costs one line when the list is empty. [proposed: this IR]

C18. A delegating agent that receives introduced terms from a delegate carries them into its own report, instead of adopting them untracked. [inferred: R5]

## Relations

R1. C4 depends-on C1 because W-008 states every empty part and never omits it.

R2. C9 depends-on C1 because W-008 declares the bootstrap block a cache of its own Statement.

R3. C10 depends-on C9 because W-008 reports any difference between a bootstrap's copy and the block as drift.

R4. C11 depends-on C1 because W-008 names the style guide section as the authority the block caches.

R5. C18 depends-on C7 because a delegating agent can only carry what its delegate's report lists.

## Evidence

E1. communication-pipeline, docs/term-lifecycle.md, the table "The rule in one table" and the section Ratification, steps 1 to 6; approved by the owner 2026-10-25.

E2. communication-pipeline, eval/cases/001-review-response-2026-10-23.md, the finding on "fold".

E3. The owner's "Convergence and Divergence", 2026-10-22, the three indicators: prediction surprise, unratified vocabulary, explanation cost.

E4. docs/rules/working-agreement.md, W-008, Statement and Required bootstrap text; docs/style.md, Reports and summaries; both at v1.5.0.

## Asks

A1. Adjudicate the amendment: accept, amend, or reject.

A2. Ratify or strike the part name terms introduced (T1).

A3. Rule on C7: whether a report to a delegating agent lists its terms introduced when it has any.
