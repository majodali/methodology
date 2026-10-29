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
| 8 | revised | 2,823 | 173 | 7 | 2.5 | not readable (contradictions 0, undefined terms 0; restatement mismatch on C44, C45 only) |
| 9 | revised | 2,814 | 173 | 7 | 2.5 | not readable (restatement matched; contradictions 1, undefined terms 1) |
| 10 | revised | 2,804 | 172 | 6 | 2.1 | readable (restatement matched; contradictions 0, undefined terms 0) |

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

## Round 8, 2026-10-27 (revised brief, reads ordered)

2,823 words; 7 findings; 2.5 per thousand words. Restatement: 196
words; one mismatch, the status rule (C44, C45), which the stranger
located in the prose: the exception sits in a second sentence and
the restatement missed it. Contradictions 0, undefined terms 0;
verdict: not readable for RD-4, on the restatement alone. By fix
kind as the stranger judged: cut 3, rephrase 2, add 2; by locus:
prose 6, IR 1.

The status-rule mismatch is the fifth in eight rounds (rounds 3, 4,
6, 7, 8): five strangers wrote "each element carries a status". The
text was correct each time. A text five readers compress the same
way has a defect the reader test finds and the rule list does not.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | status exception in a second sentence | restatement | rephrase C44: "Each term, claim and cluster, and no other element, ends with one status"; C45 cut |
| 2 | "Methodology-level" without a claim | IR gap | add C179 in the IR |
| 3, 4 | RD-1, RD-2, RD-3, RD-5 unnamed | identifier | declined, as in rounds 5 to 7; fifth stranger |
| 5 | "unit" before its definition | term order | rephrase: C173 before C76 |
| 6 | C88 restates the count's ends | excess | rephrase T14 "a sequence of rounds from a first round to its end"; C88 keeps the ends |
| 7 | "then" | excess | cut |

Fixes after round 8: IR 173 claims (one cut, one header claim
added); prose 2,823 to 2,814 words. Lint clean; round trip 173 of
173; the four changed passages re-read against C44, C88, C167, C173,
T14.

## Round 9, 2026-10-27 (revised brief, reads ordered)

2,814 words; 7 findings; 2.5 per thousand words. Restatement: 185
words, matching the IR, the first match of the count. Contradictions
1 (the term element must hold the term's meaning, and a term with a
definition site must not restate it; the IR's own T1 to T7 broke the
rule), undefined terms 1 ("inline gloss"); verdict: not readable for
RD-4. By fix kind as the stranger judged: cut 1, rephrase 2, add 4;
by locus: prose 3, both 4.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | C73 two prohibitions | compound | split: C73, C180 |
| 2 | term body vs no restatement | contradiction | rephrase C23: "either `defined-at:` ... or its meaning"; C26 cut; T1 to T7 lose their restated meanings |
| 3 | "inline gloss" undefined | term | rephrase C78: "carries its definition in parentheses instead of a link" |
| 4 | RD-1, RD-2, RD-3, RD-5 unnamed | identifier | declined, as in rounds 5 to 8; sixth stranger |
| 5, 6 | "Those rounds", "those rounds" | referent | rephrase: "The ten rounds", "the ten rounds" |
| 7 | "Otherwise the IR is delivered as it stands" repeats the table's last row | excess | cut C168 and R29 |

Fixes after round 9: IR 173 to 172 claims; prose 2,814 to 2,804
words. Lint clean; round trip 172 of 172; the five changed passages
re-read against C23, C73, C78, C140, C180. The first prose edit
script aborted again on a wrapped anchor; the second applied every
edit, checked by grep before the round was launched.

## Round 10, 2026-10-27 (revised brief, reads ordered)

