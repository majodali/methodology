# Review record: stranger rounds run until readable

Reader of the reviewed text: RD-4 (a fresh agent session). Reviewer:
the communication pipeline's stranger reviewer (haiku, a fresh
instance per round), disposition D3, rounds until readable with a
limit of ten: the rule this amendment introduces, applied to itself.
Text reviewed: `docs/intermediate-representation.md` whole, with the
new passages marked. Because PR #50 merged with its second round not
readable, these rounds also stand in for the rounds that text did not
get.

## Round 1, 2026-10-26

2,572 words; 28 findings, 16 in the new passages; 10.9 per thousand
words; verdict: not readable for RD-4. Every finding was fixed,
pre-existing ones included, so the rounds converge on the whole text.

| # | Finding (shortened) | Disposition |
|---|---|---|
| 1 | reasoning role and paraphraser unlinked at first use | fixed |
| 2, 8, 9, 24 | another project's history or a provenance parenthetical outside History | fixed: the header drops the schema version; the three rulings move to History with their link |
| 3, 22 | semicolons | fixed |
| 4 | CK-12 unnamed | fixed |
| 5 | "a term is defined once per IR" has no check | fixed: CK-13, term uniqueness |
| 6 | inferred claims have no part | fixed: decided or inferred render under covered |
| 7 | "unit" used before defined; "P-008 defines" unclear | fixed |
| 10 | a PR body's footprint unclassified | fixed: the pull request's changes are the deliverable, carried by its branch |
| 11 | "the two" | fixed |
| 12 | "dependent asks" undefined | fixed: defined in the inputs paragraph |
| 13 | "this output" | fixed: the owner's review flag, defined in the inputs paragraph |
| 14 | the rows say until readable, the subsection says ten | fixed: the rows point at the subsection |
| 15 | who starts the stranger; may the reasoning role be the stranger | fixed: the reasoning role dispatches a fresh instance, never itself |
| 16 | "the text" | fixed: the rendered prose |
| 17 | fixes after a readable verdict | fixed: post-verdict fixes, listed as such |
| 18 | who re-renders after fixes | fixed: the paraphraser re-renders with a new map; the reasoning role fixes normative prose itself |
| 19 | the review record has no check | fixed: CK-14 |
| 20, 21 | no default at the limit; "adjudication" undefined | fixed: not delivered, Status stays reviewed, the record says so; the owner decides at the deliverable's adjudication (Article 8, linked) |
| 23 | the meta-review sentence carries three claims and names no recipient | fixed: split; reports to the owner |
| 25 | the render map under the Stranger rounds heading | fixed: the subsection now follows the render map paragraph |
| 26, 27, 28 | "that amendment", "Each", "evidencing instance" | fixed: PR #50 named; "each of the four texts"; motivating instance, Article 6 linked |
