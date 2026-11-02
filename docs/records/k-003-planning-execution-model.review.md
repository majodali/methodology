# Review record: K-003 takes a declared planning/execution model as its referent

Reader of the reviewed text: RD-4 (a fresh agent session). Reviewer:
a stranger, a fresh instance per round, reading only the files named
in its brief. Rounds until readable, limit ten, under the
[intermediate representation specification](../intermediate-representation.md#stranger-rounds)
as it stands on `main`. Text reviewed: K-003 (the Backlog is the
single source of progress truth) in
[`docs/rules/knowledge.md`](../rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth),
the whole rule with its header, rendered by the reasoning role from
[its IR](k-003-planning-execution-model.ir.md) (43 claims, 17 terms,
6 relations). Every fix is made in the IR first and the prose is
re-rendered or edited to match.

## Count 1, 2026-10-30: the K-003 amendment carried from project-orchestrator

Inputs: the project-orchestrator proposal "A declared planning/execution model is the source of progress truth" and its IR (93 claims, 17 terms), at project-orchestrator commit `25e92e8`, approved for carrying by the owner at node P3-N007's verifying gate on 2026-10-30 (crossing commit `1b9e207`); the owner's decision of 2026-10-30 that the proposal lands in this repository as a methodology change, by pull request. Reader RD-4. Disposition D3 (Normative: yes): the reasoning role rendered the amended rule, the two vocabulary rows, the Referent row's second sense and the release-register entry from the IR. The stranger reads the amended K-003 and the IR. The vocabulary rows and the release-register entry carry the IR's other claims, mapped in the render map after K-003.

Branch point version and commit the count runs under: v1.9, the version the owner accepted on 2026-10-30, at communication-pipeline `main`, commit `d1c5b55`. The specification's count 6, on branch `ir-spec-count-6-case-012`, is changing the rounds; this count runs under `main`'s rules unless the Orchestrator says otherwise.

Quote re-check (the P3-N007 plan's condition before the amendment is applied): the proposal's quote of K-003, taken at v1.6.0, commit `3e34829`, was compared on 2026-10-30 with K-003 at this repository's `main`, commit `e049bc6`, from the rule's heading to the next rule's heading. The two are byte-identical. No drift. The vocabulary row *planning/execution model* is unchanged since commit `350f75f`.

Lint before round 1:

- IR checks (`mtool ir check`): 0 violations, 0 warnings, unratified terms 0.
- Round trip: 43 of 43 claims mapped; the render map follows K-003.
- Claims check, against an empty base, over K-003, the vocabulary rows and the release-register entry together: every claim but one has a carrying sentence above the overlap floor. The exception is C24, the PR field. Its sentence, "this amendment's PR", holds no content word the script counts.
- `mtool style` on K-003: 0 violations. The warnings fall on fixed forms: the rule-header em-dash, the header lines read as one sentence, and the Protects em-dash of Article 5's form. One falls on the decided referent clause's semicolon. Two are stem matches: "Type" in "custom document types" and "Rendering" in "rendered".
- Sentences over 25 words in the text under review: 2. The first is the header, a fielded form with no sentence breaks, at 130 words. The second is the appended sentence, at 29 words. The owner's gate decision of 2026-10-30 keeps that sentence whole ([gate record](https://github.com/majodali/project-orchestrator/blob/25e92e8ef541e0929e7e447f582edc15d3ec7629/docs/plans/p3-n007-type-declared-amendment-drafted.md#gate-record-2026-10-30-at-verifying)). Neither sentence is shortened before round 1. The Orchestrator's report asks the owner to confirm.

Changes to K-003 beyond the proposal's replacement text, each in the IR:

- The Motivated-by line names the proposal and the owner's approval at the gate (C6, proposed).
- The Cites line names Article 7 (C7, proposed) and carries the declaration form (C8 to C11, decided).
- A Protects line names provenance (C12, proposed).
- The statement's words are the proposal's. Links were added at first use to Register, Workflow, referent and renderings. The link on planning/execution model moved to its first use, in the Cites line.

### Curve, count 1

| Round | Prose words | IR claims | Findings | Per 1,000 words | Verdict |
|---|---|---|---|---|---|
| 1 | 261 | 43 | 8 | 30.7 | not readable (one own mismatch on C8 and C9, quoted, not counting; contradiction 1; undefined terms 2) |
| 2 | 268 | 43 | 5 | 18.7 | not readable (one own mismatch on C2 with T7, quoted, not counting; contradictions 2; undefined term 1) |
| 3 | 278 | 44 | 2 | 7.2 | not readable (one own mismatch on C10, the Cites passage's second in two rounds, counting under the override; contradictions 0; undefined term 1) |
| 4 | 251 | 44 | 1 | 4.0 | readable (restatement matched; contradictions 0; the undefined-term finding withdrawn at confirmation on a reason quoting the prose) |

### Round 1, count 1, 2026-10-30

Brief: `k003-r1-brief.md` in the reasoning role's scratchpad, naming commit `0ba6aa9`, dispatched by the Orchestrator. Stranger: instance `ace605047a865643a`, a fresh instance, at commit `0ba6aa9`. Prose 261 words (whitespace-separated words of K-003 from its heading to the next rule's heading, the render map stripped, by `wordCount` in the communication-pipeline's `scripts/ir.mjs`; the stranger's count: about 257); IR 43 claims; 8 findings, 30.7 per thousand words. Restatement: one mismatch, on C8 and C9, attributed by the stranger to its own restatement, with a quoted prose sentence that carries C8. Contradiction 1 (finding 7), undefined terms 2 (findings 2 and 3); verdict: not readable for RD-4. Fixed 3; declined 4; finding 1 needs no fix under the exception.

Mismatches: C8 (own; relied on C8), C9 (own; relied on C8)

The quoted sentence is the Cites line's declaration clause, which carries C8. The quote's exact words are in the stranger's report, which the Orchestrator holds. Under the first condition's exception the own mismatch does not count. Signals script after the `Mismatches:` line: no signal fired; C8 and C9 stand on no earlier line.

Readability note, recorded without a fix: the stranger found that the prose states no problem. A rule states a norm and its reason; its form has no problem section.

| # | Finding (shortened) | Kind | Decision |
|---|---|---|---|
| 1 | own mismatch on C8 and C9, the declaration in the Cites line | restatement | no fix: the quoted sentence carries C8, so the mismatch does not count |
| 2 | "slice" in the Motivated-by line undefined | SP-04 | fixed: rephrased to avoid the project-orchestrator term: "with the record of its Project model at commit `86a1330` as the evidencing instance", the link on "record" kept (the slice record); C3, C4 and C5 reworded |
| 3 | "verifying gate" in the Motivated-by line undefined | SP-04 | fixed: rephrased: "approved by the owner for carrying at that project's node P3-N007 on 2026-10-30", the link on "P3-N007" kept (the gate record); C6 reworded |
| 4 | "C1+" in the Applies line has no link | SP-05 | fixed: the Cites line opens with the C-tier vocabulary row, "the criticality scale the Applies tag `[C1+]` reads: C1 and above". The Applies line itself stays unlinked: `mtool` parses every bracketed span on that line as an applicability tag, so a link there breaks the form audit |
| 5 | "Checked entries MUST be rewritten ..." names no actor | SP-18 | declined: K-003's released v1.6.0 sentence, outside this amendment's scope; an actor added to a MUST sentence is an amendment of its own. Listed for the owner as a candidate for the next K-003 edit |
| 6 | "entries MUST carry current stage designations" names no actor | SP-18 | declined: the reason of 5. Listed for the next K-003 edit |
| 7 | the title and the referent clauses contradict the appended sentence | SP-25 | declined: the owner decided at P3-N007's gate on 2026-10-30 that the title and the referent clauses stand as drafted, "instead" marking the exception. A fresh stranger again reads them as a contradiction. Listed for the owner with the smallest marker that would resolve it, should the owner want it: "no other document may claim that role, except as the next sentence provides" |
| 8 | the Rationale's dash clause ("— a mirror, not a duplication") is excess | SP-26 | declined: the reason of 5 (released text, outside scope). Listed for the next K-003 edit |

Claims after fixes: 43. Prose after fixes: 266 words. Claims check after the fixes (base: round 1 prose, over K-003, the vocabulary rows and the release-register entry): 4 changed claims (C3 to C6), 0 missing, 0 stale. Round trip: 43 of 43 claims mapped. IR checks: 0 violations, 0 warnings. `mtool audit form`: no findings. Fix commit: `a0adb86`.

Decided claims the fixes changed, for the owner: C3, C4 and C5 name the record of the Project model at commit `86a1330` in place of the slice; C6 names node P3-N007 without its gate's stage.

Confirmation: 2 of 3 fixes hold. Not held: 4. Declines accepted: 4 of 4. New defects: 1.

The round 1 instance confirmed at `a0adb86`. Finding 4 held in part: the Applies line is the first use of "C1+" and still carried no name. Finding 7 is withdrawn: the instance withdrew the contradiction on a reason quoting the prose, "that model is the referent instead", with C38. The round 1 verdict stays not readable as recorded; round 2 decides.

Re-fixed before round 2:

| # | Defect (shortened) | Kind | Re-fix |
|---|---|---|---|
| 4 | the Applies line's "C1+" carries no name | SP-05 | the Applies line reads `[C1+] (criticality tier C1 and above)`, the instance's proposed wording; `mtool audit form` accepts it (K-003 parses as C1 to C3, no findings). The Cites entry shortens to "the criticality scale of the Applies line". Marked `awaiting restatement` |
| N1 | "its Project model" follows a date and a node, so "its" has no clear antecedent | SP-03 | "with the record of the project-orchestrator's Project model at commit `86a1330`". Marked `awaiting restatement` |

Neither re-fix changes a claim. Claims check after the re-fixes (base: the prose at `a0adb86`): 0 changed claims, 0 missing, 0 stale. Round trip: 43 of 43.

### Round 2, count 1, 2026-10-30

Branch point version and commit: v1.9 at communication-pipeline `main`, commit `d1c5b55`. Prose 268 words; IR 43 claims; unratified terms 0. Brief: `k003-r2-brief.md` in the reasoning role's scratchpad, naming commit `d29bf2d`.

Claims check before the round (base: round 1 prose at `0ba6aa9`): 4 changed claims (C3 to C6), 0 missing, 0 stale.

Awaiting restatement: the re-fixes of finding 4 and of new defect N1. This round's entry states whether the round names them on its `Mismatches:` line or in a finding.

Signals script before the round: no signal fired; no line unparsed.

Carried into the brief: declines 5, 6 and 8 with their reasons, and the readability note. No passage is listed: no passage has drawn a mismatch that counts.

Stranger: instance `ae595e6a0b5723585`, a fresh instance, at commit `d29bf2d`. Prose 268 words by `wordCount`; IR 43 claims; 5 findings, 18.7 per thousand words. Restatement: one mismatch, on C2 with the term T7 (referent), attributed by the stranger to its own restatement, with a quoted prose sentence. Contradictions 2 (findings 2 and 5), undefined term 1 (finding 3); verdict: not readable for RD-4. Fixed 2; declined 2; finding 1 needs no fix under the exception.

Mismatches: C2 (own; relied on C2)

The quoted sentence is in the stranger's report, which the Orchestrator holds. The Orchestrator reports that the quote carries an IR claim, so the own mismatch does not count. The "relied on" entry names C2, the claim of the referent clauses' passage; the Orchestrator corrects it if the quote carries another claim. The passage, the referent clauses with the appended sentence, draws its first mismatch here. Round 1's own mismatch was on another passage, the Cites line's declaration (C8 and C9). Signals script after the `Mismatches:` line: no signal fired.

Awaiting restatement from round 1: the re-fix of finding 4 (the Applies line) and of new defect N1 ("the project-orchestrator's Project model"). Round 2 names neither on its `Mismatches:` line or in a finding.

| # | Finding (shortened) | Kind | Decision |
|---|---|---|---|
| 1 | own mismatch on C2 with T7, the referent clauses and the exception | restatement | no fix: the quote carries an IR claim, so the mismatch does not count |
| 2 | the title, "the single source of progress truth", against the appended sentence | SP-25 | declined: the reason of round 1, finding 7. The owner decided at P3-N007's gate on 2026-10-30 that the title and the referent clauses stand, with "instead" marking the exception; the title is the rule's name (C38). The instance offered to withdraw it if the rule records the precedence |
| 3 | "implementation map" in the Motivated-by line before the Statement defines it | SP-04 | fixed: the Motivated-by line links "implementation map" to K-003's own anchor, whose Statement defines it |
| 4 | "which" in the Cites line has no clear antecedent | SP-03 | fixed: "and the entry names the custom document types that make up the model, with no new Classification field", per C10 and C11 |
| 5 | the referent clauses, "no other document may claim that role", against the appended sentence | SP-25 | declined: the reason of 2. Fixed after round 2 by the owner's decision of 2026-11-01, which adopted the marker (round 3 entry) |

Two instances in a row, rounds 1 and 2, read the title and the referent clauses as contradicting the appended sentence. The Orchestrator is putting the marker to the owner now: "no other document may claim that role, except as the next sentence provides", and no change to the title (C38). The round 2 confirmation table carries findings 2 and 5 as declines the instance may withdraw by quoting the appended sentence.

Claims after fixes: 43. Prose after fixes: 269 words. Claims check after the fixes (base: the prose at `d29bf2d`): 0 changed claims, 0 missing, 0 stale. No claim changed. Round trip: 43 of 43 claims mapped. IR checks: 0 violations, 0 warnings. `mtool audit form`: no findings. Fix commit: `bec2473`.

Confirmation: 2 of 2 fixes hold. Not held: none. Declines accepted: 1 of 2. New defects: 1.

The round 2 instance confirmed at `bec2473`. Finding 2 is withdrawn: the instance withdrew it on a reason quoting the appended sentence, the title being a name under the rule-heading form. Finding 5 stands as a decline, pending the owner. The instance holds that the appended sentence does not name the clause "no other document may claim that role". It would withdraw the finding when the rule carries the marker or the owner records the reading. The owner's answer on the marker is pending.

Re-fixed after confirmation:

| # | Defect (shortened) | Kind | Re-fix |
|---|---|---|---|
| N1 | "with no new Classification field" in the Cites line has no verb | SP-03 | "and the declaration needs no new Classification field", per C11. Marked `awaiting restatement` |

The re-fix changes no claim.

### Round 3, count 1, 2026-11-01

Branch: methodology PR #73 merged at `a1959c3`'s state, so the count continues on branch `k-003-count-1-rounds` from `main` at `be5f993`. Branch point version and commit: v1.9 at communication-pipeline `main`, commit `d1c5b55`, the version the count opened under; v1.9 is still the active version on that project's `main`. The specification on this repository's `main` now carries count 6. Under branch point v1.9 a change the owner adopts during a count applies from the next count, so this count's rounds keep the rules it opened under. Brief: `k003-r3-brief.md` in the reasoning role's scratchpad, naming commit `e404dce`. Prose 278 words; IR 44 claims; unratified terms 0.

The owner's decision of 2026-11-01 adopted the marker. The second referent clause now reads "no other document may claim that role, except as the next sentence provides" (C44, decided, evidence E10; R7 ties it to C2). Round 2's finding 5 is closed as fixed by that decision; it is no longer a decline. The title is unchanged (C37). The release-register entry's impact assessment gains one line on the marker.

Claims check before the round (base: round 2 prose at `d29bf2d`): 1 changed claim, C44, new; 0 missing, 0 stale. Round trip: 44 of 44 claims mapped. IR checks: 0 violations, 0 warnings. `mtool audit form`: no findings.

Awaiting restatement: the re-fix of round 2's new defect N1, the Cites line's "and the declaration needs no new Classification field". This round's entry states whether the round names it on its `Mismatches:` line or in a finding. The marked clause sits in the passage of C2, which drew round 2's own mismatch; a second mismatch on that passage counts under the override.

Signals script before the round: no signal fired; no line unparsed.

Carried into the brief: round 1's declines 5, 6 and 8 with their reasons, and the readability note.

Stranger: instance `a9f2d1b45960bf846`, a fresh instance, at commit `e404dce`. Prose 278 words by `wordCount`; IR 44 claims; 2 findings, 7.2 per thousand words. Restatement: one mismatch, on C10, attributed by the stranger to its own restatement, with a quoted prose sentence: the restatement dropped "that make up the model" from the Cites line's declaration. Contradictions 0: the marker holds, and no finding raises the referent clauses. Undefined term 1 (finding 2); verdict: not readable for RD-4.

Mismatches: C10 (own; relied on C10)

The quoted sentence is the Cites line's declaration clause, which carries C8 to C11; the quote's exact words are in the stranger's report, which the Orchestrator holds. The passage, the declaration in the Cites line, drew round 1's own mismatch on C8 and C9. This mismatch is the passage's second in two rounds, so it counts under the override, and step 6 applies. Signals script after the `Mismatches:` line: no signal fired; the script compares claims, and round 1's line named C8 and C9, not C10. The recurrence is on the passage, read from the review record. Under the specification's second meta-review signal, a restatement mismatch that recurred on one passage in two rounds fires the signal, so this text is a meta-review subject; the script misses the recurrence because it compares claims. The count's `Meta-review:` line, written at the count's end, reads `pending`.

Awaiting restatement from round 2: the re-fix of N1, "and the declaration needs no new Classification field" in the Cites line. Round 3 names the passage that holds it, on its `Mismatches:` line and in finding 2.

| # | Finding (shortened) | Kind | Decision |
|---|---|---|---|
| 1 | own mismatch on C10, "that make up the model" dropped from the Cites line's declaration; the passage's second mismatch in two rounds | restatement, step 6 | structural fix: the declaration mechanism (C8 to C11) moves out of K-003's Cites line into the vocabulary row for planning/execution model, where a declaration form belongs. The Cites line now cites Constitution Article 7 and that row in one short clause, "(how a Classification declares the model)"; C7 reworded to match. C8 to C11 keep their words and move to the IR's vocabulary section. No decided claim changed. Marked `awaiting restatement` |
| 2 | "definition-by-citation" in the Cites line undefined | SP-04 | resolved by the move of 1: the term leaves K-003. The vocabulary row reads "a definition by citation under Article 7", linked to the Article |

Claims after fixes: 44. Prose after fixes: 251 words. Claims check after the fixes (base: round 3 prose at `e404dce`, over K-003, the vocabulary rows and the release-register entry): 1 changed claim (C7), 0 missing, 0 stale. Round trip: 44 of 44 claims mapped; the render map sends C8 to C11 to the vocabulary row. IR checks: 0 violations, 0 warnings. `mtool audit form`: no findings. Fix commit: `ba4e286`.

For round 4's brief: the Cites line, listed for a one-sentence restatement before the stranger opens the IR.

Confirmation: 0 of 0 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 0.

The round 3 instance read K-003 and the IR at `ba4e286` for new defects only, since the step-6 move is not for confirmation and finding 2 was resolved by the move. It found none, and confirmed that "definition-by-citation" is gone from K-003. The step-6 move stays `awaiting restatement`.

Two reader points from the instance, recorded without a fix:

- The Cites line's parenthesis glosses only the vocabulary row, so the line does not state Article 7's own contribution. C7 and the prose agree. If the round 4 stranger raises it, the fix names Article 7's role in two words.
- The link to the planning/execution model row resolves on a released version only when the row ships with the amendment. C21 and C22 already hold that.

### Round 4, count 1, 2026-11-01

Branch point version and commit: v1.9 at communication-pipeline `main`, commit `d1c5b55`; the count keeps the rules it opened under. Brief: `k003-r4-brief.md` in the reasoning role's scratchpad, naming commit `351296b`. Prose 251 words; IR 44 claims; unratified terms 0.

Claims check before the round (base: round 3 prose at `e404dce`): 1 changed claim (C7), 0 missing, 0 stale.

Awaiting restatement: the step-6 move of round 3's finding 1, the Cites line. The brief lists the Cites line for a one-sentence restatement before the stranger opens the IR. This round's entry states whether that restatement matched. A mismatch on the Cites passage or on the referent clauses' passage (C2) counts under the override.

Signals script before the round: no signal fired; no line unparsed. The second signal fired in round 3 on the Cites passage, read from the record (round 3 entry).

Carried into the brief: round 1's declines 5, 6 and 8 with their reasons, and the readability note. The carrier note reads: K-003 carries C1 to C7, C12, C44 and the terms; the vocabulary rows and the release-register entry carry C8 to C11 and C13 to C43.

Stranger: instance `aa54c592425d18317`, a fresh instance, at commit `351296b`. Side effect: the instance made one read-only `list_sessions` call, whose result it did not use; the brief allowed reading the two files only. Prose 251 words by `wordCount`; IR 44 claims; 1 finding, 4.0 per thousand words. Restatement: matched the IR; no restatement mismatch. Contradictions 0. Undefined term 1 (finding 2, in the instance's numbering).

Mismatches: none

The listed passage: the instance's one-sentence restatement of the Cites line matched the IR. The step-6 move of round 3's finding 1 holds; its `awaiting restatement` mark clears. Signals script after the `Mismatches:` line: no signal fired.

| # | Finding (shortened) | Kind | Decision |
|---|---|---|---|
| 2 | "stage designations" in the released sentence "entries MUST carry current stage designations" is undefined | SP-04 | fixed: "stage designations" is linked at first use to the Workflow vocabulary row, which defines a Backlog entry's current stage as a designation. A first-use link is within the amendment's scope, as the first commit's links were; the sentence's words are unchanged. The finding falls outside round 1's declines 5, 6 and 8, which concern actors and the Rationale |

Two points the instance did not count, fixed in the IR:

- C7 omitted the C-tier citation the Cites line carries. The citation becomes its own claim, C45, proposed: "K-003's Cites line names the C-tier vocabulary row as the criticality scale of the Applies line." C7 keeps its words. A single extended C7 drew a compound-claim warning (CK-03), so the addition takes a new number.
- T2 said "every project" where the Applies line limits K-003 to C1 and above. T2 now reads "every project at criticality tier C1 and above".

Verdict: not readable, pending confirmation. Under the rule the count opened under, an undefined-term finding the round's instance withdraws at confirmation, on a reason quoting the prose, does not count against the verdict. If the instance withdraws finding 2 on the linked sentence, round 4 reads readable and step 7 applies.

Claims after fixes: 45. Prose after fixes: 251 words. Claims check after the fixes (base: round 4 prose at `351296b`): 1 changed claim (C45, new), 0 missing, 0 stale. Round trip: 45 of 45 claims mapped. IR checks: 0 violations, 0 warnings. `mtool audit form`: no findings. Fix commit: `c71dee7`.

Confirmation: 1 of 1 fixes hold. Not held: none. Declines accepted: 0 of 0. New defects: 1.

The round 4 instance confirmed at `c71dee7`. The fix of finding 2 holds, and the instance withdrew finding 2 on a reason quoting the linked sentence, "entries MUST carry current stage designations". The withdrawn undefined-term finding does not count against the verdict. Round 4 reads readable.

Step 7: the round's one finding, 2, was fixed in the IR's terms and the prose before confirmation and is marked **confirmed** (withdrawn). The new defect, N1, sits in the IR only: ask A2 named four proposed claims and omitted C45. A2 now names five, C6, C7, C12, C24 and C45. The edit is an ask-list edit with no prose change, so it needs no stranger read; it is applied after confirmation, as count 5 of the specification did. N1 is marked **applied after confirmation**.

### Verdict, count 1

Readable at round 4 of four, on 2026-11-01, under the rules the count opened under (the specification at `e049bc6`, branch point v1.9). Rounds 1 to 3 were not readable. The text is not delivered by the reasoning role: an amendment awaits the owner's adjudication under Article 8. The IR's Status reads `reviewed`. The release-register entry's Adjudication field reads pending.

Footprint: declared 5, changed 5, surprises 0, misses 0, on branch `k-003-planning-execution-model` (PR #73, base `e049bc6`) and on branch `k-003-count-1-rounds` (base `be5f993`). Unratified terms: 0.

Meta-review: pending. Signals checked: signal 1 (fixes not held or claims missing or stale in two or more rounds) did not fire: one fix not held, in round 1 only. Signal 2 fired: a restatement mismatch recurred on one passage, the declaration in the Cites line, in rounds 1 (C8, C9) and 3 (C10). The signal is read from the record; the signals script, which keys recurrence by claim, does not report it. Signal 3 did not fire: words per claim fell from 6.07 in round 1 to 5.70 in round 4. Signal 4 did not fire: no contradiction in round 3 or later. The text is a meta-review subject.

The owner deferred the count's meta-review on 2026-11-02 to the communication-pipeline's ruleset review, which reads this record among its inputs. The `Meta-review:` line stays `pending` until that review delivers.

### For the owner

- A1: adjudicate the amendment under Article 8: accept, accept with amendments, or reject. **Resolved**: accepted as it stands, 2026-11-02.
- A2: ratify or strike the five proposed claims: C6, the Motivated-by wording; C7, the Cites entry for Article 7 and the planning/execution model row; C12, the Protects line; C24, the PR field; C45, the Cites entry for the C-tier row. **Resolved**: ratified, 2026-11-02.
- Candidates for the next K-003 edit, from round 1: finding 5, "Checked entries MUST be rewritten …" names no actor; finding 6, "entries MUST carry current stage designations" names no actor; finding 8, the Rationale's clause "a mirror, not a duplication". Each is released v1.6.0 text outside this amendment. **Resolved**: queued for the next K-003 edit, 2026-11-02, as a Backlog entry.
- Terms: none unratified. The amendment's vocabulary rows, *list of what is next* and *rendering*, carry terms the owner ratified on 2026-10-30. **Resolved**: nothing to ratify.
- Decided claims the rounds reworded, for ratification in their new wording: C3, C4 and C5 name the record of the Project model at commit `86a1330` in place of the slice; C6 names node P3-N007 without its gate's stage; C8 to C11 moved, their words unchanged, from the Cites line to the vocabulary row. **Resolved**: accepted with the amendment as it stands, 2026-11-02.
- Ruleset note, for the communication-pipeline's review: the signals script keys recurrence by claim, not by passage, so it missed signal 2 in this count. **Resolved**: listed for the pipeline's ruleset review, which also takes the deferred meta-review.