2,804 words; 6 findings; 2.1 per thousand words. Restatement: 190
words, matching the IR. Contradictions 0, undefined terms 0;
verdict: readable for RD-4. The count ends at round 10 with a
readable verdict. The text delivered is the text this round judged.
The six findings are recorded unfixed, as the rule for a readable
round says; the next edit of the specification fixes them.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | RD-5 rule's scope: terms with a definition site | term scope | accepted finding, unfixed; fix: C78 "a term with a definition site" |
| 2 | "reworked" two sentences before Rework's definition | term order | accepted finding, unfixed; fix: C101 before C100 |
| 3 | C136 two claims | compound | accepted finding, unfixed; fix: split |
| 4 | RD-1, RD-2, RD-3, RD-5 unnamed | identifier | declined, as in rounds 5 to 9; seventh stranger; raised for the meta-review as a brief-versus-rule disagreement (SP-05 "name and link" against P-004 "name or link") |
| 5 | "Register" unlinked at first use in its section | link | accepted finding, unfixed; fix: link |
| 6 | "from a first round to its end" | excess | accepted finding, unfixed; fix: cut from T14 |

Footprint before delivery: declared 3, changed 3, surprises 0,
misses 0. IR Status set to `reviewed (unratified terms 12; surprises
0; misses 0; round 10 readable)`.

## Verdict

Readable for RD-4 at round 10 of a count of ten, by the revised
brief. Findings per thousand words by round: 7.6 (old brief) and 9.0
(revised) at round 1, then 4.5, 6.0, 2.8, 2.5, 4.2, 2.5, 2.5, 2.5,
2.1. Prose 2,884 words at round 1 and 2,804 at round 10; IR 148
claims at round 1 and 172 at round 10, the growth from splits. The
same rules in PR #51's text, fixed in prose, ran 2,572 to 4,516 words
over ten rounds and never reached readable.

## After the count, 2026-10-27

