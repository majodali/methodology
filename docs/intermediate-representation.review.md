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

Meta-review: delivered (signals 1 and 2; pending at the close on 2026-10-29): [evaluation case 010](https://github.com/majodali/communication-pipeline/blob/main/eval/cases/010-meta-review-ir-spec-count-4-2026-10-30.md), 2026-10-30. Signals checked at the end of count 4 by `scripts/signals.mjs` (reading the last count) and by reading: first, fired, as the rule reads: fixes were not held at confirmation in rounds 1 (one of seven) and 2 (two of eleven), and in rounds 2 and 4 the prose fixes did not reach the prose on their first write, each refixed and confirmed afterwards; second, fired: C41 stands on the Mismatches lines of rounds 2 and 4, both times attributed by the stranger to its own restatement, which under the branch point's step 6 made the passage a prose finding owed a structural fix before round 5; the reasoning role's hand check missed the recurrence and the count closed readable at round 4, so the passage, the Relation row's sentence "A reference from one claim to another is a relation, never a pronoun inside the claim" read twice as barring every pronoun, is owed its structural fix at the next edit; no declined finding raised again; third, words per IR claim 16.1 to 15.6, minus 3 percent; fourth, no contradiction in round 3 or later. The limit was not reached. The reasoning role asks the owner, in the report that delivers this count, to dispatch the meta-review.

## Count 5, 2026-10-30: evaluation cases 010 and 011

Inputs: the owner's adoption on 2026-10-30 of communication-pipeline evaluation cases 010 and 011 ("For cases 010 and 011 - go with all recommendations, all terms ratified."). Seven adopted changes amend this specification: case 010's changes 1, 5, 9, 11, 12 and 13 and case 011's change 1. The others amend the communication-pipeline branch point, as its v1.9. Reader RD-4. Disposition D3 (Normative: yes): the reasoning role rendered the amended passages from the IR. Text reviewed: `docs/intermediate-representation.md` whole; the IR covers the whole text.

Branch point version and commit the count runs under (case 010 change 10): v1.9 as proposed, communication-pipeline commit 8019eee on branch `branch-point-v1.9-cases-010-011`, the changes the owner adopted before this count. Confirmed by the Orchestrator before round 1: the owner adopted the changes on 2026-10-30, before this count opened, so they apply to it under case 010 change 10; the pipeline's own rounds on v1.9 run in parallel.

Changes to the IR. C203 reworded and split (C221). C222 to C224 added, the own-mismatch rule, with T22 own mismatch. C187 reworded to the branch point's first signal, with T23 claims check linked to the branch point's Rounds section. C189 reads "in the count's last round". C35 moved into The referent rule after C41, its identifier kept. C220 added, the renderer defined before C76; C81 drops its appositive. C76, C77, C79, C82, C94, C152 and C202 made inferred (R44 to R50). C225 added to the History. 210 claims before the count's edit; 216 after.

Case 011 change 1 in this text. The case's sentence "A mismatch that step 6 makes a prose finding always counts" names the branch point's step 6, which this specification does not hold. C224 renders it in the second signal's words: "A restatement mismatch that recurred on one passage always counts against the verdict." C224 is inferred by R52.

The C41 passage (case 010 change 11). C35, "A reference from one claim to another is a relation, never a pronoun inside the claim", moved from the Element kinds table's Relation row into The referent rule, after C41. The move is the structural fix for the mismatch on C41 in count 4's rounds 2 and 4. Round 1's entry of this count states whether its restatement matched on the passage of C41 and C35.

The sources of eight claims (case 010 change 13). A claim whose source names no actor becomes inferred, with a relation naming its basis.

| Claim | Source | Actor in the source | Decision |
|---|---|---|---|
| C76 | methodology PR #48: "A term with a definition site is linked at its first use" | none | inferred, R44 (the renderer, C220) |
| C77 | methodology PR #46: "A term the IR introduces is defined in a sentence of its own" | none | inferred, R45 (the renderer, C220) |
| C79 | pipeline schema v1.2: "a claim renders under the part its `part:` field names" | none | inferred, R46 (the renderer, C220) |
| C81 | pipeline schema v1.2: "It follows the style specification for the IR's reader", after the paraphraser's and the reasoning role's sentences | the renderer, by the pronoun | stays decided; the appositive dropped (change 12) |
| C82 | methodology PR #46: "The rendering states an empty Asks section" | none | inferred, R47 (the renderer, C220) |
| C94 | the owner's ratification of 2026-10-27 of "a finding ... is a finding like any other" | none | inferred, R48 (the reasoning role records dispositions, C95) |
| C152 | methodology PR #48: a proposed term "listed for ratification" | none, and no trigger | inferred, R49 (Terms introduced, C153) |
| C202 | case 008 change 5: "the record marks each confirmed or unfixed" | none | inferred, R50 (the reasoning role records dispositions, C95) |

Lint before round 1 (case 010 change 8, case 011 change 8). IR checks: 0 violations, 0 warnings. Sentences over 25 words in the prose: 2, the Status line (49) and the Reader paragraph's assumed-knowledge sentence (26), both header forms; `mtool style` warns on the Status line only. Neither was changed by this edit.

Three gaps remain from the edit of 2026-10-30 for IR-only documents. This count does not change them. The render map omits C217 to C219. C13's Status values omit `delivered IR-only`. The prose's "another is whether the owner designated the document IR-only" has no claim.

### Curve, count 5

| Round | Prose words | IR claims | Findings | Per 1,000 words | Verdict |
|---|---|---|---|---|---|
| 1 | 3,368 | 216 | 20 | 5.9 | not readable (four own mismatches on five claims, C104 a step-6 mismatch that counts; contradictions 2; undefined terms 4) |
| 2 | 3,413 | 220 | 6 | 1.8 | not readable (two own mismatches, C41 a step-6 mismatch that counts; contradiction 1; undefined terms 0) |
| 3 | 3,443 | 222 | 9 | 2.6 | not readable (two own mismatches, quoted; contradictions 0; undefined terms 3) |
| 4 | 3,471 | 223 | 8 | 2.3 | not readable (three own mismatches, quoted, two step-6 passages that count; contradiction 1; undefined terms 3) |
| 5 | 3,568 | 230 | 5 | 1.4 | not readable (three own mismatches on the two step-6 passages, counting under the override; contradictions 0; undefined terms 0) |
| 6 | 3,640 | 232 | 8 | 2.2 | not readable (one own mismatch, quoted, not counting; contradiction 1; undefined terms 0) |
| 7 | 3,727 | 236 | 14 | 3.8 | not readable (five own mismatches, three counting; contradictions 0; undefined term 1) |
| 8 | 3,752 | 238 | 8 | 2.1 | not readable (three own mismatches, two on step-6 passages counting under the override; contradictions 2; undefined terms 0) |
| 9 | 3,836 | 244 | 4 | 1.0 | not readable (one own mismatch, quoted, not counting by the Orchestrator's ruling; contradiction 1; undefined term 1) |
| 10 | 3,864 | 244 | 2 | 0.5 | not readable (restatement matched; contradiction 1; undefined terms 0) |

### Round 1, count 5, 2026-10-30

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier. Prose 3,368 words (whitespace-separated words, comments stripped, by `wordCount` in the communication-pipeline's `scripts/ir.mjs`); IR 216 claims; 20 findings, 5.9 per thousand words. Restatement: four mismatches, each attributed by the stranger to its own restatement, each with a quoted prose sentence. Contradictions 2 (findings 12, 20), undefined terms 4 (findings 5, 7, 8, 13); verdict: not readable for RD-4. Accepted 17 and one step-6 finding; declined 3.

Mismatches: C223 (own; relied on C223), C195 (own; relied on C195), C104 (own; relied on C104), C84 (own; relied on C220)

The relied-on claims are read from the Orchestrator's report that each quoted sentence carries the IR's claim. The quoted sentences themselves are not in this record; the Orchestrator holds the stranger's report.

Signals script after the `Mismatches:` line (branch point v1.9 step 6, case 010 change 2): signal 2 fired, "C104 in count 4 round 1; count 5 round 1". C84, C195 and C223 stood on no earlier count's line. Earlier counts' claims listed as information: C44, C93, C73, C74, C135 (count 4) and C41 (count 4, rounds 2 and 4). C104 is therefore a step-6 finding (finding 21 below): a prose finding whatever the attribution, owed a structural fix, and under the override it counts against the first condition. The first condition is not met in round 1. The own mismatches on C223, C195 and C84 do not count under the exception.

The C41 passage (case 010 change 11): the stranger states that its restatement matched on the passage of C35 and C41, after C35's move into The referent rule. Count 4's step-6 fix holds.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 to 4 | own mismatches on C223, C195, C104, and C84 with C220 | restatement | C223, C195, C84: no prose defect under the exception; C104: finding 21 |
| 5 | `delivered IR-only` unlinked in the Status row | SP-04 | add the link to the vocabulary row |
| 6 | "Every project-specific term used in a claim appears as a term element" names no actor | SP-18 | declined: a sentence stating what the document contains is a form rule, not a duty |
| 7 | "cluster" unlinked; "topic claim" undefined | SP-04 | add the link; add C226 "A topic claim is the claim that states the cluster's subject.", inferred by R53 |
| 8 | "review record" in CK-14 before its definition | SP-04 | add the link |
| 9 | `mtool ir check` with no link | SP-05 | add the link to methodology-tools |
| 10 | "Normative text is rendered by the reasoning role, not by the paraphraser" repeats the renderer's definition | SP-26 | cut C84; C176 moves beside C220; R6, R17 and R30 point at C220 |
| 11 | the IR-then-prose order stated four times | SP-26 | declined: each sentence is a rule for a distinct moment (a fix to rendered prose, the readable verdict, a not-readable verdict, the limit); they share the order and differ in trigger |
| 12 | the first condition counts every mismatch; the next sentences exempt one | SP-25 | rephrase C203, add C227, rephrase C223 and C224: the first condition with one exception and one override, as one rule; the definitions of restatement mismatch, own mismatch and passage moved before it |
| 13 | "passage" undefined; "recurred" with no round count | SP-04 | add C228 "A passage is the prose sentences that carry one claim or one cluster.", inferred by R55; C224 reads "on one passage in two rounds" |
| 14 | "rendering condition" before its section | SP-09 | rephrase: a link to the Rendering conditions section for "(table below)" |
| 15 | the input sentence holds two inputs | SP-01 | split; C229 "Another input is whether the owner designated the document IR-only." |
| 16 | "A term, a decision or a register fact requires the IR." names no actor | SP-18 | declined: a condition statement, not a duty |
| 17 | "The IR of a delivered report is not edited after delivery." names no actor | SP-18 | rephrase C161: "The reasoning role does not edit ..."; C161 inferred by R54 |
| 18 | "The record is the communication-pipeline project's analysis" has no antecedent | SP-03 | rephrase: "The communication-pipeline project's analysis records the ten rounds." |
| 19 | PR #51 unlinked at first use | SP-05 | add the link |
| 20 | C13's Status values omit `delivered IR-only` while C218 requires it | SP-25 | rephrase C13 to hold the value; the prose row already held it; the render map gains C217 to C219 |
| 21 | step 6: the mismatch on C104 in count 4 round 1 and count 5 round 1 | restatement, step 6 | structural fix: the subject sentence (C104) moves after the four signals and the reasoning role's check, and the ask to the owner (C106) moves beside the pending line, before "The owner may dispatch"; no claim changed; `awaiting restatement` |

Claims after fixes: 219. Prose after fixes: 3,389 words. Claims check after the fixes (base: round 1 prose): 9 changed claims, 0 missing, 1 stale (C13), 1 removed (C84). C13 reads stale because the fix brought the IR to the prose's existing Status row; the prose sentence carried the value before the fix. Round trip: 219 of 219 claims mapped.

The stranger's quoted sentences for the own mismatches (case 011 change 2):

- C223: "An own mismatch does not count against the verdict when the stranger quotes a prose sentence that carries the IR's claim."
- C195: "A restatement mismatch is not withdrawn at confirmation."
- C104: "A text is a meta-review subject when its count reaches the limit or its review record shows a meta-review signal."
- C84 with C220: "The renderer is the paraphraser or, for normative text, the reasoning role."

Each quoted sentence carries the claim the `Mismatches:` line relies on.

Confirmation: 16 of 17 fixes hold. Not held: 13. Declines accepted: 2 of 3. New defects: 4.

Finding 13 held in part: the second signal's sentence still lacked "in two rounds". The declines of findings 6 and 16 were accepted. The decline of finding 11 was not accepted by the instance; the decline stands on its reason (each sentence is a rule for a distinct moment, sharing the order and differing in trigger). Findings 6, 11 and 16 go into round 2's brief with their reasons. Finding 21, the step-6 fix on C104, was not put to the instance; it stays `awaiting restatement`.

Re-fixed before round 2:

| # | Defect (shortened) | Kind | Re-fix |
|---|---|---|---|
| 13, N1 | the second signal's sentence says "recurred on one passage" with no round count | SP-04, SP-25 | C208: "The second signal also fires when a restatement mismatch recurred on one passage in two rounds."; C208 inferred by R56; marked `awaiting restatement` as a second fix |
| N2 | passage and topic claim defined with no term element | CK-04 | T24 passage and T25 topic claim, status proposed; the Status parenthesis reads unratified terms 2; A5 asks the owner to ratify or strike them |
| N3 | C84's removal unrecorded in the History while the `Mismatches:` line cites C84 | SP-26 | C230: "In count 5, the sentence giving normative text to the reasoning role was cut as a repeat of the renderer's definition." |
| N4 | free-standing finding pointers at the end of R53, R54 and R55 | CK-16 | cut the pointers; each reason is one sentence |

Decided claims the fixes changed, for the owner: C84 cut (its rule is C220's); C161 gains the reasoning role and becomes inferred; C13 holds `delivered IR-only`, decided by the owner's IR-only option of 2026-10-30; C203, C223 and C224, with the new C227, join case 010 change 1's and case 011 change 1's texts into one rule; C208 gains "in two rounds" and becomes inferred.

### Round 2, count 5, 2026-10-30

Branch point version and commit: v1.9 at communication-pipeline commit cafe4d1 on branch `branch-point-v1.9-cases-010-011`, with its own round 1 fixes and re-fixes. Prose 3,413 words; IR 220 claims; unratified terms 2 (T24, T25).

Claims check before the round: 11 changed claims, 0 missing, 1 stale (base: round 1 prose). The stale claim is C13: the fix brought the IR to the prose's Status row, which held `delivered IR-only` before round 1. C84 removed.

Awaiting restatement: finding 21, the step-6 fix on the C104 passage (the meta-review subject sentence); C208, the second fix of finding 13. This round's entry states whether the restatement matched on each.

Signals script before the round: signal 1 fired on rounds 1 and 2, round 1 by finding 13 not held and both rounds by the C13 stale report; without the C13 report, signal 1 reads round 1 only. Signal 2 fired on C104 (count 4 round 1, count 5 round 1), already taken as finding 21. Signals 3 and 4 not fired. No line unparsed.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier. Prose 3,413 words by `wordCount` (the stranger's eye: about 5,000); IR 220 claims; 6 findings, 1.8 per thousand words. Restatement: two mismatches, each attributed by the stranger to its own restatement, each with a quoted sentence. Contradiction 1 (finding 5), undefined terms 0; verdict: not readable for RD-4, on the contradiction and on the step-6 mismatch on C41.

The stranger's quoted sentences: for C41, "The bare pronouns are it, this, that, these and those, with no noun after."; for C217, "Prose is rendered from the IR when a rendering condition selects rendering."
Mismatches: C41 (own; relied on C42), C217 (own; relied on C71)

Signals script after the `Mismatches:` line: signal 2 fired on C41 (count 4 rounds 2 and 4, count 5 round 2) and on C104 (count 4 round 1, count 5 round 1). C41 is therefore a step-6 finding: a prose finding whatever the attribution, owed a structural fix, and under the override it counts against the first condition. C217 stood on no earlier line. Signal 1 as before round 2.

Awaiting restatement from round 1: the C104 passage matched in part; the restatement omitted the limit trigger but did not disagree with it. Round 1's step-6 fix on C104 is recorded as matched on restatement. C208, the re-fix of finding 13, was named neither on the `Mismatches:` line nor in a finding.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | own mismatch on C41: the restatement dropped the determiner phrases from the antecedent rule | restatement, step 6 | structural fix: C41 split; C41 states the antecedent rule for a bare pronoun, beside the pronoun list, and C231 states it for a bare determiner phrase, beside the determiner list; C35 stays after C41; `awaiting restatement` |
| 2 | own mismatch on C217 | restatement | no prose defect, under the exception |
| 3 | CK-04's sentence at 29 words | SP-02 | split C58; C232 "a term in the project's `docs/vocabulary.md` is also a project-specific term" |
| 4 | "render map" first used at CK-15 before its definition | SP-04 | add the link to the vocabulary row, T11's definition site |
| 5 | the input list stated as complete, then extended by two owner inputs | SP-25 | rephrase C110: "…, longest claim and two owner inputs"; C205 and C229: "The first owner input is …", "The second owner input is …" |
| 6 | "The IR of a delivered report is a record" against the next sentence | SP-26 | declined: C135 is a decided claim stating the delivered IR's lifecycle state, and the next sentence is the duty that follows from it (C161, with its relation); a rendering drops no claim |

Claims after fixes: 222. Prose after fixes: 3,443 words. Claims check after the fixes (base: round 2 prose): 7 changed claims, 0 missing, 0 stale. Round trip: 222 of 222.

Confirmation: 5 of 5 fixes hold. Not held: none. Declines accepted: 1 of 1. New defects: 1.

The five are findings 3, 4 and 5 and the two mismatch dispositions: finding 1 is the step-6 fix, which stays `awaiting restatement`, and finding 2 is an own mismatch with no fix. For findings 3, 4 and 5 the instance's verdict words ("does not hold") judged the finding, and its statement that each defect is gone in the current text is the confirmation. On finding 1 the instance noted that its restatement still omits the determiner-phrase rule, now C231. The instance accepted finding 6's decline on its own reason: the sentence states retention.

Re-fixed before round 3:

| # | New defect (shortened) | Kind | Re-fix |
|---|---|---|---|
| N1 | C205 reworded in round 2 but keeps its v1.1 provenance unmarked | provenance | C205: "[decided: pipeline branch point v1.1, 2026-10-25; reworded for form in count 5, round 2]"; C229 likewise, "[decided: owner, 2026-10-30; reworded for form in count 5, round 2]". The specification has no rule for a decided claim reworded for form; the decided source stays and the note records the rewording. |

Decided claims the fixes changed, for the owner: C41 split into C41 and C231 (the step-6 structural fix); C58 split into C58 and C232; C110 names two owner inputs, decided by the owner's IR-only option of 2026-10-30; C205 and C229 renamed as the first and second owner inputs.

Declined findings for round 3's brief: round 1's 6, 11 and 16, and round 2's 6, each with its reason.

### Round 3, count 5, 2026-10-30

Branch point version and commit: v1.9 as at communication-pipeline branch `branch-point-v1.9-cases-010-011`, this round's opening commit. Prose 3,443 words; IR 222 claims; unratified terms 2 (T24, T25).

Claims check before the round: 7 changed claims, 0 missing, 0 stale (base: round 2 prose).

Awaiting restatement: round 2's step-6 fix on the referent rule (C41 and C231). C208, round 1's re-fix, was named neither on round 2's `Mismatches:` line nor in a finding, so it no longer awaits restatement. This round's entry states whether the restatement matched on the referent rule's determiner-phrase sentence.

Declined findings carried in the brief: round 1's 6, 11 (the instance did not accept the decline) and 16; round 2's 6; each with its reason.

Signals script before the round: signal 1 fired as before round 2 (rounds 1 and 2, the second by the C13 stale report only); signal 2 fired on C104 and C41, both already step-6 findings; signals 3 and 4 not fired; no line unparsed.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier. Prose 3,443 words by `wordCount`; IR 222 claims; 9 findings, 2.6 per thousand words. Restatement: two mismatches, each attributed by the stranger to its own restatement, each quoted. Contradictions 0, undefined terms 3 (findings 3, 5, 8); verdict: not readable for RD-4, on the undefined terms.

The stranger's quoted sentences: for C227, "The first condition: the stranger's restatement of the problem, terms and decisions has no mismatch with the IR."; for C194, "The second and third conditions: the stranger finds no contradiction and no undefined term."
Mismatches: C227 (own; relied on C203), C194 (own; relied on C221)

Each quoted sentence carries a neighbouring claim (C203, C221), not the contradicted one. The Orchestrator read both as not counting under the exception. On the branch point's round 3 the Orchestrator read the same case (C25 relied on C23) as counting; under that reading both mismatches here count as well. The verdict is not readable either way.

Signals script after the `Mismatches:` line: no new recurrence; C227 and C194 stood on no earlier line. Signal 1 and signal 2 (C104, C41) as before the round. Round 1's C223 mismatch sat on the same verdict rule as C227, on a different claim; the script reads claims, not passages.

Awaiting restatement from round 2: the restatement matched on the referent rule (C41, C231 and C35). Round 2's step-6 fix is confirmed by restatement.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | own mismatch on C227 | restatement | no prose defect; see the note on the exception above |
| 2 | own mismatch on C194 | restatement | no prose defect; see the note on the exception above |
| 3 | "project-specific term" in the Term row before CK-04 defines it | SP-04 | add an anchor on CK-04's definition and link the Term row's phrase to it |
| 4 | "A fix to prose rephrases …" and "A fix adds words only …" name no actor | SP-18 | rephrase C87 and C143: "The reasoning role rephrases …", "The reasoning role adds words …"; both inferred (R59, R60) |
| 5 | "confirmation" undefined at first use | SP-04 | add C233 at first use: "Confirmation is the step at which the round's stranger instance says whether each fix holds."; inferred by R58 |
| 6 | "The review record marks each finding of the final round confirmed or unfixed." names no actor | SP-18 | rephrase C199: "The reasoning role marks … in the review record."; inferred by R61 |
| 7 | the first signal's two triggers joined by "or" | SP-01 | declined: the sentence states one signal whose condition is a disjunction; its wording is case 010 change 5's adopted text, and the branch point carries the same sentence |
| 8 | "dependent ask" used in the input list before its definition | SP-04 | reorder: C204 before C110; no claim changed |
| 9 | the case identifiers in the History unlinked | SP-05 | add links to cases 008, 009, 010 and 011 in communication-pipeline at first use |

Claims after fixes: 223. Prose after fixes: 3,471 words. Claims check after the fixes (base: round 3 prose): 4 changed claims, 0 missing, 0 stale. Round trip: 223 of 223.

Confirmation: 4 of 7 fixes hold. Not held: 3, 5, 8. Declines accepted: 1 of 1. New defects: 2.

The seven fixes are 3, 4 (two claims, C87 and C143), 5, 6, 8 and 9. The instance held the prose of 3, 4, 6, 8 and 9 and reported the IR behind the prose on 3, 5 and 8. The Orchestrator's message gave the count as 5 of 7; the reasoning role records 4 of 7, the count the not-held list implies. On 5 and 8 the IR at this round's fix commit (2b7627d) already held C233 at first use and C204 before C110; the instance also found no term element for confirmation, which is true. Finding 3 stands for the IR: C25 uses "project-specific term" before C58 defines it. These, and the new defect on the provenance of reworded claims, are fixed in round 4's fix pass.

Decided claims the fixes changed, for the owner: C87 and C143 (the fix discipline ratified on 2026-10-27) and C199 (case 009 change 18) gain the reasoning role as actor and become inferred.

Declined findings for round 4's brief: round 1's 6, 11 and 16; round 2's 6; round 3's 7; each with its reason.

### Round 4, count 5, 2026-10-30

Branch point version and commit: v1.9 as at communication-pipeline branch `branch-point-v1.9-cases-010-011`, its round 4 opening commit. Prose 3,471 words; IR 223 claims; unratified terms 2 (T24, T25). Round 3's confirmation was not yet back when round 4 opened; its line is recorded in round 3's entry when it arrives.

Claims check before the round: 4 changed claims, 0 missing, 0 stale (base: round 3 prose).

Awaiting restatement: none; the referent rule's step-6 fix matched in round 3.

Declined findings carried in the brief: round 1's 6, 11 (the instance did not accept the decline) and 16; round 2's 6; round 3's 7; each with its reason.

Signals script before the round: signal 1 and signal 2 (C104, C41) as before; signals 3 and 4 not fired; round 3 found no contradiction; no line unparsed.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier. Prose 3,471 words by `wordCount`; IR 223 claims; 8 findings, 2.3 per thousand words. Restatement: three mismatches, each attributed by the stranger to its own restatement, each quoting a sentence that carries an IR claim. Contradiction 1 (finding 4), undefined terms 3 (findings 5, 6 and 8, each a term used before its definition); verdict: not readable for RD-4, on the contradiction, the undefined terms and the two step-6 passages.

The stranger's quoted sentences: for C223 and C224, "The exception: an own mismatch does not count when the stranger quotes a prose sentence that carries the IR's claim."; for C194, "A contradiction or undefined-term finding withdrawn by the round's stranger instance at confirmation, on a reason quoting the prose, does not count against the verdict."
Mismatches: C223 (own; relied on C223), C224 (own; relied on C223), C194 (own; relied on C194)

Reading of the exception, adopted by the Orchestrator on 2026-10-30 for both texts: "a prose sentence that carries the IR's claim" is a sentence that carries an IR claim faithfully, whichever claim, because the exception's point is that the prose is not at fault. Under that reading none of the three own mismatches counts by the exception.

Finding of count 5 for the owner: the exception does not say which claim the quoted sentence must carry. One reading requires the contradicted claim; the other, adopted above, accepts any claim the sentence carries faithfully. The two readings gave different results on this text's rounds 2 and 3 and the branch point's round 3. The exception's wording is case 011 change 1's adopted text and is not changed here.

Signals script after the `Mismatches:` line: signal 2 fired on C223 (rounds 1 and 4) and C194 (rounds 3 and 4), with C104 and C41 as before. By passage, the verdict rule drew own mismatches in rounds 1 (C223), 3 (C227) and 4 (C223, C224), and the withdrawal rule in rounds 3 and 4 (C194). Both are step-6 findings: prose findings whatever the attribution, owed a structural fix, and under the override they count against the first condition.

The referent passage (C41, C231, C35) matched again.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1, 2 | own mismatches on C223 and C224: the verdict rule | restatement, step 6 | structural fix: the three conditions become a numbered list, each condition carrying its own qualifiers; the first condition's sentence points at its exception and override, as the branch point's C23 does (C203, reworded); the definitions of restatement mismatch, own mismatch, passage and confirmation stand before the list; `awaiting restatement` |
| 3 | own mismatch on C194: the withdrawal rule | restatement, step 6 | structural fix: C194 split by condition; the contradiction withdrawal (C194) sits in the second condition's item and the undefined-term withdrawal (C235) in the third's; C195 (no withdrawal of a mismatch) sits in the first condition's item; `awaiting restatement` |
| 4 | C1 ("before any prose") against the RD-1 and RD-3 exception (C131) | SP-25 | rephrase C1: "… before any prose of the communication exists, for each text that requires one", linked to Texts that require an IR |
| 5 | "topic claim" used before its definition in the Cluster row | SP-04 | reorder: C31 holds the list, C226 defines the topic claim, C240 "A cluster's list may open with a topic claim." |
| 6 | "unfixed" used before its definition (C202 before C182) | SP-04 | reorder: C182 before C202, in the IR and the prose |
| 7 | "its adjudication" (C102) | SP-03 | rephrase C102: "the amendment's adjudication under Article 8" |
| 8 | "form audit" with the link on Article 9, not on the term (C109) | SP-04 | rephrase: the link on "form audit" |

Queued items applied in the same pass:

- Round 3's finding 3 for the IR: T27 project-specific term, defined at the prose's CK-04 anchor, so C25 uses a term element. Round 3's finding 5: T26 confirmation, status proposed, with C233; unratified terms 3; A5 extended.
- Round 3's new defect on provenance: A6 asks the owner to ratify or strike the new wording of the decided claims count 5 reworded or split. Each such claim's provenance notes its rewording.
- Ask 4 of 2026-10-30: C203 reads as the branch point's C23. The `Meta-review: unparsed` line enters the specification (C236 defines an unparsed line; C237 the line; C238 the return of `pending`; C239 `not indicated` otherwise; C191 reworded), worded as the branch point's rule after its round 4 pass.

Claims after fixes: 230. Prose after fixes: 3,568 words. Claims check after the fixes (base: round 4 prose): 14 changed claims, 0 missing, 0 stale. Round trip: 230 of 230.

Confirmation: 5 of 5 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 3.

The five are findings 4 to 8; findings 1 to 3 are the step-6 fixes, which await round 5's restatement. The three new defects are fixed in round 5's fix pass: N1 (SP-25, "Otherwise the reasoning role writes `Meta-review: not indicated`" lacks C239's condition), N2 (a gap: an accepted deliverable whose review record carries `Meta-review: unparsed` is also a finding of the next form audit) and N3 (the IR's order of E6 and R62 to R64).

Decided claims the fixes changed, for the owner: all are listed in A6. New rule for the owner: the `Meta-review: unparsed` line (C236 to C238).

Declined findings for round 5's brief: round 1's 6, 11 and 16; round 2's 6; round 3's 7; each with its reason. Passages awaiting restatement in round 5: the verdict's conditions (C203, C227, C223, C224, C195) and the withdrawal rule (C194, C235).

### Round 5, count 5, 2026-10-30

Branch point version and commit: v1.9 as at communication-pipeline branch `branch-point-v1.9-cases-010-011`, its round 5 opening commit. Prose 3,568 words; IR 230 claims; unratified terms 3 (T24, T25, T26). Round 4's confirmation was not yet back when round 5 opened; its line is recorded in round 4's entry when it arrives.

Claims check before the round: 14 changed claims, 0 missing, 0 stale (base: round 4 prose).

Awaiting restatement: round 4's two step-6 fixes, the verdict's conditions (C203, C227, C223, C224, C195) and the withdrawal rule (C194, C235). This round's entry states whether the restatement matched on each.

Declined findings carried in the brief: round 1's 6, 11 (the instance did not accept the decline) and 16; round 2's 6; round 3's 7; each with its reason.

Signals script before the round: signal 1 fired on rounds 1 and 3 by fixes not held, without the C13 report; signal 2 fired on C104, C41, C223 and C194, all step-6 findings already taken; signals 3 and 4 not fired (round 4's contradiction, C1 against C131, sat on sentences no earlier fix touched); no line unparsed.

Stranger brief: before round 5 the Orchestrator brought the brief's Readability verdict sentence to the current rule: three conditions, the first with the own-mismatch exception and the recurrence override, the second and third plain. In rounds 1 to 4 that sentence had quoted the round 1 rule. Later rounds' briefs start from the updated round 5 brief.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier, under the brief with the current verdict sentence. Prose 3,568 words by `wordCount`; IR 230 claims; 5 findings, 1.4 per thousand words. Restatement: three mismatches, each attributed by the stranger to its own restatement, each quoting the prose sentence that carries its claim. The restatement gave the verdict without the exception and the override, and applied withdrawal to all three conditions. Contradictions 0, undefined terms 0; verdict: not readable for RD-4, because both mismatch passages are step-6 passages and count under the override.

The quoted sentences, as the round 5 text carries them: for C195, "A restatement mismatch is not withdrawn at confirmation."; for C194 (with C235), "A contradiction finding withdrawn by the round's stranger instance at confirmation, on a reason quoting the prose, does not count against the verdict."; for C227 (with C223 and C224), "The exception: an own mismatch does not count when the stranger quotes a prose sentence that carries the IR's claim."
Mismatches: C195 (own; relied on C195), C194 (own; relied on C194), C227 (own; relied on C223)

Signals script after the `Mismatches:` line: signal 2 fired on C223 (rounds 1, 4 and 5), C194 (rounds 3, 4 and 5), C195 (rounds 1 and 5) and C227 (rounds 3 and 5), with C104 and C41 as before. Both passages awaiting restatement, the verdict's conditions and the withdrawal rule, did not match: round 4's structural fixes did not hold on restatement. The referent passage (C41, C231, C35) matched.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 to 3 | own mismatches on C195, C194 with C235, and C227 with C223 and C224 | restatement, step 6 | second structural fix on both passages: the verdict becomes a table, one row per condition, with the columns "Counts against the verdict" and "Does not count against the verdict"; the exception and the override sit in the first condition's row, each withdrawal in its own condition's row, and C195 in the first row's "counts" column; the claims keep their identifiers, C203, C227 and C195 reworded to the table's cells; `awaiting restatement` |
| 4 | Rendering conditions opens with the input list before the table that is its subject | SP-10 | add C246 first: "The rendering conditions decide, for one IR, who renders its prose and whether the stranger rounds run."; inferred by R66 |
| 5 | "A stranger review runs in rounds until …" names no actor | SP-18 | rephrase C88: "The reasoning role runs a stranger review in rounds until …"; inferred by R65; added to A6 |

This is the second structural fix on each passage. The reasoning role judged the table no worse a reading than the list: each row holds a condition with its qualifiers, so a restatement that takes a condition reads its row.

Queued items applied in the same pass: round 4's N1 (C239 rendered with its condition: "When the text is no subject and no line is unparsed, the reasoning role writes `Meta-review: not indicated`."); N2 (C247, inferred by R67: "A `Meta-review: unparsed` line in the review record of an accepted deliverable is a finding of the next form audit under Article 9."); N3 (E6 after E5; R62 to R64 after R61); defect A, shared with the branch point (C238: "When the unparsed line parses, …"). The branch point's round 5 finding 7 applied here too: the exception reads "a prose sentence that carries an IR claim", the reading adopted on 2026-10-30 (C223).

Findings of count 5 for the owner, from the stranger's open points: the lifecycle does not say how an IR-only document's IR is kept; the text does not say whether an unconfirmed fix stays in the delivered text. The exception's wording now follows the adopted reading, and the exception-reading finding stays on the owner's list with it.

Claims after fixes: 232. Prose after fixes: 3,640 words. Claims check after the fixes (base: round 5 prose): 8 changed claims, 0 missing, 0 stale. Round trip: 232 of 232.

Confirmation: 2 of 2 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 3.

The two are findings 4 and 5; findings 1 to 3 are the step-6 table, awaiting restatement. The three new defects sit on the new table and its neighbours and are fixed in round 6's fix pass, on both texts where the table is shared: N1 (SP-25, the first row's Counts cell stands unqualified against the Does-not-count cell), N2 (a gap, rows 2 and 3 do not say what a withdrawal without a quoted reason does) and N3 (SP-03, the Rendering conditions subject sentence does not cover the IR-only row; two adjacent "decides").

Decided claims the fixes changed, for the owner: C203, C223, C227, C195 and C88, added to A6 where not already listed; new rule C247.

Declined findings for round 6's brief: round 1's 6, 11 and 16; round 2's 6; round 3's 7; each with its reason. Passages awaiting restatement in round 6: the verdict table (C203, C227, C223, C224, C195, C221, C234) and the withdrawal cells (C194, C235).

### Round 6, count 5, 2026-10-30

Branch point version and commit: v1.9 as at communication-pipeline branch `branch-point-v1.9-cases-010-011`, its round 6 opening commit. Prose 3,640 words; IR 232 claims; unratified terms 3 (T24, T25, T26). Round 5's confirmation was not yet back when round 6 opened; its line is recorded in round 5's entry when it arrives.

Claims check before the round: 8 changed claims, 0 missing, 0 stale (base: round 5 prose).

Awaiting restatement: round 5's second structural fixes, the verdict table (C203, C227, C223, C224, C195, C221, C234) and the withdrawal cells (C194, C235). This round's entry states whether the restatement matched on each.

Declined findings carried in the brief: round 1's 6, 11 (the instance did not accept the decline) and 16; round 2's 6; round 3's 7; each with its reason.

Signals script before the round: signals 1 and 2 fire as before; signal 3 not fired; the script's signal 4 check matches the wording of round 5's own signals note, not a finding, so signal 4 is not fired; no line unparsed.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier. Prose 3,640 words by `wordCount`; IR 232 claims; 8 findings, 2.2 per thousand words. Restatement: one mismatch, attributed by the stranger to its own restatement, quoting the sentence that carries C1; no earlier mismatch on that passage. The first condition holds. Contradiction 1 (finding 5), undefined terms 0 (findings 2 and 6 are a missing link and a shortened term); verdict: not readable for RD-4, on the contradiction.
Mismatches: C1 (own; relied on C1)

Signals script after the `Mismatches:` line: C1 stood on no earlier line; signal 2 as before on C104, C41, C223, C194, C195 and C227; no line unparsed.

Awaiting restatement: all three passages matched. The verdict table's first row matched on direction, and the withdrawal cells matched: the second structural fix on each of the two step-6 passages is confirmed by restatement. The referent passage matched again.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | own mismatch on C1 | restatement | no prose defect, under the exception |
| 2 | "proposed" used as a status in the Term row before Provenance defines it | SP-04 | add the link to Provenance at that use |
| 3 | "Later uses of a term … are not linked." names no actor | SP-18 | rephrase C164: "The renderer does not link a later use of a term with a definition site in the unit."; inferred by R70; added to A6 |
| 4 | "A restatement mismatch is never withdrawn at confirmation." names no actor | SP-18 | rephrase C195 in the table: "The round's stranger instance never withdraws a restatement mismatch at confirmation."; inferred by R68; the branch point's cell follows |
| 5 | the delivered text "with the round's fixes applied" against findings marked unfixed | SP-25 | add C248 "An unconfirmed fix's words stay in the delivered prose." and C249 "The unfixed mark records that the readable round's stranger instance did not confirm the fix."; inferred by R71; for the owner with the count 5 findings, since they answer the open point round 5's stranger raised |
| 6 | "subject" alone for "meta-review subject" | SP-04 | rephrase C191, C238 and C239: "meta-review subject"; the branch point's same sentences follow |
| 7 | "communication-pipeline evaluation case 009" repeated in full after its first link | SP-26 | cut to "case 009" in the two later History mentions |
| 8 | "that ended" attaches to the amendment text | SP-03 | rephrase C207: "… amendment text, rounds that ended without a readable verdict." |

Queued items applied in the same pass, shared with the branch point where the text is shared: the first row's Counts cell "… except as the next column states" (C227); rows 2 and 3 "A … finding withdrawn on a reason that does not quote the prose still counts." (C250, C251, inferred by R69); C246 "The rendering conditions settle, for one IR, whether prose is rendered, who renders it and whether the stranger rounds run."; C236 "An unparsed line is … or a claims-check line a round after round 1 lacks."; C224 "on one passage in any two rounds of the text's counts". The specification has no fixed confirmation line, so the branch point's round 6 findings 4 and 5 do not apply here.

Claims after fixes: 236. Prose after fixes: 3,727 words. Claims check after the fixes (base: round 6 prose): 14 changed claims, 0 missing, 0 stale. Round trip: 236 of 236. One new `mtool style` warning, on "Provenance", reads the word in the new link's anchor.

Confirmation: 7 of 7 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 3.

The three new defects are fixed in round 7's fix pass, on both texts where the text is shared: N1 (SP-04, "claims-check line" undefined in the unparsed-line sentence, whose "or" joins two definitions), N2 (the second signal's "in two rounds" against the override's "in any two rounds of the text's counts") and N3 (the next-edit fix of an unfixed finding does not say what it changes, after "An unconfirmed fix's words stay in the delivered prose").

Decided claims the fixes changed, for the owner: C164, C195, C191, C239 and C207, added to A6; new rules C248 to C251.

Declined findings for round 7's brief: round 1's 6, 11 and 16; round 2's 6; round 3's 7; each with its reason. Nothing awaits restatement in round 7.

### Round 7, count 5, 2026-10-30

Branch point version and commit: v1.9 as at communication-pipeline branch `branch-point-v1.9-cases-010-011`, its round 7 opening commit. Prose 3,727 words; IR 236 claims; unratified terms 3 (T24, T25, T26). Round 6's confirmation was not yet back when round 7 opened; its line is recorded in round 6's entry when it arrives.

Claims check before the round: 14 changed claims, 0 missing, 0 stale (base: round 6 prose).

Awaiting restatement: none; round 6 matched on all three passages.

Declined findings carried in the brief: round 1's 6, 11 (the instance did not accept the decline) and 16; round 2's 6; round 3's 7; each with its reason.

Signals script before the round: signals 1 and 2 fire as before; signal 3 not fired; signal 4 fired by reading: round 6's contradiction (finding 5) sat on the readable round's marking rule, C202, which round 4's fix moved after C182; no line unparsed.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier. Prose 3,727 words by `wordCount`; IR 236 claims; 14 findings, 3.8 per thousand words. Restatement: five mismatches, each attributed by the stranger to its own restatement. Finding 1 (C50) ties meta-review signals to convergence with no prose basis and no quote, so it counts. Findings 2 and 3 (C1, C44) quote the sentences that carry them. Findings 4 and 5 (C203 without "that counts"; C194 and C235 without the withdrawals) sit on the verdict passage, which drew mismatches in rounds 1, 3, 4 and 5, so the override counts them. Contradictions 0, undefined term 1; verdict: not readable for RD-4.

The quoted sentences, as the round 7 text carries them: for C1, "The reasoning role writes an intermediate representation (IR) before any prose of the communication exists, for each text that requires one."; for C44, "Each term, claim and cluster, and no other element, ends with one status in square brackets."; for C203, "The first condition: the restatement of the problem, terms and decisions has no mismatch with the IR that counts."; for C194, "A contradiction finding withdrawn by the round's stranger instance at confirmation, on a reason quoting the prose."
Mismatches: C50 (own), C1 (own; relied on C1), C44 (own; relied on C44), C203 (own; relied on C203), C194 (own; relied on C194)

Signals script after the `Mismatches:` line: signal 2 reports C203 (rounds 3 and 7), C194 (rounds 3, 4, 5 and 7), C1 (rounds 6 and 7) and C44 (count 4 round 1, count 5 round 7), with C104, C41, C223, C195 and C227 as before. By the script's reading, C1 and C44 also recur, so under the override they count and step 6 applies to their passages as well. The Orchestrator's reading counted neither. No structural fix is made on C1's or C44's passage in this pass, because the record holds neither misreading; C1's wording changes under finding 6. The question goes to the Orchestrator. The Orchestrator ruled after the round: both count under the rule as written. C1 and C44 are step-6 findings, found by the script after the round; the round 7 verdict, not readable, is unchanged. Their structural fixes are made in round 8's fix pass: C1's scope leads its sentence, since both strangers dropped it; the Provenance section opens with the elements that carry a status, since both strangers gave a status to every element. Both passages then await restatement.

The referent passage matched.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | own mismatch on C50: signals tied to convergence | restatement | counts; no prose defect found: C50 states the unratified-term count as one indicator of convergence and names no signal |
| 2, 3 | own mismatches on C1 and C44, quoted | restatement | see the signals note above |
| 4, 5 | own mismatches on C203 and on C194 with C235: the verdict passage | restatement, step 6 | third structural fix: the verdict gets its own sub-header, "The verdict", under Stranger rounds, and the rest of the section its own, "The count"; nothing else moves; `awaiting restatement`, third fix |
| 6 | "communication" undefined, beside "text" | SP-04 | rephrase C1, C12 and C23: "text" |
| 7, 8 | "bare pronoun" and "bare determiner phrase" used before their lists | SP-04 | reorder: each list first, then its rule (C42 before C41, C163 before C231); C35 stays after C41 |
| 9 | "rounds" in CK-14 unlinked | SP-04 | add the link to Stranger rounds |
| 10 | the Rendering rule header over Stranger rounds and Meta-review | SP-08 | rename: "Rendering and review"; the anchor `rendering-rule`, which the vision document links, kept |
| 11 | "The unfixed mark records …" after the sentence that defines unfixed | SP-26 | cut C249; no claim lost |
| 12 | "its meta-review" | SP-03 | rephrase C106: "that subject's meta-review" |
| 13 | the two form-audit sentences | SP-26 | merge C247 into C109: "A `Meta-review: pending` or `Meta-review: unparsed` line in an accepted deliverable's review record is a finding of the next form audit under Article 9 (audits)." |
| 14 | "Prose written directly is under the style guide's mechanical checks." | SP-18 | rephrase C206: "The author of prose written directly runs the style guide's mechanical checks on it."; inferred by R74 |

Queued items applied in the same pass: round 6's N1 (C236 split; C252 defines the claims-check line; C253 a round after round 1 with no claims-check line counts as unparsed); N2 (C208, "in two rounds of the text's counts"); N3 (C254: "At that edit, the reasoning role revises the unconfirmed words for the next count's confirmation."). The branch point's round 7 finding 6, shared: "The override governs the exception." in the table (C255, inferred by R75).

Finding of count 5 for the owner: the verdict passage has drawn restatement omissions in five rounds (1, 3, 4, 5, 7). A 200-word restatement of a text near 3,700 words compresses a qualified rule; the meta-review should weigh this against the 200-word limit.

Confirmation: 8 of 9 fixes hold. Not held: 9. Declines accepted: 0 of 0. New defects: 8.

The instance (a91d38d881607604a) re-read the prose and the IR. Finding 9 did not hold: the CK-14 link goes to the Stranger rounds heading, which uses "round" without defining it; the link should go to the vocabulary row. Fixes 10 and 14 hold, with residue carried as new defects 1 and 3. The eight new defects: 1, the CK-15 row still says "(Rendering rule)"; 2, the CK-14 link, as not-held 9; 3, "The author of prose written directly" names no defined role; 4, "The override governs the exception." repeats the override; 5, "before a round" names no round; 6, "the next count's confirmation" names an event no sentence describes; 7, the IR heading "### Rendering rule" is stale; 8, C253 cites R62, which does not derive it. Defect 4 is declined: the sentence states precedence, which "always" alone did not, and the branch point carries the same sentence under a finding its round 7 instance confirmed. The re-fix and defects 1 to 3 and 5 to 8 are fixed in round 8's fix pass.

Claims after fixes: 238. Prose after fixes: 3,752 words. Claims check after the fixes (base: round 7 prose): 12 changed claims, 0 missing, 0 stale; C247 and C249 removed. Round trip: 238 of 238.

Decided claims the fixes changed, for the owner: C1, C12, C23, C106, C109 and C206, added to A6; new rules C252 to C255.

Declined findings for round 8's brief: round 1's 6, 11 and 16; round 2's 6; round 3's 7; each with its reason. Passage awaiting restatement in round 8: the verdict section (C203, C227, C223, C224, C255, C195, C221, C194, C250, C234, C235, C251), third fix.

### Round 8, count 5, 2026-10-30

Branch point version and commit: v1.9 as at communication-pipeline branch `branch-point-v1.9-cases-010-011`, its round 8 opening commit. Prose 3,752 words; IR 238 claims; unratified terms 3 (T24, T25, T26). Round 7's confirmation was not yet back when round 8 opened; its line is recorded in round 7's entry when it arrives.

Claims check before the round: 12 changed claims, 0 missing, 0 stale (base: round 7 prose).

Awaiting restatement: round 7's third structural fix, the verdict section under its own sub-header (C203, C227, C223, C224, C255, C195, C221, C194, C250, C234, C235, C251). This round's entry states whether the restatement matched on it. The C1 and C44 recurrences the script reported in round 7 wait for the Orchestrator's reading.

Declined findings carried in the brief: round 1's 6, 11 (the instance did not accept the decline) and 16; round 2's 6; round 3's 7; each with its reason.

Signals script before the round: signals 1 and 2 fire as before, signal 2 now also on C203, C1 and C44; signal 3 not fired; signal 4 fired by reading in round 6; no line unparsed. The text is a meta-review subject at the count's end.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier (aa38f61075323bda0). Prose 3,752 words by `wordCount` (the stranger's estimate: about 4,400); IR 238 claims; 8 findings, 2.1 per thousand words. Restatement: three mismatches, each attributed by the stranger to its own restatement, each quoting the sentence that carries its claim: C44 ("Each term, claim and cluster, and no other element, ends with one status"), the restatement giving every element a status; C104 and C106 (the meta-review subject), the restatement saying the signals trigger a review of the count; C123 (the footprint), the restatement saying the footprint rules govern delivered IRs. The round 8 brief listed no earlier-round passages, so the stranger could not check the override. Contradictions 2 (findings 4 and 5), undefined terms 0; verdict: not readable for RD-4.
Mismatches: C44 (own; relied on C44), C104 (own; relied on C104), C106 (own; relied on C106), C123 (own; relied on C123)

Signals script after the `Mismatches:` line: C44 recurs (count 4 round 1; count 5 rounds 7 and 8), its third recurrence, so it counts under the override and the queued structural fix stands; the first condition fails on it. C104 also recurs (count 4 round 1; count 5 rounds 1 and 8): by the rule as written the meta-review subject passage is a step-6 passage, it counts, and it takes a structural fix in this pass. C106 and C123 stand on no earlier line; their passages join round 9's restatement-match list.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | own mismatch on C44: every element given a status | restatement, step 6 | structural fix from the ruling of 2026-10-30: the Provenance section opens with the element kinds that carry a status, "Three element kinds carry a provenance status: terms, claims and clusters. No other element carries a provenance status.", then the format sentence (C259, C260, C44 reworded); `awaiting restatement` |
| 2 | own mismatch on C104 and C106: the signals read as triggering a review | restatement, step 6 for C104 | structural fix: the ask to the owner (C106) and "The owner may dispatch a meta-review of any text." (C192) move beside the subject sentence (C104), in a paragraph of their own before the `Meta-review:` line rules; `awaiting restatement` |
| 3 | own mismatch on C123: the footprint read as governing delivered IRs | restatement | no prose defect, under the exception; the passage joins round 9's restatement-match list |
| 4 | a cluster renders as one paragraph, but its claims' `part:` fields may differ | SP-25 | add C256, proposed: "A cluster's claims share one `part:` value."; a rule without a check, because no tool runs a changed CK-09; A7 asks the owner |
| 5 | an IR-only document has no report to list proposed terms | SP-25 | add C257, proposed: "When the IR is the deliverable, the IR's own Asks section lists each proposed term for ratification."; evidence E7, the roadmap's and the IR-only record's asks A2; A7 asks the owner |
| 6 | "withdraws" undefined | SP-04 | add C258 at first use: "The round's stranger instance withdraws a finding at confirmation when it says the finding does not hold against the prose as it stands."; inferred by R77 |
| 7 | "disposition" and "declined" undefined | SP-04 | add C261 at first use: "A finding's disposition is the reasoning role's decision on the finding: fixed, or declined with a reason."; inferred by R78; the vocabulary has no disposition row |
| 8 | the final-round marking sentence repeats the recording duty | SP-26 | declined: C199 carries a distinct claim, the mark at the limit, in the review record, where no text is delivered (case 009 change 18) |

Round 7's carried items applied in the same pass: fix 9 re-fixed (the CK-14 link goes to the vocabulary's round row); new defects 1 (CK-15 "(Rendering and review)"), 3 (C206: "The reasoning role runs the style guide's mechanical checks on prose it writes directly."), 5 (C252: "… records the claims check run before each round from round 2."), 6 (C254: "… revises the unconfirmed words, which the next count's rounds then review."), 7 (the IR heading "### Rendering and review"), 8 (C253 cites R76, which derives it). Defect 4 stays declined and is carried. The ruling's structural fix on C1: "For each text that requires one, the reasoning role writes an intermediate representation (IR) before any prose of the text exists."; `awaiting restatement`.

Confirmation: 4 of 5 fixes hold. Not held: 4. Declines accepted: 1 of 1. New defects: 7.

The instance (aa38f61075323bda0) re-read the prose in full and the IR's lines 1 to 140, and quoted C206, C252 and C254 from its earlier read. The five confirmable fixes are rows 3, 4, 5, 6 and 7; rows 1 and 2 are step-6 fixes, not confirmed by the instance. Row 4 did not hold: claims without a `part:` value still split, by provenance, under the parts for RD-1 and RD-2. Row 5 holds with residue: the Term row's first sentence lacks its condition. On row 2 the instance reported the meta-review subject sentences inside the signal-list paragraph; the committed file at e121dd7 already holds them in a paragraph of their own, so the instance read an older text. New defects 4 to 6 report C206, C252 and C254 as disagreeing with the prose; the committed IR carries the prose's wording for all three, so these too come from a stale read. Row 4, row 5's residue and new defects 1 to 7 are taken in round 9's fix pass.

Claims after fixes: 244. Prose after fixes: 3,836 words. Claims check after the fixes (base: round 8 prose): 11 changed claims, 0 missing, 0 stale. Round trip: 244 of 244.

Decided claims the fixes changed, for the owner: C1, C44 with C259 and C260, added to A6; new proposed rules C256 and C257 in A7; new inferred claims C258 and C261.

Declined findings for round 9's brief: round 1's 6, 11 and 16; round 2's 6; round 3's 7; round 7's new defect 4; round 8's 8; each with its reason. Passages awaiting restatement in round 9: the verdict section; the C1 passage; the Provenance opening (C259, C260, C44); the meta-review subject paragraph (C104, C106, C192); the footprint passage (C123).

### Round 9, count 5, 2026-10-30

Branch point version and commit: v1.9 as at communication-pipeline branch `branch-point-v1.9-cases-010-011`, its round 8 fix commit. Prose 3,836 words; IR 244 claims; unratified terms 3 (T24, T25, T26). Round 8's confirmation was not yet back when round 9 opened; its line is recorded in round 8's entry when it arrives.

Claims check before the round: 11 changed claims, 0 missing, 0 stale (base: round 8 prose).

Awaiting restatement: the verdict section (third fix, round 7); the C1 passage (round 8); the Provenance opening, C259, C260 and C44 (round 8); the meta-review subject paragraph, C104, C106 and C192 (round 8); the footprint passage, C123, first occurrence, listed for its match. This round's entry states whether the restatement matched on each.

Declined findings carried in the brief: round 1's 6, 11 (the instance did not accept the decline) and 16; round 2's 6; round 3's 7; round 7's new defect 4; round 8's 8; each with its reason.

Signals script before the round: signal 1 fires as before; signal 2 on C104, C41, C223, C194, C195, C227, C203, C1 and C44; signal 3 not fired; signal 4 fired by reading in round 6; no line unparsed. The text is a meta-review subject at the count's end.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier (a2127801c8f655ec2). Prose 3,836 words by `wordCount` (the stranger's estimate: about 4,500, by hand); IR 244 claims; 4 findings, 1.0 per thousand words. Restatement: one mismatch, on C132, attributed by the stranger to its own restatement, which dropped "register fact"; it quotes both sentences of Texts that require an IR that carry C132: "A report to RD-1 or RD-3 that introduces no term, records no decision and states no register fact may be written as prose directly." and "A term, a decision or a register fact requires the IR." Contradiction 1 (finding 3), undefined term 1 (finding 2); verdict: not readable for RD-4.
Mismatches: C132 (own; relied on C132)

The two readings of finding 1. The stranger counted the mismatch: it read the listed Purpose passage (C1) as covering the when condition through "that requires one", so the override applied. The Orchestrator's ruling: the mismatch sits on C132's passage, its first occurrence; the quoted sentences carry C132 faithfully, so the exception applies and it does not count. The stranger restated C1 itself without mismatch. The verdict is not readable on findings 2 and 3 under either reading. C132's passage joins round 10's restatement-match list.

Restatement matches on the passages awaiting restatement: the verdict section (third fix, round 7) matched; the C1 passage matched; the Provenance opening (C259, C260, C44) matched; the meta-review subject paragraph (C104, C106, C192) matched; the footprint comparison (C123) matched. The referent passage (C35, C41, C33) matched. Each mark clears.

Row 2 of round 8, checked against the committed file: the instance was right. The subject sentences (C104, C106, C192) followed the signal list in one paragraph; round 8's fix had separated them only from the `Meta-review:` line rules. The round 8 entry's stale-read note on row 2 is wrong. This pass breaks the paragraph after the signals; no word changes.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | own mismatch on C132: "register fact" dropped, quoted | restatement | does not count, under the exception (the Orchestrator's ruling); no prose defect; the passage joins round 10's restatement-match list |
| 2 | "governed document" undefined, Provenance table, decided row | SP-04 | the methodology vocabulary has no row for it; rephrase C46: "quoted from a document the human owner ratified"; no term added |
| 3 | the withdrawal sentence lets the instance withdraw a restatement mismatch, which the first row forbids | SP-25 | rephrase C258, with round 8's new defect 2: "At confirmation, the round's stranger instance withdraws a finding other than a restatement mismatch by saying the finding no longer applies to the prose."; R77 cites C195 |
| 4 | "after delivery" repeats "delivered" | SP-26 | cut: C161 reads "The reasoning role does not edit the IR of a delivered report." |

Round 8's carried items applied in the same pass. Row 4 re-fixed: C256 moves to the rendering parts and reads "The renderer renders a cluster whose claims fall under different parts as one paragraph per part." (proposed, A7). Row 5's residue: C152 reads "When a report delivers the text, the reasoning role lists each proposed term for ratification in that report." New defect 1: the Provenance opening is two sentences; C260 merges into C259, "Terms, claims and clusters, and no other element, carry a provenance status."; the merge is listed in A6. New defect 2: taken in finding 3's wording. New defect 3: C262 added, "A confirmed or unfixed mark is not a disposition: the mark records whether the round's stranger instance confirmed a fix." (inferred, R79). New defect 7: C1 reads "For each text that requires an intermediate representation (IR), the reasoning role writes the IR before any prose of the text exists.", the link to Texts that require an IR kept. A7 also asks whether a finding's disposition (C261) keeps its name beside the communication-pipeline's dispositions D0 to D3.

New defects 4 to 6 of round 8 are declined as stale reads. The committed IR already carries the prose's wording: C206, "The reasoning role runs the style guide's mechanical checks on prose it writes directly."; C252, "A claims-check line is the review-record line in which the reasoning role records the claims check run before each round from round 2."; C254, "At that edit, the reasoning role revises the unconfirmed words, which the next count's rounds then review."

Confirmation: 3 of 3 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 3.

The instance (a2127801c8f655ec2) re-read the prose and the IR. The confirmable fixes are rows 2, 3 and 4. Row 1 has no text fix; the instance does not dispute the ruling and notes that the mismatch sits on C131 and C132, with both carriers quoted. The three new defects: 1, SP-25, C256 against C174 in Rendering and review, a cluster rendered as one paragraph and as one paragraph per part; 2, SP-01, the Provenance opening's first sentence joins the positive claim and the negative claim, which the merge of C260 into C259 made one; 3, SP-05 and SP-04, A7 names "dispositions D0 to D3" with no name or link. All three are taken in round 10's fix pass: C174 gains a clause naming C256's rule as its exception, and C174 joins A6; the Provenance opening splits into two sentences again, C259 and C260 restored, and A6 notes that the merge was reversed; A7 names the communication-pipeline's branch-point dispositions without the identifiers.

Claims after fixes: 244 (C260 removed, C262 added). Prose after fixes: 3,864 words. Claims check after the fixes (base: round 9 prose): 8 changed claims, 0 missing, 0 stale; C260 removed. Round trip: 244 of 244. IR check: 0 violations, 0 warnings. Lint and style warnings: 27 and 50, as before the pass.

Decided claims the fixes changed, for the owner: C1 again, C259 with C260 merged into it, and C46, added to A6. Proposed C256 reworded in A7.

Declined findings for round 10's brief: round 1's 6, 11 and 16; round 2's 6; round 3's 7; round 7's new defect 4; round 8's 8 and new defects 4 to 6; each with its reason. Passages awaiting restatement in round 10: the verdict section; the C1 sentence in its new wording; the Provenance opening in its two-sentence form; C132's passage, first occurrence, listed for its match.

### Round 10, count 5, 2026-10-30

Round 10 is the limit. Branch point version and commit: v1.9 as at communication-pipeline branch `branch-point-v1.9-cases-010-011`, its closing commit a0f30be. Prose 3,864 words; IR 244 claims; unratified terms 3 (T24, T25, T26). Round 9's confirmation was not yet back when round 10 opened; its line is recorded in round 9's entry when it arrives.

Claims check before the round: 8 changed claims, 0 missing, 0 stale (base: round 9 prose).

Awaiting restatement: the verdict section (third fix, round 7); the C1 sentence in its round 9 wording; the Provenance opening in its two-sentence form (C259, C44); C132's passage, first occurrence, listed for its match. This round's entry states whether the restatement matched on each.

Declined findings carried in the brief: round 1's 6, 11 (the instance did not accept the decline) and 16; round 2's 6; round 3's 7; round 7's new defect 4; round 8's 8 and new defects 4 to 6; each with its reason.

At the limit, the reasoning role fixes round 10's findings in the IR and then in the prose, and round 10's stranger instance confirms each fix before the owner's decision, other than a step-6 fix. A step-6 fix stays awaiting restatement and counts as unfixed.

Signals script before the round: signal 1 fires as before; signal 2 as before, with no new claim (C132 stands on one line); signal 3 not fired (15.72 words per claim against round 1's 15.59); signal 4 fired by reading again: round 9's contradiction (finding 3) sat on C258, which round 8's fix added; no line unparsed. The text is a meta-review subject at the count's end.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier (a730555ad1a871eb3). Prose 3,864 words by `wordCount` (the stranger's estimate: about 4,500 to 5,000, by hand); IR 244 claims; 2 findings, 0.5 per thousand words. Restatement: no mismatch. The stranger noted one omission of its own, that a readable verdict also stops a count, and quoted the sentence that carries C88. Contradiction 1 (finding 1), undefined terms 0; verdict: not readable for RD-4, on the contradiction alone.
Mismatches: none

Restatement matches on the passages awaiting restatement: the verdict section (third fix, round 7) matched; the C1 sentence in its round 9 wording matched; the Provenance opening in its two-sentence form (C259, C44) matched; C132's passage matched. The referent passage matched. Each mark clears. The stranger also found C206, C252 and C254 matching the prose, as their round 8 declines stated. It raised no declined finding.

Side effect: before reading, the instance made one call to a docs guide menu outside the brief's two files. The call read no file and created nothing.

| # | Finding (shortened) | Kind | Disposition |
|---|---|---|---|
| 1 | C174 against C256: one paragraph per cluster, and one paragraph per part | SP-25 | rephrase C174, as queued from round 9's confirmation: "The paraphraser renders one cluster as one paragraph in the cluster's order, except a cluster whose claims fall under different parts."; C174 joins A6, and A7 names it as C256's exception |
| 2 | the first-condition cell's "never withdraws a restatement mismatch" against the withdrawal sentence (C195 against C258) | SP-26 | declined: the cell is C195's only prose carrier, and the communication-pipeline branch point carries the same verdict table, which stays identical; C258 states which findings a withdrawal covers, and C195 states the first condition's rule. A fold into C258 under 25 words would join two claims in one sentence |

The Orchestrator accepted the decline of finding 2 with its reason. C195's provenance is inferred, by R68, not decided as the Orchestrator's message stated; the decline does not rest on it.

Round 9's confirmation defects applied in the same pass: defect 1 is finding 1 above. Defect 2: the Provenance opening splits into two sentences again, "Terms, claims and clusters carry a provenance status. No other element carries a provenance status."; C260 is restored, and A6 notes that the merge was reversed. Defect 3: A7 names "the communication-pipeline's branch-point dispositions" without the identifiers.

Claims after fixes: 245 (C260 restored). Prose after fixes: 3,876 words. Claims check after the fixes (base: round 10 prose): 3 changed claims, 0 missing, 0 stale. Round trip: 245 of 245. IR check: 0 violations, 0 warnings. Lint and style warnings: 27 and 50, as before the pass. Footprint: declared 5, changed 5, surprises 0, misses 0.

Decided claims the fixes changed, for the owner: C174 and C259 with C260, added to A6.

Confirmation: 1 of 1 fixes hold. Not held: none. Declines accepted: 1 of 1. New defects: 1.

The instance (a730555ad1a871eb3) re-read the prose and the IR in full. Finding 1's fix holds; finding 2's decline is accepted. The new defect sits in the IR's asks only: A7's "the communication-pipeline's branch-point dispositions" names a term with no link (SP-04). The instance also noted, not counting it, that A6's "whose exception names the cluster C256 splits" overstates what C174 says. Both are applied after confirmation, in the closing commit, and touch no claim and no prose: A7 links the communication-pipeline vocabulary's disposition row, "the branch point's output for one IR"; A6 reads "C174, whose exception describes the clusters C256 splits."

Final-round marks (the limit): finding 1, confirmed; finding 2, declined, the decline accepted by the instance. No step-6 fix was pending, so no fix stays awaiting restatement and no finding is unfixed.

### Verdict, count 5

The limit was reached at round 10 of count 5, on 2026-10-30. The final round's verdict: not readable for RD-4, on one contradiction (finding 1, C174 against C256), whose fix the instance confirmed. Under the limit rule the reasoning role does not deliver the text before the owner's decision.

| Round | Findings per 1,000 words | Contradictions |
|---|---|---|
| 1 | 5.9 | 2 |
| 2 | 1.8 | 1 |
| 3 | 2.6 | 0 |
| 4 | 2.3 | 1 |
| 5 | 1.4 | 0 |
| 6 | 2.2 | 1 |
| 7 | 3.8 | 0 |
| 8 | 2.1 | 2 |
| 9 | 1.0 | 1 |
| 10 | 0.5 | 1 |

Findings in all: 84 across ten rounds. Prose 3,368 words at round 1 and 3,891 at close (3,876 after round 10's fixes; the closing Status line adds 15). IR 216 claims at round 1 and 245 at close. Restatement mismatches: none in round 10; every passage that awaited restatement matched by round 10.

Meta-review: delivered (signals 1, 2 and 4; pending at the close on 2026-10-30): [evaluation case 012](https://github.com/majodali/communication-pipeline/blob/main/eval/cases/012-meta-review-branch-point-v1.9-and-ir-spec-count-5-2026-10-30.md). Signals checked at the end of count 5 by `scripts/signals.mjs` (reading the last count) and by reading: first, fired: fixes not held at confirmation in rounds 1, 3, 7 and 8, and the claims check reported a stale claim before rounds 1 and 2; second, fired: restatement mismatches recurred on the passages of C44, C104, C41, C223, C195, C227, C203, C194 and C1, each given a structural fix that a later round matched; no declined finding was raised again; third, not fired: words per IR claim 15.59 at round 1 and 15.84 at round 10, 2 percent; fourth, fired by reading: the contradictions of rounds 6, 9 and 10 sat on passages an earlier round's fix touched (C202, C258, C256). The count also reached the limit, so the text is a meta-review subject on two grounds. The reasoning role asks the owner, in the report on this count, to dispatch the meta-review.

The owner's decision at the limit: deliver, rework or withdraw the text. Open items for that decision, in one list:

1. A5: ratify or strike the terms passage (T24), topic claim (T25) and confirmation (T26).
2. A6: ratify or strike the new wording of the decided claims count 5 reworded, split or merged: C1; C13; C31 and C240; C41 and C231; C58 and C232; C87; C88; C102; C106; C109; C110; C143; C161; C164; C191 and C239; C194 and C235; C195; C199; C203; C205; C206; C207; C208; C221 and C234; C223; C224; C227; C229; C12; C23; C44 with C259 and C260 (merged in round 9, split again in round 10); C46; C174.
3. A6: ratify or strike the new rules: the `Meta-review: unparsed` line (C236 to C238) and its form-audit finding, merged into C109; a withdrawal without a quoted reason still counts (C250, C251); an unconfirmed fix's words stay in the delivered prose (C248) and are revised at the next edit (C254); the claims-check line (C252, C253); the override governs the exception (C255).
4. A7: ratify or strike C256, a cluster whose claims fall under different parts renders as one paragraph per part, the exception C174 now describes; striking C256 also strikes C174's clause.
5. A7: ratify or strike C257, an IR-only deliverable's own Asks section lists each proposed term for ratification.
6. A7: decide whether a finding's disposition, fixed or declined (C261), keeps its name beside the communication-pipeline's disposition, the branch point's output for one IR.
7. Three gaps for IR-only documents, carried unchanged from the edit of 2026-10-30: the render map omits C217 to C219; C13's Status values omit `delivered IR-only`; the prose's "another is whether the owner designated the document IR-only" has no claim.
8. The finding of count 5 recorded in round 7: the verdict passage drew restatement omissions in five rounds; the meta-review should weigh the 200-word restatement limit against a text near 3,900 words.

The owner's decision, 2026-10-30: count 5 accepted and delivered (methodology PR #69 merged). The items above, marked:

1. A5: granted. The terms passage (T24), topic claim (T25) and confirmation (T26) ratified, with withdrawal (T28); vocabulary rows added.
2. A6, the reworded decided claims: granted; the claims carry decided provenance from 2026-10-30.
3. A6, the new rules: granted.
4. A7, C256: granted; C174's clause stands.
5. A7, C257: granted.
6. A7, the name: "disposition" of a finding renamed "decision on a finding" (T29) and ratified under that name; C95, C261 and C262 and the vocabulary's review-record row reworded to it.
7. The three IR-only gaps: none remained at acceptance. Count 5's rounds had closed all three: C13 holds `delivered IR-only`; C229 carries the owner-input sentence; the render map maps C217 to C219. The list carried them from the count's opening note without re-checking.
8. Passed to the meta-review, which the owner dispatched with the branch point's as one task.

Meta-review: delivered (signals 1, 2 and 4): [evaluation case 012](https://github.com/majodali/communication-pipeline/blob/main/eval/cases/012-meta-review-branch-point-v1.9-and-ir-spec-count-5-2026-10-30.md), 2026-10-30.

## Count 6, 2026-10-30: evaluation case 012

Inputs: the owner's adoption on 2026-10-30 of communication-pipeline evaluation case 012 (all fifteen changes adopted as recommended; terms by the default). Eleven adopted changes amend this specification: changes 1, 2, 4 to 9, 11, 13 and 14. Change 3 is no change; change 10 is the branch point's; change 12 is the signals script's; change 15 is the evaluation corpus README's. Reader RD-4. Disposition D3 (Normative: yes): the reasoning role rendered the amended passages from the IR. Text reviewed: `docs/intermediate-representation.md` whole; the IR covers the whole text.

Branch point version and commit the count runs under: v1.10, communication-pipeline commit 387dc43 on branch `branch-point-v1.10-case-012`, the changes the owner adopted before this count. The pipeline's own rounds on v1.10 run in parallel.

Changes to the IR. Each claim that renders a case 012 change is proposed, with the change number as its source, under ask A8. C203 and C227 reworded: every restatement mismatch counts. C222 (own mismatch), C223 (the exception), C224 (the override) and C255 (the override governs the exception) struck, with relations R51, R52 and R75. C263 and C264 added, the omission, with C265 inferred by R80. C266 to C268 added, the one-sentence restatement of each listed passage. C269 to C275 added: the fix pass, the claims check after it, the fix commit read in full, the new defect and the next round's opening. C276 to C278 added, a new defect at the final confirmation. C279 to C283 added in the fix rules: no new rule in a fix; a reworded decided claim keeps its source. C189 (the third signal) struck, with R36 and R38; C284 and C288 added; C105 reads "the signals". C252 and C253 read the claims-check line after a fix pass. C285 and C286 added to the History. R55 and R56 retargeted from C224 to C208 and C228. Terms T30 to T35 added; T23 points to the pipeline's vocabulary row. 245 claims before the count's edit; 265 after.

Not changed: the own-mismatch vocabulary row. Neither text uses the term outside its history after count 6; ask A9 asks the owner to strike or keep it. The vocabulary row *meta-review signal* now reads three conditions.

Sentences over 25 words before round 1: 2, the Status line (54 words, `mtool style`) and the Reader paragraph's assumed-knowledge sentence (26 words). Both are resolved: each sentence of the Status line is under 25 words, and the assumed-knowledge sentence drops "including its Readers table", which the Reader line's reader catalog link already carries. At round 1: 0.

Lint before round 1: IR checks 0 violations, 0 warnings.

### Curve, count 6

| Round | Prose words | IR claims | Findings | Per 1,000 words | Verdict |
|---|---|---|---|---|---|
| 1 | 4,129 | 265 | 8 | 1.9 | not readable (two mismatches, both on step-6 passages; contradictions 0; undefined terms 0) |

### Round 1, count 6, 2026-10-30

Branch point version and commit: v1.10 at communication-pipeline commit 387dc43. Prose 4,129 words (whitespace-separated words, comments stripped, by `wordCount` in the communication-pipeline's `scripts/ir.mjs`); IR 265 claims; unratified terms 0.

Claims check: none before round 1; under case 012 change 13 the check runs after each fix pass. The edit's claims check against main: 30 changed claims, 0 missing, 0 stale; C189, C222, C223, C224 and C255 removed.

Passages awaiting restatement: none; every passage that awaited restatement in count 5 matched by its round 10.

Declined findings carried in the brief from count 5, where the text under them stands: round 1's 6, 11 and 16; round 2's 6; round 3's 7; round 8's 8; round 10's 2, its reason restated without the shared table, which v1.10 removes from the branch point. Each with its reason. Not carried: round 7's new defect 4, because "The override governs the exception." is struck; round 8's new defects 4 to 6, stale reads with no text under them.

Signals script before the round: no round of count 6 recorded yet; nothing to read.

Stranger model: claude-haiku-5-5, a fresh instance at the frugal tier (ad9b27f6af3fa271f). Prose 4,129 words by `wordCount` (the stranger's estimate: about 4,500, by hand); IR 265 claims; 8 findings, 1.9 per thousand words. Restatement: two mismatches, each counting under the first condition as count 6 reads it. Listed passages: none. Omissions noticed: 9, by topic, not counted: the rendering-conditions rows; CK-01 to CK-16; the withdrawal rules for contradictions and undefined terms; the review record and the claims-check line; the unparsed-line rules and the `Meta-review:` line values; the footprint comparison; the IR-only exemption from CK-14; the delivery and lifecycle rules; the History. Contradictions 0, undefined terms 0 (two terms defined only after first use, findings 5 and 6); verdict: not readable for RD-4.

The quoted sentences: for C260, "Terms, claims and clusters carry a provenance status. No other element carries a provenance status."; the restatement gave every element kind a status. For C104 with C106, "A text is a meta-review subject when its count reaches the limit or its review record shows a meta-review signal." and "The reasoning role asks the owner ... to dispatch that subject's meta-review."; the restatement had the signals trigger the meta-review.
Mismatches: C260 (relied on C259), C104 (relied on C106)

Signals script after the `Mismatches:` line: signal 2 fires on C104 (count 4 round 1; count 5 rounds 1 and 8; count 6 round 1) and C106 (count 5 round 8; count 6 round 1). The Provenance opening recurs by reading: its earlier mismatches stand on C44 (count 4 round 1; count 5 rounds 7 and 8), and this round's entry names C260, a claim of the same passage. Both passages are step-6 passages again.

For the ruleset review: the Provenance opening and the meta-review subject passage drew restatement mismatches in counts 4, 5 and 6, with structural fixes between the counts. Count 5's fixes, a two-sentence Provenance opening and the subject sentences in their own paragraph, matched in count 5's rounds 9 and 10 and did not hold against this count's fresh reader.

| # | Finding (shortened) | Kind | Decision |
|---|---|---|---|
| 1 | mismatch on C260: every element kind given a status | restatement, step 6 | structural fix: the Element kinds table gains a Provenance status column, a cell per kind; C259 and C260 split per kind (C259, C292, C293; C260, C294, C295); the Provenance opening keeps C44 only; `awaiting restatement` |
| 2 | mismatch on C104 with C106: the signals read as triggering the meta-review | restatement, step 6 | structural fix: the Meta-review section takes three sub-headings; the first, "Who dispatches a meta-review", opens "The owner dispatches a meta-review." (C289, inferred by R82), then C104 ("A text becomes a meta-review subject when ..."), C106 and C192; the signals and the `Meta-review:` line follow under their own sub-headings; `awaiting restatement` |
| 3 | "in the unit" repeats the scope | SP-26 | cut from C164 |
| 4 | "A term the IR introduces is listed under Terms introduced" names no actor | SP-18 | rephrase C153: "When a report delivers the text, the reasoning role lists each term the IR introduces under *Terms introduced* in that report." |
| 5 | "the owner's adopted changes" undefined | SP-04 | rephrase C279: "the changes the owner adopted for the count", linked to the communication-pipeline evaluation corpus's Meta-review records section |
| 6 | "stranger instance" used before its definition | SP-04 | add C290 at first use: "The round's stranger instance is the stranger the reasoning role dispatched for the round." (inferred, R83) |
| 7 | the header "The count" holds rounds, the limit, the record and rework | SP-08 | rename "Rounds, the limit and rework"; the anchor `the-count` kept |
| 8 | the next-edit sentence joins a duty and the next count's review | SP-01 | split C254; C291 added |

The instance's two uncounted observations, fixed in the same pass: C253 reads "The signals script reports a round with a fix pass and no claims-check line as unparsed.", so the definition of an unparsed line holds; R73 drops the round-1 exemption that case 012 change 13 struck.

Claims after fixes: 272. Prose after fixes: 4,198 words. Claims check after the fixes (base: round 1 prose): 15 changed claims, 0 missing, 0 stale. Round trip: 272 of 272. IR check: 0 violations, 0 warnings.

Decided claims the fixes reworded, for the owner's list at the count's close: C259 and C260 (split per kind), C104, C164, C153, C254 (split, with C291).

Confirmation: 6 of 6 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 3.

The instance (ad9b27f6af3fa271f) read both files in full at fix commit 3e720f4. The confirmable fixes are rows 3 to 8; rows 1 and 2 are step-6 fixes, not confirmed by the instance. The three new defects and one uncounted observation, fixed IR first before round 2 opens (case 012 change 6):

- N1 (SP-25, the `Meta-review:` line): a round with no claims-check line has no line to name. C237 split: "While a line is unparsed, the reasoning role writes `Meta-review: unparsed` in place of `pending` or `not indicated`." and C296, "The `Meta-review: unparsed` line names the unparsed line, or the round when the round has no claims-check line." (proposed, case 012 change 13). The fix specifies change 13's rule and adds no rule.
- N2 (SP-26, "Who dispatches a meta-review"): the unqualified sentence "The owner dispatches a meta-review." cut, with C289 and R82. The structural fix over-reached and is trimmed; the section opens with the subject rule (C104), then C106 and C192, each stated once. The passage stays `awaiting restatement`.
- N3 (SP-26, the presence rule in the table and the Provenance sentence): the table cells keep the presence rule; C44 reworded to the form only, "The status is the last thing in the element, in square brackets." The passage stays `awaiting restatement`.
- R76 read "a round after round 1"; it now reads the fix-pass rule of case 012 change 13.

Claims check after the confirmation's fixes (base: the round 1 fix pass's prose): 3 changed claims, 0 missing, 0 stale; C289 removed. Claims: 272. Prose: 4,208 words. Round trip: 272 of 272.

Decided claims reworded after confirmation, for the owner's list at the count's close: C44, C237 (split, with C296).

### Round 2, count 6, 2026-10-30

Branch point version and commit: v1.10 at communication-pipeline commit 387dc43. Round 2 reads the text at this round's opening commit, named in the brief. Prose 4,208 words; IR 272 claims; unratified terms 0.

Passages awaiting restatement, listed in the brief for a one-sentence restatement each (case 012 change 4): the Element kinds table's provenance column with the Provenance opening (C259, C292 to C295, C260, C44), round 1's step-6 fix; the "Who dispatches a meta-review" passage (C104, C106, C192), round 1's step-6 fix as trimmed after confirmation.

Declined findings carried in the brief from count 5: round 1's 6, 11 and 16; round 2's 6; round 3's 7; round 8's 8; round 10's 2. Each with its reason.

Forms added to the brief: none.

Signals script before the round: signal 2 fires on C104 and C106, as recorded in round 1; no line unparsed.
