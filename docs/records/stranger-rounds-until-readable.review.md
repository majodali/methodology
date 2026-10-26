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

## Round 3, 2026-10-26

3,196 words; 27 findings, 21 in the new passages; 8.4 per thousand
words; verdict: not readable for RD-4. Every finding was fixed. This
text is a meta-review subject from this round.

| # | Finding (shortened) | Disposition |
|---|---|---|
| 1, 6 | Status values incomplete; the review flag has no field | fixed: every Status transition named; `review requested` recorded in the Status parenthesis |
| 2 | "the counts the sections below record" | fixed: the two sections named |
| 3, 24 | the Footprint fragment; a declared footprint on a chat-message IR | fixed: a sentence; ignored |
| 4 | every term must be a T element versus CK-04 | fixed: or linked inside the claim |
| 5 | CK-13 tests spelling only | fixed: stated as the mechanical part; synonyms are a stranger finding |
| 7, 8 | the round-trip check has no identifier or thresholds; three findings in one sentence | fixed: CK-15, split, the ratio as information |
| 9, 12, 15, 21 | two claims in one sentence or cell | fixed: split |
| 10 | no actor for fixes after a readable round | fixed: the reasoning role at the next edit; recorded as accepted until then |
| 11 | rework and the count | fixed: rework restarts the count |
| 13, 14 | meta-review trigger time; "gate" | fixed: before the pipeline's next report to the owner; the methodology's session when the pipeline is archived |
| 16 | a raw IR lacks W-008's parts | fixed: the IR's sections stand for the parts, stated in the row |
| 17 | "provisional" | fixed: removed |
| 18 | a rename counted twice | fixed: one changed file, declared when either path is |
| 19, 20, 26 | referents | fixed |
| 22 | inferred claims under covered contradict W-008 | fixed: inferred renders under what changed, in both places |
| 23 | only Asks has an empty-part wording | fixed: every part, in W-008's words |
| 25 | the footprint compared once, recorded later | fixed: compared at reviewed and at delivery; delivery counts recorded |
| 27 | "formal project model" | fixed: the Backlog's horizon named |

## Round 4, 2026-10-26

3,429 words; 21 findings, 20 in the new passages; 6.1 per thousand
words; verdict: not readable for RD-4. Every finding was fixed.

| # | Finding (shortened) | Disposition |
|---|---|---|
| 1, 2, 4, 6, 8, 10 | long sentences or two claims in a cell | fixed: split |
| 3 | "review flag" and "review requested" name one concept | fixed: `review flag` everywhere, recorded in the Status parenthesis |
| 5 | no comparison when the branch is merged or deleted before delivery | fixed: the last comparison made |
| 7 | "human-owner reader" undefined | fixed: RD-1 or RD-2 |
| 9 | the Term row's "inside the claim" versus CK-04 | fixed: removed |
| 11 | CK-14 fires during rounds because `rendered` precedes them | fixed: `reviewed` or `delivered` only |
| 12 | the ratio is information in a findings table | fixed: the intro and the row say so |
| 13 | the render map notation undefined | fixed: the notation read out |
| 14, 17, 18, 20 | referents | fixed |
| 15 | who accepts findings of a readable round; later edits | fixed: the reasoning role records; the next edit fixes and may start rounds |
| 16 | "not delivered" versus the owner's decision | fixed: the reasoning role does not deliver; the owner decides |
| 19 | the meta-review duty unbounded | fixed: a session of the pipeline, on the record and the text, delivered as that session's report |
| 21 | no test for a new claim in prose | fixed: the stranger's claim-evidence finding named |

## Round 5, 2026-10-26

3,529 words; 21 findings, 19 in the new passages; 5.95 per thousand
words; verdict: not readable for RD-4. Every finding was fixed.

