# Review record: the intermediate representation specification, rewritten from its IR

Reader of the reviewed text: RD-4 (a fresh agent session). Reviewer:
a stranger, a fresh haiku instance per round, reading only the files
named in its brief. Rounds until readable, limit ten (owner ruling of
2026-10-26). Text reviewed: `docs/intermediate-representation.md`,
rendered by the reasoning role from
`docs/intermediate-representation.ir.md` (148 claims, 18 terms,
24 relations). Every fix is made in the IR first and the prose is
re-rendered or edited to match.

Experiment design (owner, 2026-10-26, after the per-finding analysis
of PR #51's ten rounds): round 1 runs twice on one text. Round 1a
uses the brief of the PR #51 rounds unchanged, for comparison. Round
1b uses a revised brief: no SP-18 (a norm names its test) and no
"unclassified case" prompt; a redundancy check added; the verdict
decoupled from the finding count and given by whether the stranger's
restatement of the text's problem, terms and decisions matches the IR,
with no contradiction and no undefined term; each finding carries the
kind of fix it needs (cut, rephrase, add). Rounds 2 onward use the
revised brief.

Lint before round 1: IR CK-01 to CK-16 clean; round trip 148 of 148
claims mapped; `mtool style` 25 warnings, all P-008 first-use links
on vocabulary terms used in their plain sense (Document, Specification,
Register, Entry, Target, Provenance) except as noted per round.

Meta-review: pending

## Curve

| Round | Brief | Prose words | IR claims | Findings | Per 1,000 words | Verdict |
|---|---|---|---|---|---|---|
| 0 (PR #51 text, for comparison) | old | 4,516 | 19 (amendment) | — | — | not readable after ten rounds |
| 0 (main text, for comparison) | — | 2,635 | — | — | — | not readable (PR #50 round 2) |
| 1a | old | 2,884 | 148 | 22 | 7.6 | not readable |
| 1b | revised | 2,884 | 148 | 26 | 9.0 | not readable (contradictions 1, undefined terms 1; restatement matched in substance) |
| 2 | revised | 2,864 | 161 | | | |

## Round 1a, 2026-10-26 (old brief)

2,884 words (the stranger counted 3,036 including the render map);
22 findings; 7.2 per thousand words; verdict: not readable for RD-4.
Compared with round 1 of PR #51's text: 28 findings, 10.9 per
thousand words, on 2,572 words. By kind: SP-18 edge-case elaboration
12 (findings 4, 5, 6, 8, 10, 11, 12, 13, 14, 19, 20 and the second
half of 8); SP-03 referents 3 (1, 2, 16: "It" and "that session" with
the antecedent in the previous sentence); SP-04 terms 3 (17 "state
paragraph", 21 "register fact" used one sentence before its
definition, 22 "formal project model"); other-project history 3
(3, 15, 18); SP-01 one (9); CK-01 one (7: the bare-form list counts
five and lists six). Dispositions follow after round 1b, so one set
of fixes serves both.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1, 2 | "It" with the antecedent in the previous sentence | referent | rephrase: "The file sits", "The file opens" |
| 3 | header names the adopting project | history | cut: the header drops the adoption sentence; History holds it |
| 4 | owner decisions outside rounds have no record defined | edge | cut: C141 (where the owner's decision is recorded) removed |
| 5 | when `draft`, `rendered`, `delivered` are set | edge | declined: the default clause covers; C158 added for `reviewed` (see 20) |
| 6 | inline definition vs sentence of its own | contradiction | cut: "rendered as an inline definition" removed from C27; C77 states the rendering |
| 7 | bare-form list: five said, six listed | wording | rephrase: C42 split into pronouns (C42) and determiner phrases (C163), no count stated |
| 8 | "whatever the purpose" vs row 2 keyed on purpose; "owner asked" undefined | contradiction, edge | cut: "whatever the text's purpose" removed from C90; second half declined, the owner's request is an input |
| 9 | verdict sentence joins three tests | compound | rephrase: C93 states its three conditions as a list |
| 10 | what a redundancy finding does to the verdict | edge | rephrase: C94 "recorded and fixed like any other finding" |
| 11 | readable-round findings vs delivered report not edited | edge | rephrase: C97 split (C97, C156); a delivered report has no next edit |
| 12 | does rework reset the limit | edge | rephrase: C89 "a count ends at the limit, ten rounds"; the limit is per count |
| 13 | dispositions vs adjudication outcomes | edge | declined: the decision is the adjudication; no mapping added |
| 14 | document delivery trigger; meta-review timing; who writes the line | edge | rephrase: C106 names the reasoning role and the delivering report; C159 names who sets the line; timing declined |
| 15 | pipeline named as performer; History does not say why | history | rephrase: placement moved to History as C162; C107 keeps the duty |
| 16 | "that session" | referent | rephrase: "The performing session" |
| 17 | "state paragraph" undefined | term | cut: the state-paragraph reason removed from C116 and C130 |
| 18 | "routed IRs" undefined; other project's practice | term, history | cut: the tuning source removed from C120 |
| 19 | deliverable neither chat nor branch | edge | declined: the default clause covers |
| 20 | footprint trigger: `reviewed` only set at the limit | edge | add: C158 "the end of a count sets the Status to `reviewed`" (one rule, 11 words); C99 narrowed |
| 21 | "register fact" used before its definition | term | rephrase: the definition moved before the first use |
| 22 | "formal project model" undefined | term | cut: C137 removed |

## Round 1b, 2026-10-26 (revised brief)

2,884 words; 26 findings; 9.0 per thousand words. Restatement: 190
words, matching the IR in substance; the stranger answered "no"
because four header sentences had no backing claim. Contradictions 1
(the bare-form count), undefined terms 1 ("state paragraph"); verdict:
not readable for RD-4. By fix kind as the stranger judged: cut 6,
rephrase 8, add 12; by locus: prose 8, IR 5, both 13. Of the twelve
"add" findings, nine are claim splits where the added words are a
repeated subject; three ask for a definition or referent.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1–4 | header sentences (status, W-009, Portfolio register, assumed knowledge) without claims | IR gap | add in the IR: C149, C150, C151; cut the Portfolio-register parenthesis with the adoption sentence |
| 5–14 | ten compound sentences, each from a compound claim | compound | split in the IR: C27/C152, C77/C153, C80/C154, C96/C155, C97/C156, C98/C157, C99/C158, C108/C159, C134/C160, C135/C161 |
| 15 | review record used before its definition | term order | rephrase: the definition (T12) moves to Document form; the Purpose use is gone with C141 |
| 16 | render map used in CK-15 before its definition | term order | add: "(Rendering rule)" pointer, two words |
| 17 | register fact before its definition | term order | rephrase: definition moved first |
| 18 | readable verdict before its definition | term order | rephrase: C93 moved before C88 |
| 19 | "the limit" without antecedent | referent | rephrase: C89 names the limit |
| 20 | "state paragraph" undefined | term | cut from C116 and C130 (as 1a-17) |
| 21 | "there" | referent | rephrase: "in the review record" |
| 22, 23 | "also" twice | excess | cut |
| 24 | "with no part in the text's rounds" repeated | excess | cut from C107 |
| 25 | five vs six | contradiction | rephrase (as 1a-7) |
| 26 | R22 "contradicts ... unless" | IR form | cut R22 |

Fixes after round 1: IR 148 to 161 claims (eleven splits, four
header claims, two cuts: C137, C141); relations 24 to 26 (R22 cut,
R25 to R27 added); prose 2,884 to 2,864 words. Lint clean; round trip
161 of 161; `mtool style` 20 warnings, all first-use links on
vocabulary words in their plain sense.

Overlap of the two briefs on one text: both found the bare-form
count, the "state paragraph" term, "register fact" before its
definition, and the limit's scope. The old brief found twelve
edge-case elaborations (SP-18) of which two were accepted as rules
and ten declined or resolved by cutting. The revised brief found ten
compound sentences the old brief passed, four IR gaps behind the
header, and three excess-word findings the old brief has no rule for.
