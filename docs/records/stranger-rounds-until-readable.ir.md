# IR: Stranger rounds run until readable

Reader: RD-4 (a fresh agent session) reading the intermediate-representation specification; the human owner adjudicates the amendment.
Purpose: document. The amendment that replaces the two-round stranger review with rounds until a readable verdict, limited to ten, for every stranger review the rendering conditions select, and adds the meta-review trigger for texts that need more than two rounds.
Status: draft (round 1 of the stranger rounds at stranger-rounds-until-readable.review.md: 28 findings, 16 new, not readable; all fixed)
Source: the owner's message of 2026-10-26 after merging PR #50 ("I should have requested the third stranger round"; "unlimited stranger reviews until all clean (or perhaps a sanity limit of ten) on any doc requiring a stranger review"; "more than two reviews should then have those reviews and the doc itself meta-reviewed by this project").
Normative: yes
Footprint: docs/intermediate-representation.md; docs/records/; docs/releases.md; docs/backlog.md

## Terms

T1. Meta-review: a review, by the communication-pipeline project, of a text's review record and the text itself, reporting whether the process needs a change. [proposed: this IR]

## Claims

### The rule

C1. A stranger review runs in rounds until a round returns the verdict readable. [decided: owner, 2026-10-26]

C2. The review stops after ten rounds without a readable verdict, and the review record says so. [decided: owner, 2026-10-26]

C3. The rule applies to every stranger review the rendering conditions select, not only to normative text. [decided: owner, 2026-10-26]

C4. A text that needs more than two rounds is a subject for meta-review by the communication-pipeline project. [decided: owner, 2026-10-26]

C5. Each round is run by the reasoning role with a fresh stranger on the fixed IR and the fixed text. [decided: methodology PR #50, 2026-10-26]

C11. Each round's findings, dispositions and verdict are recorded in the review record beside the IR. [decided: methodology PR #50, 2026-10-26]

C6. At the limit the text is not delivered, the IR's Status stays reviewed, and the review record states that the limit was reached. [proposed: this IR]

C12. The owner decides when adjudicating the deliverable whether a text at the limit is delivered, reworked or withdrawn. [proposed: this IR]

C13. The stranger of a round is an agent instance with a fresh context, never the reasoning role and never an earlier round's instance. [proposed: this IR]

C14. After a not-readable verdict, prose the paraphraser rendered is rendered again from the fixed IR with a new render map. [proposed: this IR]

C18. After a not-readable verdict, prose the reasoning role rendered is fixed by the reasoning role. [proposed: this IR]

C15. The fixes of a readable round are applied before delivery and listed in the review record as post-verdict fixes. [proposed: this IR]

C16. CK-13 checks that two T elements do not name the same term. [proposed: this IR]

C19. CK-14 checks that a reviewed IR has its review record with a verdict per round. [proposed: this IR]

C17. The meta-review reports to the owner. [proposed: this IR]

### Why

C7. The second round on PR #50's own text returned not readable, and no third round ran before the merge. evidence: E1. [decided: review record, 2026-10-26]

C8. The owner's ruling replaces the one-decision-per-amendment form of the two-round rule with a stopping rule the reasoning role applies without an ask. [inferred: R1]

C9. The amendment's own review supplies the rounds PR #50 did not get, because the review covers the whole specification. [proposed: this IR]

C10. The amendment is normative content for the methodology-corpus type and mints no duty elsewhere. [proposed: this IR]

## Relations

R1. C8 depends-on C7 because the owner's ruling answers the case where an ask at adjudication was missed.

## Evidence

E1. docs/records/normative-second-round.review.md, Round 2, verdict not readable; PR #50 merged 2026-10-26 without a third round.

E2. The owner's message of 2026-10-26.

## Asks

A1. Adjudicate the amendment: accept, amend, or reject. Depends: C1, C2, C3, C4.

A2. Ratify or strike the term meta-review (T1).