| # | Finding (shortened) | Disposition |
|---|---|---|
| 1, 13, 17 | referents and an ask's wording | fixed |
| 2 | a semicolon in the CK-13 cell | fixed: split |
| 3 | the Claim row's default ignores `part:` | fixed: the field decides |
| 4 | render map used before defined | fixed: pointer to the Rendering rule |
| 5 | "claim-evidence finding" undefined | fixed: the stranger reports a sentence no claim holds |
| 6 | where the render map lives | fixed: in the prose file; omitted from a sent copy |
| 7 | the heading does not predict the meta-review | fixed: a Meta-review subsection |
| 8 | where the verdict is recorded | fixed: the review record and the Status parenthesis |
| 9 | accepted findings: no actor, no test | fixed: the reasoning role; an unfixed one is a defect in the edit |
| 10 | Status at the limit | fixed: set to reviewed at any end of the rounds; the Status row says so |
| 11 | "amendment" unscoped | fixed: a change to the methodology corpus |
| 12, 14 | the meta-review's time, performer and test | fixed: due before acceptance; a session with no part in the rounds; the `Meta-review:` line and the audit |
| 15 | CK-15 on an IR with no prose | fixed: runs only when prose was rendered |
| 16 | a report for RD-4 or RD-5 | fixed: CK-07 flags the disagreement |
| 18 | empty parts of an IR delivered as it stands | fixed: one line at the IR's end in W-008's words |
| 19, 20 | footprint with no branch diff | fixed: recorded as not comparable |
| 21 | which artifact is authoritative | fixed: the IR, for an active document |

## Round 6, 2026-10-26

About 3,600 words (the reviewer counted 4,900 with markup); 23
findings, 21 in the new passages; 4.7 per thousand words by the
reviewer's count; verdict: not readable for RD-4. Every finding was
fixed.

| # | Finding (shortened) | Disposition |
|---|---|---|
| 1 | the Status parenthesis does not admit a verdict | fixed: the Status row lists the last verdict |
| 2, 9, 19, 23 | "It", "it" and "That edit" referents | fixed |
| 3, 4 | base-branch deliverables; when counts are recorded | fixed: no branch carries a base-branch deliverable; the comparison at reviewed records nothing |
| 5 | "one concept under two names" has no test | fixed: left to the stranger, stated as such |
| 6 | a decided claim whose text is new has no part | fixed: `part: changed` |
| 7 | the docs/ sentence versus CK-07 | fixed: the sentence removed; IR locations stated by purpose |
| 8 | the round trip covers claims only | fixed: claims, terms and asks; CK-15 says so |
| 10, 11, 22 | "prose file" undefined; where it sits; two copies in one sentence | fixed: defined in Document form; split |
| 12 | connective prose would trip the new-claim test | fixed: asserts something no claim holds |
| 13, 14 | accepted findings with no edit; which edit starts rounds | fixed: no deadline of their own; any edit |
| 15, 16, 17, 18 | rework and the meta-review line; the document case; who starts the meta-review; the two periods in one sentence | fixed: one line reset per count; the delivering report; the reasoning role asks the owner to dispatch; split, with the archive as the event |
| 20 | no actor for the ratification asks; no check | fixed: the reasoning role adds them; CK-08 checks them |
| 21 | a semicolon joining clauses in a cell | fixed: split |

## Round 7, 2026-10-26

3,903 words; 22 findings, 20 in the new passages; 5.6 per thousand
words; verdict: not readable for RD-4. Every finding was fixed. Two
findings (6 and 17) were contradictions introduced by earlier fixes.

| # | Finding (shortened) | Disposition |
|---|---|---|
| 1, 9, 10, 19 | referents | fixed |
| 2, 15 | `part: changed` for new decided text has no test and conflicts with the raw-IR row | fixed: when no governed document held the decision before; the row says "unless `part: changed`" |
| 3, 4, 21 | several claims or a semicolon in one sentence | fixed: split; the proposer named |
| 5 | CK-08's scope for the per-term ask | fixed: for any reader |
| 6 | the render map lists claims only, CK-15 expects terms and asks | fixed: the map lists claims, terms and asks |
| 7 | fixing accepted findings could loop | fixed: such an edit starts no rounds |
| 8 | who delivers after the owner's decision at the limit | fixed: the reasoning role, setting delivered |
| 11 | "all its rounds" | fixed: the rounds of every count |
| 12, 13, 14 | the project named before defined; History records no arrangement; "the next audit" | fixed: linked and defined at first use; History says why; the form audit under Article 9 |
| 16, 17 | the footprint row versus the section; "records nothing" contradicts the merged-branch rule | fixed: one timing rule; base-branch deliverables ignored in the section too |
| 18 | a document delivered by a PR body unclassified | fixed: active from its merge |
| 20 | "owner's flag" | fixed: review flag |
| 22 | no test for an added claim without rounds | fixed: stated as having no test beyond the reader |
