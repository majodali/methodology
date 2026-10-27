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

## Curve

| Round | Brief | Prose words | IR claims | Findings | Per 1,000 words | Verdict |
|---|---|---|---|---|---|---|
| 0 (PR #51 text, for comparison) | old | 4,516 | 19 (amendment) | — | — | not readable after ten rounds |
| 0 (main text, for comparison) | — | 2,635 | — | — | — | not readable (PR #50 round 2) |
| 1a | old | 2,884 | 148 | 22 | 7.6 | not readable |
| 1b | revised | 2,884 | 148 | 26 | 9.0 | not readable (contradictions 1, undefined terms 1; restatement matched in substance) |
| 2 | revised | 2,864 | 161 | 13 | 4.5 | not readable (contradictions 1, undefined terms 0; restatement matched in substance) |
| 3 | revised | 2,842 | 162 | 17 | 6.0 | not readable (contradictions 1 on the IR side, undefined terms 1; four restatement mismatches the stranger attributed to its own restatement) |
| 4 | revised | 2,829 | 165 | 8 | 2.8 | not readable (contradictions 3, undefined terms 2; six restatement mismatches the stranger attributed to its own compressions) |
| 5 | revised | 2,824 | 168 | 7 | 2.5 | not readable (contradictions 0, undefined terms 1; two restatement mismatches, the stranger's overstatement of C104) |
| 6 | revised | 2,830 | 170 | 12 | 4.2 | not readable (contradictions 2, undefined terms 1; restatement mismatches on C44, C45, C104 the stranger called its own, and on T19 held as a term only) |
| 7 | revised | 2,839 | 173 | 7 | 2.5 | not readable (contradictions 2, undefined terms 0; one restatement mismatch the stranger called its own) |
| 8 | revised | 2,823 | 173 | | | |

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

## Round 2, 2026-10-26 (revised brief)

2,864 words; 13 findings; 4.5 per thousand words. Restatement: 196
words, matching the IR in substance; "no" because one Reader-line
sentence had no backing claim. Contradictions 1 (the next-edit rule
against the frozen IR of a delivered report), undefined terms 0;
verdict: not readable for RD-4. By fix kind as the stranger judged:
cut 5, rephrase 2, add 6; by locus: prose 4, IR 3, both 6. The
stranger noted that it read both files in one batch, so its
restatement was not independent of the IR; the round 3 brief orders
the reads.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | "without one" | referent | add: "a definition site", two words |
| 2 | "Such a term" | referent | rephrase: the IR's wording, "A term the IR introduces" |
| 3 | "the declaration" | referent | rephrase in C123: "the Footprint header" |
| 4 | "a lint for it" | referent | cut "for it" in C123 |
| 5 | C76 compound | compound | split: C76, C164 |
| 6 | C45 rule plus three reasons | compound | split: C45, C165, same words |
| 7, 8 | Purpose repeats Element kinds (C2 = C20) and Provenance (C3 = C44) | excess | cut C2, C3 |
| 9 | Claim row repeats the referent rule (C28 = C40) | excess | cut the clause from C28 |
| 10 | "and returns findings and a verdict" repeats the round definition | excess | cut from C92 |
| 11 | next edit vs delivered report frozen | contradiction | rephrase C156: "of an active document"; R28 added |
| 12 | Reader line roles unlinked | link | links added, no word change |
| 13 | "The human owner reads the specification as RD-4 does" without a claim | IR gap | add C166 in the IR |

Fixes after round 2: IR 161 to 162 claims (two splits, two cuts, one
header claim); prose 2,864 to 2,842 words. Lint clean; round trip
162 of 162.

Meta-review: pending (the third round starts; the rule C104 makes
this text a meta-review subject).

## Round 3, 2026-10-27 (revised brief, reads ordered)

2,842 words; 17 findings; 6.0 per thousand words. Restatement: 199
words, written before the IR was opened; four claims misstated (C44,
C45, C104, C106), which the stranger attributed to its restatement,
not to the text. Contradictions 1 (the IR's nine terms defined by
this specification carried status decided without a definition site,
against C27), undefined terms 1 ("human-owner reader"); verdict: not
readable for RD-4. By fix kind as the stranger judged: cut 6,
rephrase 5, add 6; by locus: prose 2, IR 8, both 7. Eight findings
are on the IR alone: three compound claims under the CK-03 length
threshold, the header form (C11, C13), a free-standing evidence
element, the term statuses, and the ask that omitted seven proposed
claims.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1, 2 | "The file" | referent | rephrase: "The IR" |
| 3 | C9 compound | compound | split: C9, C167 |
| 4 | "the term" | referent | rephrase C164: "a term with a definition site" |
| 5 | C165 three reasons, two repeating the table | excess | cut: one reason stays |
| 6 | C96 repeats C88 | excess | cut C96 |
| 7 | "names its referent and" | excess | cut from C43 |
| 8 | "its readable round" | referent | rephrase C156 |
| 9 | "human-owner reader" undefined | term | cut: "RD-1 or RD-2" in C30, C79 |
| 10–12 | C71, C86, C114 compound | compound (IR) | split: C168, C169, C170 |
| 13 | E3 free-standing | IR form | cut E3 |
| 14 | nine terms decided without a definition site | contradiction (IR) | rephrase: T8 to T13 and T16 to T18 become proposed; the methodology vocabulary holds none of them; unratified terms 11 |
| 15 | Status parenthesis holds narrative | IR form | cut: counts only; the narrative lives here |
| 16 | Reader header holds more than one identifier | IR form | cut: `Reader: RD-4`; C151 and C166 hold the rest |
| 17 | A2 omits seven proposed claims | IR | add: A3 lists every proposed claim |

Fixes after round 3: IR 162 to 165 claims (four splits, one cut);
terms proposed 2 to 11; prose 2,842 to 2,829 words. Lint clean (the
pipeline lint counts 8 unratified terms because its own vocabulary
holds three of the nine); round trip 165 of 165.

## Round 4, 2026-10-27 (revised brief, reads ordered)

2,829 words; 8 findings; 2.8 per thousand words. Restatement: 196
words; six claims compressed, which the stranger attributed to its
restatement. Contradictions 3, undefined terms 2; verdict: not
readable for RD-4. By fix kind as the stranger judged: cut 2,
rephrase 1, add 5; by locus: prose 2, IR 4, both 2. The three
contradictions are rule gaps the earlier rounds did not see: the
footprint comparison keyed on a Status an unreviewed IR never
reaches; the fix rule for readable rounds; "text" covering the IR
under `docs/records/`.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | footprint compared only when Status becomes `reviewed` | contradiction | rephrase C123: "Before delivery" |
| 2 | "recorded and fixed" vs readable-round findings unfixed | contradiction | rephrase C94: "treated like any other finding" |
| 3 | "A text under docs/" covers the IR | contradiction | rephrase C19: "Prose that will live under `docs/`" |
| 4 | C101 two actions | compound | split: C101, C171, C172 |
| 5 | "the unit" undefined | term | add C173, the unit's definition from P-008, 14 words (a rule the rewrite had dropped) |
| 6 | "designation" undefined | term | rephrase C133: "the state of its prose: active or delivered" |
| 7, 8 | reader glosses the Readers table holds | excess | cut: the glosses become links, which also satisfies P-004 |

Fixes after round 4: IR 165 to 168 claims (two splits, one added
definition); prose 2,829 to 2,824 words. Lint clean; round trip 168
of 168.

## Round 5, 2026-10-27 (revised brief, reads ordered)

2,824 words; 7 findings; 2.5 per thousand words. Restatement: 170
words; the stranger read "meta-review subject" as "required" and
counted the overstatement against C104 and C106. Contradictions 0,
undefined terms 1 ("the limit" one sentence before its definition);
verdict: not readable for RD-4. By fix kind as the stranger judged:
cut 1, rephrase 2, add 4; by locus: prose 1, IR 1, both 5.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | "the limit" before its definition | term order | add T19 (limit: ten rounds in one count) and the sentence "The limit is ten rounds in one count" before the count's definition; C89 loses "ten rounds"; net six words |
| 2 | C72 two rendering rules | compound | split: C72, C174 |
| 3 | "the checks run and" repeats C111 | excess | cut from C119 |
| 4 | the default clause under "Purpose" | header | rephrase: heading "Purpose and scope" |
| 5 | RD-1, RD-2, RD-3, RD-5 linked but not named | identifier | declined: P-004 accepts a parenthesized name or a link; round 4 cut the names as excess |
| 6 | "meta-review subject" read as a mandatory dispatch | restatement | declined: the two sentences that follow state what the label obliges (the pending line; the ask to the owner) |
| 7 | Reader line's role clause has no claim | IR gap | add C175 in the IR |

Fixes after round 5: IR 168 to 170 claims, terms 18 to 19; prose
2,824 to 2,830 words, the first round in which the prose grew (six
words, for the limit's definition). Lint clean; round trip 170 of 170.
Two findings declined, the first declines since round 1a.

## Round 6, 2026-10-27 (revised brief, reads ordered)

2,830 words; 12 findings; 4.2 per thousand words, up from 2.5.
Restatement: 185 words; "each element" for the status rule and
"required" for the meta-review subject, both called restatement
error by the stranger; the limit held as a term with no claim.
Contradictions 2, undefined terms 1; verdict: not readable for RD-4.
By fix kind as the stranger judged: cut 0, rephrase 7, add 5; by
locus: prose 4, IR 1, both 7. Both contradictions sit in the Stranger
rounds paragraph that round 5's fixes rewrote: the until-readable rule
against the limit, and the delivered text against the owner's
delivery at the limit. The second stranger in a row read "meta-review
subject" as mandatory, so the paragraph now puts the ask before the
pending line.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | "count" before its definition | term order | rephrase: the limit defined without the count ("ten rounds"); the count then uses the limit |
| 2 | "rework" before its definition | term order | cut "or to rework" from T14; C171 covers the rework case |
| 3 | until readable vs ends at the limit | contradiction | rephrase C88 "until a round returns readable or the count reaches the limit"; C89 becomes the limit claim |
| 4 | delivered text vs delivery at the limit | contradiction | rephrase C155: "After a readable verdict" |
| 5–7 | rule and reason in one sentence (C84, C121, C132) | compound | split: C176, C177, C178, each supporting its rule by relation |
| 8 | "The performing session" | referent | rephrase C108: "The session the owner starts" |
| 9 | "dependent asks" unlinked to its definition | term | rephrase C110: "dependent asks (asks with a `Depends:` field)" |
| 10 | RD-1, RD-2, RD-3, RD-5 unnamed | identifier | declined, as in round 5; third stranger to raise it, the SP-05 brief wording ("name and link") is stricter than P-004 ("name or link") |
| 11 | "The reasoning role records in the review record" repeated | excess | rephrase C103: "The review record holds, per round" |
| 12 | the limit sentence had no claim | IR gap | C89 restated as the limit claim |

Fixes after round 6: IR 170 to 173 claims (three reason splits);
prose 2,830 to 2,839 words (nine words, from the three split reasons
restating their subjects). Lint clean; round trip 173 of 173.

## Round 7, 2026-10-27 (revised brief, reads ordered)

2,839 words; 7 findings; 2.5 per thousand words. Restatement: 190
words; one mismatch (C44, C45) the stranger called its own.
Contradictions 2, undefined terms 0; verdict: not readable for RD-4.
By fix kind as the stranger judged: cut 2, rephrase 2, add 3; by
locus: prose 5, IR 1, both 1.

Four of the seven findings (1, 2, 4, 5) quote sentences round 6
had fixed in the IR but not in the prose: the reasoning role's first
edit script of round 6 aborted on an unmatched anchor and its earlier
replacements were lost, while the render map was updated by a second
script. The mechanical round trip passed, because it reads only the
map. The stranger found the drift. Two lessons for the process: the
round trip needs a semantic half (the stranger's), as the rendering
rule says; and a fix is not applied until the prose is re-read
against the changed claims.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1, 2 | until readable vs ends at the limit | contradiction (prose drift) | rephrase: the round 6 fix applied to the prose |
| 3 | T14 omits rework as an end of a count | contradiction (IR) | declined: the count ends at the limit; rework follows the owner's decision and starts a new count (C171) |
| 4 | "count" before its definition | term order (prose drift) | rephrase: the round 6 fix applied |
| 5 | rule and reason in one sentence (C84) | compound (prose drift) | rephrase: the round 6 split applied |
| 6 | 36-word inputs sentence | length | cut "to the conditions" from C110 |
| 7 | RD-1, RD-2, RD-3, RD-5 unnamed | identifier | declined, as in rounds 5 and 6; fourth stranger to raise it |

Fixes after round 7: IR 173 claims unchanged in count (C110
shortened); prose 2,839 to 2,823 words. Lint clean; round trip 173 of
173; the three drifted passages re-read against C84, C88, C89, C103,
C176 and T14, T19.
