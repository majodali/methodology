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
| 5 | the referent clauses, "no other document may claim that role", against the appended sentence | SP-25 | declined: the reason of 2 |

Two instances in a row, rounds 1 and 2, read the title and the referent clauses as contradicting the appended sentence. The Orchestrator is putting the marker to the owner now: "no other document may claim that role, except as the next sentence provides", and no change to the title (C38). The round 2 confirmation table carries findings 2 and 5 as declines the instance may withdraw by quoting the appended sentence.

Claims after fixes: 43. Prose after fixes: 269 words. Claims check after the fixes (base: the prose at `d29bf2d`): 0 changed claims, 0 missing, 0 stale. No claim changed. Round trip: 43 of 43 claims mapped. IR checks: 0 violations, 0 warnings. `mtool audit form`: no findings. Fix commit: pending, the Orchestrator commits the staged pass.

The confirmation line is written when the round 2 instance answers.
