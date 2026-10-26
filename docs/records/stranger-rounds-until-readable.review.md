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

## Round 2, 2026-10-26

3,004 words; 25 findings, 15 in the new passages; 8.3 per thousand
words; verdict: not readable for RD-4. Every finding was fixed. A
third round follows, which makes this text a meta-review subject.

| # | Finding (shortened) | Disposition |
|---|---|---|
| 1 | only chat messages get an empty footprint | fixed: absent or empty when no branch carries the deliverable |
| 2, 3, 5, 9 | two claims in a cell; long sentences | fixed: split |
| 4 | "ratification ask" undefined | fixed: the ask is spelled out |
| 6 | fixes after a readable verdict change the judged text | fixed: the delivered text is the judged text; a readable round's findings are fixed at the next edit |
| 7, 8 | the IR fix duty missing for normative text; "re-rendered prose" names nothing there | fixed: fixes to the IR in every case; the prose as it then stands |
| 10 | Article 8 as the basis for adjudicating a deliverable | fixed: the owner's acceptance or rejection; Article 8 for an amendment |
| 11, 12, 13 | meta-review used before defined; no test; no trigger owner or time | fixed: defined first; three or more rounds in the record; the reasoning role records and asks; the pipeline performs it at its next gate |
| 14 | CK-14 cannot tell when a review was owed | fixed: the conditions that select rounds are listed in the check; Status values defined |
| 15 | "same term" has no test | fixed: equal names after lower-casing |
| 16 | provenance in the header | fixed: moved to History |
| 17, 18, 19 | tuning by another project's record; "routed IRs"; an editorial count change | fixed: a count changes by amendment; the data source named in History |
| 20 | no one appends the render map for normative text | fixed: whoever rendered the prose |
| 21 | Term row versus Rendering rule on introduced terms | fixed: a defining sentence of its own, in both |
| 22 | "state paragraph" | fixed: described, with the catalog cited |
| 23 | renames | fixed: changed under both paths |
| 24 | docs/records/ reports read as documents | fixed: outside docs/records/ |
| 25 | nothing sets Status to reviewed | fixed: the Status row says who sets each value and when |

Meta-review subject: yes, from round 3 (recorded here per the rule).
