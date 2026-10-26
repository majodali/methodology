# IR: Stranger rounds run until readable

Reader: RD-4 (a fresh agent session) reading the intermediate-representation specification; the human owner adjudicates the amendment.
Purpose: document. The amendment that replaces the two-round stranger review with rounds until a readable verdict, limited to ten, for every stranger review the rendering conditions select, and adds the meta-review trigger for texts that need more than two rounds.
Status: draft
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

C5. Each round is run by the reasoning role, with a fresh stranger, on the fixed IR and the fixed text, and recorded in the review record beside the IR. [decided: methodology PR #50, 2026-10-26]

C6. The owner decides at adjudication what happens to a text that reaches the limit. [proposed: this IR]

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