The owner accepted the text (PR #52 merged) and ratified the twelve
terms and the proposed claims. The ratification edit added the twelve
vocabulary rows, set the IR's terms to decided with their definition
sites, and fixed the accepted findings of round 10 (findings 1, 2,
3, 6; finding 5's link was already present); finding 4 stays
declined. Prose 2,804 to 2,808 words;
IR 172 to 173 claims (C136 split). The edit fixes accepted findings
and ratification only, so it starts no new rounds.

Count 1 meta-review: delivered, 2026-10-27, by a fresh session with no
part in the rounds: communication-pipeline
[evaluation case 007](https://github.com/majodali/communication-pipeline/blob/main/eval/cases/007-meta-review-full-ir-rounds-2026-10-27.md)
(seven changes proposed, six recommended; the round-10 text judged
readable for RD-4). Count 2 below has its own line.

## Count 2, 2026-10-27: the readable round's findings fixed before delivery

Amendment from communication-pipeline evaluation case 008, change 5,
adopted by the owner on 2026-10-27. Claims C97, C155 and C156
rewritten, C182 to C184 added, R27 and R28 changed, R33 added. The
prose edit is the Stranger rounds paragraph on the readable verdict
and one History sentence. Rounds under the pipeline's v1.5 procedure:
the claims check before each round, the stranger reading the prose
first, the confirmation after the fixes, declined findings carried.
The document's status line stays `active` on main while the IR's
Status carries the round; the brief lists that form.

### Curve, count 2

| Round | Prose words | IR claims | Findings | Per 1,000 words | Verdict |
|---|---|---|---|---|---|
| 1 | 2,877 | 176 | 15 | 5.2 | not readable (7 in-prose definitions without claims; 1 contradiction; 0 undefined terms) |
| 2 | 2,771 | 176 | 9 | 3.2 | not readable (restatement mismatch on C44, the stranger's own; 1 contradiction, 1 undefined term) |
| 3 | 2,796 | 177 | 5 | 1.8 | not readable (restatement mismatch on C44, the stranger's own; 1 contradiction, 0 undefined terms) |
| 4 | 2,797 | 177 | 3 | 1.1 | readable (restatement matched; 0 contradictions, 0 undefined terms) |

### Round 1, count 2, 2026-10-27

2,877 words; 15 findings; 5.2 per thousand words. Restatement: 190
words; seven mismatches, all in-prose definitions (round, count,
referent, register fact, review record, meta-review, the normative
gloss) that no claim backed once the terms were ratified and their T
elements dropped their meanings. Contradictions 1 (the delivered text
"fixed and confirmed" against an unfixed finding allowed), undefined
terms 0; verdict: not readable for RD-4. By fix kind as the stranger
judged: cut 7, rephrase 1, add 7; by locus: IR 7, both 8.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1, 2, 5, 6 | definitions of round, count, referent, register fact in the prose without claims | duplicate definition | cut; the term linked to its vocabulary row at first use in the section (P-008) |
| 3 | "by a session with no part in the rounds" (meta-review definition) | duplicate definition | cut with the definition sentence; the term linked |
| 4 | the review record's file name | duplicate definition | cut; linked |
| 7 | the normative gloss in the header row | duplicate definition | cut; linked |
| 8 | C155 vs C183 | contradiction | rephrase C155: "with each finding fixed and confirmed or marked unfixed" |
| 9 | "that round" | referent | rephrase: "the readable round" |
| 10, 11, 12, 13 | duties without an actor (C152, C183, C136, C158) | SP-18 | rephrase: the reasoning role named |
| 14 | "on a text at the limit" repeated | excess | cut from C102 |
| 15 | "the owner starts" repeated | excess | rephrase C108: "That session" |

Prose 2,877 to 2,768 words. Claims check (stale-aware) before round
2: 7 changed claims, 0 missing, 0 stale. Same-instance confirmation:
15 of 15 fixes hold; two new defects noted in the fixed passages and
fixed: "the term" without an antecedent (C136: "the ratified term");
"That session" (C107 names the meta-review session, C108 uses the
name). Claims check after: 3 changed, 0 missing, 0 stale.

### Round 2, count 2, 2026-10-27

2,771 words; 9 findings; 3.2 per thousand words. Restatement: 190
words; one mismatch (C44) the stranger called its own, the status
rule again. Contradictions 1 (the delivered text "judged" against the
fixes applied at the readable verdict), undefined terms 1 ("anchored
row"); verdict: not readable for RD-4. By fix kind as the stranger
judged: cut 1, rephrase 1, add 7; by locus: both 9.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1, 2, 3, 4, 5 | duties without an actor (C86, C169, C144, C135, C119) | SP-18 | rephrase: the reasoning role named; C135 split (C185) |
| 6 | "to match" without its object | referent | rephrase C169: "to match the IR" |
| 7 | the delivered text "judged" vs the fixes applied | contradiction | rephrase C155 to the stranger's wording |
| 8 | "anchored row" undefined | term | rephrase C136: "a row with a `def-` anchor" |
| 9 | "for the reader" | excess | cut from C74 |

Prose 2,771 to 2796 words. Claims check (stale-aware) before round 3:
9 changed or new claims, 0 missing, 0 stale. Same-instance
confirmation: 9 of 9 fixes hold, no new defect. Round 3 starts, so
count 2 makes the text a meta-review subject again.

### Round 3, count 2, 2026-10-27

2,796 words; 5 findings; 1.8 per thousand words. Restatement: 170
words; one mismatch (C44, C165) the stranger called its own, the
status rule for the seventh time across the two counts. Contradictions
1 (fixes required at the readable verdict against findings marked
unfixed, with no condition for unfixed), undefined terms 0; verdict:
not readable for RD-4. By fix kind as the stranger judged: cut 2, add
3; by locus: prose 1, both 4.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | "and then" | excess | cut "then" (C83) |
| 2 | the marking duty repeats the disposition rule and C155 | excess | cut; C182 becomes the condition for unfixed |
| 3 | no condition for an unfixed finding | contradiction | rephrase C182: "A finding whose fix the instance does not confirm is unfixed." |
| 4 | the checks run with no actor | SP-18 | rephrase C111: "A lint runs" |
| 5 | the IR edited with no actor | SP-18 | rephrase C134: the reasoning role |

Prose 2,796 to 2794 words. Claims check (stale-aware) before round 4:
4 changed claims, 0 missing, 0 stale. Same-instance confirmation: 5
of 5 fixes hold; one new defect noted and fixed, "the instance" with
its antecedent in the previous sentence (C182 names the readable
round's stranger instance). Claims check after: 1 changed, 0 missing,
0 stale.

### Round 4, count 2, 2026-10-27

2,797 words; 3 findings; 1.1 per thousand words. Restatement: 190
words, matching the IR. Contradictions 0, undefined terms 0; verdict:
readable for RD-4. The count ends at round 4. Under the rule this
amendment introduces, the three findings are fixed and the round's
instance confirms each before delivery. By fix kind as the stranger
judged: cut 1, add 2; by locus: prose 2, both 1.

| # | Finding (shortened) | Kind | Fix | Confirmation |
|---|---|---|---|---|
| 1 | no actor delivers after the owner's "delivered" decision | SP-18 | add C186: the reasoning role delivers (a rule PR #51's text had and the rewrite dropped) | confirmed |
| 2 | "HTML" not in C83 | mismatch | cut | confirmed |
| 3 | "that claim" | referent | rephrase C41: "the claim that holds the phrase" | confirmed |

Claims check (stale-aware) after the fixes: 2 changed or new claims,
0 missing, 0 stale. Prose 2,797 to 2811 words.

Same-instance confirmation before delivery: 3 of 3 fixes hold, each
marked confirmed above; none unfixed. The confirmation noted that the
new delivery sentence read against "does not deliver the text" at the
limit; C99 was scoped to the time before the owner's decision and the
instance confirmed the pair. IR Status set to `reviewed (count 2,
round 4 readable; fixes confirmed)`.

### Verdict, count 2

Readable for RD-4 at round 4 of a count of four. Findings per thousand
words by round: 5.2, 3.2, 1.8, 1.1. Contradictions by round: 1, 1, 1,
0, each a different conflict inside the new readable-round rule, and
each found by the next stranger. Prose 2,877 words at round 1 and
2,811 at delivery; IR 176 claims at round 1 and 178 at delivery. The
procedure's steps on this count: the stale-aware claims check found no
missing and no stale claim in five runs; the same-instance
confirmation found every fix holding and noted three new defects
(rounds 1, 3 and 4), each fixed; the carried decline was not raised;
the status rule drew its seventh self-attributed restatement
compression across the two counts, without a prose change this time.

Count 2 meta-review: not required. Owner decision of 2026-10-27,
on accepting the amendment: the three-round trigger predates the
measurements and is to be revisited.

## Count 3, 2026-10-27: the meta-review trigger is signal-based

Amendment by owner decision of 2026-10-27: the four signals replace
the trigger of three rounds; the limit stays. Claims C104 and C105
rewritten, C187 to C193 added, T20 proposed, R34 to R38 added. The
prose edit is the Meta-review paragraph and one History sentence.
Rounds under the pipeline's v1.5 procedure.

### Curve, count 3

| Round | Prose words | IR claims | Findings | Per 1,000 words | Verdict |
|---|---|---|---|---|---|
| 1 | 2,970 | 185 | 3 | 1.0 | readable (restatement matched; 0 contradictions, 0 undefined terms) |

### Round 1, count 3, 2026-10-27

2,970 words; 3 findings; 1.0 per thousand words. Restatement: 180
words, matching the IR. Contradictions 0, undefined terms 0; verdict:
readable for RD-4. The count ends at round 1. The three findings are
fixed and the round's instance confirms each before delivery.

| # | Finding (shortened) | Kind | Fix | Confirmation |
|---|---|---|---|---|
| 1 | "signal or none" | excess | cut (C192) | confirmed |
| 2 | "meta-review subject" used in the signal's definition before the rule | term order | cut the clause; T20 points at the section | confirmed |
| 3 | the kept review record has no actor | SP-18 | rephrase C172: the reasoning role keeps it | confirmed |

Claims check (stale-aware) after the fixes: 2 changed claims, 0
missing, 0 stale. Prose 2,970 to 2964 words.

Same-instance confirmation before delivery: 3 of 3 fixes hold, each
marked confirmed above; the instance noted that "named in this
section" added words that supplied no definition or referent, against
the fix rule, and the words were cut. Footprint before delivery:
declared 5, changed 5, surprises 0, misses 0 (docs/vocabulary.md added
to the declaration after a first run showed it as a surprise).

### Verdict, count 3

Readable for RD-4 at round 1. Findings 3, at 1.0 per thousand words;
contradictions 0. Prose 2,970 words at round 1 and 2,961 at delivery;
IR 185 claims.

Meta-review: not indicated. Signals checked at the end of count 3,
under the rule this count introduces: first, no fix rejected and no
missing or stale claim; second, no finding raised again and no
mismatch recurring; third, growth of minus 0.3 percent; fourth, no
round after round 3. The limit was not reached.

Count 3 accepted by the owner on 2026-10-27 (PR #57 merged); the term
meta-review signal ratified and its vocabulary row added.

## Count 4, 2026-10-29: evaluation case 009's changes 2, 14, 15 and 18

Reader RD-4. Disposition D3 (Normative: yes): the reasoning role rendered the amended passages from the IR; a fresh haiku stranger per round under the branch point v1.6 brief with the calibrations of case 009 the owner adopted on 2026-10-29 (SP-01: a duty with its actor and trigger is one claim; SP-18: a target or roadmap work assigned to no one is not a duty; SP-26: words naming a referent SP-03 requires are not excess; a rule joined by because, so or therefore to a reason the IR holds is not a defect). Text reviewed: `docs/intermediate-representation.md` whole; the IR covers the whole text, 192 claims after this count's eight new claims (C194, C195, C197 to C201) and two reworded (C189, C190).

Lint before round 1 (case 009 change 17): IR checks clean. Prose SP-02: nine sentences over 25 words before the fixes, two of them this count's (C189 at 27, C194 at 26), shortened to 21 and 25. Seven predate the count and are left for the editorial pass the backlog holds: the opening's assumed-knowledge line (26), the three-failure-modes sentence (26), the P-008 unit sentence (26), the verdict's three-condition list (35), the rendering-conditions input list (33), the direct-prose report sentence (30), the History's rewrite sentence (28). None over 35.

### Curve, count 4

| Round | Prose words | IR claims | Findings | Per 1,000 words | Verdict |
|---|---|---|---|---|---|
| 1 | 3,089 | 192 | 9 | 2.9 | not readable (restatement matched, 2 own mismatches; contradictions 0; undefined terms 3) |
| 2 | 3,117 | 193 | 16 | 5.1 | not readable (restatement matched, 4 own mismatches; contradictions 0; undefined term 1) |
| 3 | 3,143 | 201 | 4 | 1.3 | not readable (restatement matched; contradictions 0; undefined term 1) |
| 4 | 3,163 | 203 | 8 | 2.5 | readable (restatement matched, 1 own mismatch; contradictions 0; undefined terms 0) |

### Round 1, count 4, 2026-10-29

Stranger model: claude-haiku. Prose 3,089 words; 9 findings, 2.9 per thousand words. Restatement: matched the IR; two mismatches the instance attributed to its own restatement, each naming its claim and quoting the sentence relied on. Contradictions 0, undefined terms 3; verdict: not readable for RD-4. Every finding sits on text older than this count. By fix kind as the stranger judged: rephrase 6, add 3.

Mismatches: C44 (own), C104 (own)

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1, 2 | own-caused mismatches on provenance scope (C44) and the subject rule's limit condition (C104) | restatement | no prose defect; claims named |
| 3 | the proposed-term listing has no trigger | SP-18 | rephrase C152: in the report that delivers the text |
| 4 | "The rendering follows", "The rendering states" name no actor | SP-18 | rephrase C81, C82: the renderer, the paraphraser or the reasoning role |
| 5, 6 | "unratified-vocabulary indicator", "prediction-surprise indicator" undefined | SP-04 | rephrase C50, C127: the mechanical measure of unratified vocabulary (prediction surprise), one indicator of convergence |
| 7 | "Methodology-level specification" undefined | SP-04 | rephrase C179: a methodology Specification, the document type, linked |
| 8 | header "When an IR is required" is a clause | SP-10 | rephrase: "Texts that require an IR" |
| 9 | the delivered-text sentence carries the marking rule too | SP-01 | split C155; C202 |

Claims after fixes: 193. Prose after fixes: 3,117 words.

Confirmation: 6 of 7 fixes hold. Not held: 6. Declines accepted: 0 of 0. New defects: 0.

Finding 6 fixed again before round 2: C127 now reads "The counts of surprises and misses measure one indicator of convergence: how far the footprint's prediction missed", defining the indicator in the sentence. Findings 1 and 2 needed no fix.

### Round 2, count 4, 2026-10-29

Claims check before the round: 8 changed claims, 0 missing, 0 stale (base: round 1 prose). Stranger model: claude-haiku. Prose 3,117 words; 16 findings, 5.1 per thousand words, 12 of them prose findings. Restatement: matched the IR; four mismatches the instance attributed to its own restatement, each naming its claim and the sentence relied on. Contradictions 0, undefined terms 1 ("footprint" unlinked in the Footprint section); verdict: not readable for RD-4. Every prose finding sits on text older than this count, five of them the long sentences round 1's lint note had left for the editorial pass. By fix kind as the stranger judged: rephrase 10, cut 1, add 1.

Mismatches: C93 (own), C41 (own), C73 (own), C74 (own), C135 (own)

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| F1 to F4 | own-caused mismatches | restatement | no prose defect; claims named |
| F5 | the marking of readable-round findings has no actor | SP-18 | rephrase C202: the reasoning role marks |
| F6 | "is treated like any other finding" | SP-18 | rephrase C94: the reasoning role treats |
| F7 | the linking, defining and placing duties have no actor | SP-18 | rephrase C76, C77, C79: the renderer links, defines, places |
| F8 | "footprint" unlinked | SP-04 | add the link to the vocabulary row |
| F9 | the verdict sentence at 35 words | SP-02 | split C93; C203 the conditions |
| F10 | the inputs sentence at 33 words | SP-02 | split C110; C204, C205 |
| F11 | the direct-prose sentence at 30 words | SP-02 | split C131; C206 |
| F12 | the History's rewrite sentence at 28 words | SP-02 | split C140; C207 |
| F13 | the three-failure-modes sentence at 26 words | SP-02 | rephrase C4: directly written prose |
| F14 | the second signal's two conditions in one sentence | SP-01 | split C188; C208 |
| F15 | the Meta-review line's write and naming in one sentence | SP-01 | split C191; C209 |
| F16 | "The IR of a delivered report is a record." as excess | SP-26 | declined: the sentence states the IR's status, record, from which the next sentence's rule follows; cutting it loses C135 and the term's use |

Claims after fixes: 200. Prose after fixes: 3143 words. The prose fixes landed one commit after the IR's, an edit script having stopped on a render-map anchor.

Confirmation: 9 of 11 fixes hold. Not held: F12, F13. Declines accepted: 1 of 1. New defects: 2.

Fixed again before round 3: C4 shortened to 22 words; C207 split, C210 the growth figures; C203 restored to one condition per list item at 24 words (the two new defects N1 and N2 of the confirmation).

### Round 3, count 4, 2026-10-29

Claims check before the round: 20 changed claims, 0 missing, 0 stale (base: round 2 prose). Stranger model: claude-haiku. Prose 3,143 words; 4 findings, 1.3 per thousand words. Restatement: matched the IR, no mismatch. Contradictions 0, undefined terms 1 ("restatement mismatch", a term this count's C195 introduced); verdict: not readable for RD-4. By fix kind as the stranger judged: rephrase 4.

Mismatches: none

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | "restatement mismatch" undefined | SP-04 | add T21 restatement, defined at the pipeline's vocabulary, linked at first use; C211 defines a restatement mismatch in a sentence of its own |
| 2 | the style-rows duty has three actors and no trigger | SP-18 | rephrase C81: "When rendering, ..." |
| 3 | the Footprint section opens with its exemption | SP-11 | reorder: the comparison duty first, the chat-message exemption after; no claim changed |
| 4 | the History's adoption sentence holds two facts | SP-01 | split C138; C212 |

Claims after fixes: 203. Prose after fixes: 3163 words.

Confirmation: 4 of 4 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 0.

### Round 4, count 4, 2026-10-29

Claims check before the round: 4 changed claims, 0 missing, 0 stale (base: round 3 prose). Stranger model: claude-haiku. Prose 3,163 words; 8 findings, 2.5 per thousand words, 7 of them prose findings. Restatement: matched the IR; one mismatch the instance attributed to its own restatement, naming C41 and the sentence relied on. Contradictions 0, undefined terms 0; verdict: readable for RD-4. The count ends at round 4. Under step 7, the findings are fixed and the round's instance confirms each before delivery. By fix kind as the stranger judged: rephrase 6, cut 1.

Mismatches: C41 (own)

| # | Finding (shortened) | Kind | Fix | Confirmation |
|---|---|---|---|---|
| 1 | own-caused mismatch on C41 | restatement | no prose defect | n/a |
| 2, 3 | the P-008 unit sentence attributes the unit to P-008 and runs to 26 words | SP-01, SP-02 | rephrase C173: "The unit for P-008 is the whole text for a report and the section for a document." | confirmed |
| 4 | two additions in one History sentence | SP-01 | split C147; C213 | confirmed |
| 5 | three additions in one History sentence | SP-01 | split C148; C214 | confirmed |
| 6 | two changes in one History sentence | SP-01 | split C200; C215 | confirmed |
| 7 | the Rendering conditions section opens with its inputs | SP-11 | reorder: "The first row whose condition holds decides." moves to the front; no claim changed | confirmed |
| 8 | "here" | SP-26 | cut from C212 | confirmed |

Claims after fixes: 207. Prose after fixes: 3181 words. The prose fixes landed three commits after the IR's, edit scripts having stopped on anchors broken by line wraps; the instance's first two confirmation reads saw the unfixed prose and were discarded; C148 was split a second time (C216) and C215 names the case's repository at the instance's note. The prose fixes landed one commit after the IR's, an edit script having stopped on the first anchor; the instance was told to re-read before confirming.

Confirmation: 7 of 7 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 0.

The instance's first two confirmation reads saw the prose before its fixes landed and were discarded; the third read, on commit 108e26d, is the one recorded. At the instance's notes, C148 was split a second time (C216) and C215 names the case's repository.

### Verdict, count 4

Readable for RD-4 at round 4 of a count of four. Findings per thousand words by round: 2.9, 5.1, 1.3, 2.5. Contradictions by round: 0, 0, 0, 0. Prose 3,089 words at round 1 and 3,181 at delivery; IR 192 claims at round 1 and 207 at delivery, the growth from splits for one claim per sentence and the sentences shortened under case 009's change 17. Every accepted fix confirmed by its round's instance; one decline (round 2, F16) accepted by the instance. Thirty-six of the thirty-seven findings fell on text older than this count.

Meta-review: pending (signals 1 and 2). Signals checked at the end of count 4 by `scripts/signals.mjs` (reading the last count) and by reading: first, fired, as the rule reads: fixes were not held at confirmation in rounds 1 (one of seven) and 2 (two of eleven), and in rounds 2 and 4 the prose fixes did not reach the prose on their first write, each refixed and confirmed afterwards; second, fired: C41 stands on the Mismatches lines of rounds 2 and 4, both times attributed by the stranger to its own restatement, which under the branch point's step 6 made the passage a prose finding owed a structural fix before round 5; the reasoning role's hand check missed the recurrence and the count closed readable at round 4, so the passage, the Relation row's sentence "A reference from one claim to another is a relation, never a pronoun inside the claim" read twice as barring every pronoun, is owed its structural fix at the next edit; no declined finding raised again; third, words per IR claim 16.1 to 15.6, minus 3 percent; fourth, no contradiction in round 3 or later. The limit was not reached. The reasoning role asks the owner, in the report that delivers this count, to dispatch the meta-review.
