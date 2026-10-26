# Stranger review of the Portfolio refresh rendering, round 1

Reviewer: the reviewer role on the haiku model, fresh context, given the prose, the IR, the RD-1 catalog entry and the style rows. Reviewed 2026-10-25. Disposition column added by the reasoning role; a disputed finding keeps its row and gets one sentence why.

Verdict: not readable for RD-1. Counts: 257 prose words; 38 findings (prose 21, IR 17); 82 prose findings per thousand words; 6 undefined or borrowed terms; 3 unresolved referents.

| # | Quoted text | Defect (reviewer) | Rule | Disposition |
|---|---|---|---|---|
| 1 | Portfolio register refresh after the 1.5.0 migration round | "migration round" used before Terms introduced defines it | SP-04 | accepted: the term is now defined at first use and listed; T1 was also wrongly marked decided, since release-process step 5 does not define the phrase |
| 2 | Eight of the nine projects pinned ... now pin methodology 1.5.0. | lead sentence before the Asks | SP-13 | disputed: SP-13 requires leading with the outcome, then the asks; the sentence is the outcome |
| 3 | Eight of the nine projects | count in prose | SP-20 | disputed: the sentence is about that number, which SP-20 exempts |
| 4 | Review and merge this Portfolio register refresh. | two actions in one ask | SP-01 | disputed: one request with two steps, the standard merge ask |
| 5 | carries the reporting block that W-008 | "reporting block" undefined | SP-04 | accepted: rephrased as the block W-008 requires in the Agent bootstrap |
| 6 | serverless-web-app-template still pins 1.4.0 and carries no reporting block. | two claims | SP-01 | accepted: C4 split |
| 7 | has been open since 2026-09-02. | no observation date | SP-03 | accepted: "as of 2026-10-25" added |
| 8 | The allegro row records deviation D-1 ... and two methodology proposals ... | two claims | SP-01 | accepted: C7 split |
| 9 | deviation D-1 | no name | SP-05 | accepted: named |
| 10 | two methodology proposals | not named | SP-03 | accepted: both files named |
| 11 | The communication pipeline's paraphraser renders ... as the pipeline's first live run | two claims | SP-01 | accepted: C9 removed from this IR; the live run is recorded in the pipeline's chunk 2 IR |
| 12 | as the pipeline's first live run on a methodology deliverable. | process statement under What is already covered | W-008 | accepted: C9 removed |
| 13 | from the claims list behind this report | "Backlog entry", "claims list", "methodology deliverable" undefined | SP-04 | accepted in part: C9 removed; Backlog is a methodology Register type the reader knows |
| 14 | the nine pinned rows read 1.5.0, except ... | false as worded; three facts in one sentence | SP-01; consistency | accepted: C6 split and reworded as eight of nine |
| 15 | What changed | no named pointer into the deliverable | W-008 | accepted: C6 and C8 now name the file and the rows |
| 16 | The census note records ... | "census note" undefined, no pointer | SP-04 | accepted: named as the register's Census line with its location |
| 17 | The register rows depend on ... because ... | two claims | SP-01 | accepted as a rendering defect: relations are not rendered; the rendering rule now says so |
| 18 | the register caches what the Classifications declare | metaphor | SP-08 | disputed: the Portfolio register's own header calls its summaries an informative cache, so the word is the corpus's term, which RD-1 knows; a stranger could not know it, which is the finding working as designed |
| 19 | The serverless-web-app-template row depends on ... because ... | two claims | SP-01 | accepted as row 17 |
| 20 | It is defined in step 5 of the | sentence-initial pronoun | SP-03 | accepted |
| 21 | in allegro docs/plans/. | path not linked | SP-05 | accepted: linked |
| 22 | Source: the owner's merges of the nine migration PRs | false: one PR is open | IR provenance | accepted: Source now reads eight of the nine |
| 23 | C3 ... W-008's required reporting block | W-008 bare on first use in the IR | SP-05 | accepted: named |
| 24 | grep for "cached from W-008" | evidence shows a heading, claim says the required block | claim-evidence match | accepted: C3 now claims the heading, which is what the grep shows |
| 25 | C4 | compound claim | CK-03 | accepted: split |
| 26 | C6 | contradiction; compound | CK-03; consistency | accepted: split and reworded |
| 27 | names its open PR | "its" ambiguous | SP-03 | accepted: reworded |
| 28 | [proposed: this IR] on C6 and C8 | no date, no evidence; prose states them as settled | IR provenance | disputed on form: the schema's proposed status takes the IR identifier, not a date; accepted on substance: the mapping of proposed claims to W-008 parts is an open schema question (pipeline chunk 2 IR, ask A5) |
| 29 | C7 | compound claim | CK-03 | accepted: split |
| 30 | deviation D-1 against W-001 | D-1 bare | SP-05 | accepted: named |
| 31 | allegro's row records that deviation D-1 | evidence does not show the row | claim-evidence match | accepted: E5 added, the register diff |
| 32 | C8 ... census note | undefined in the IR | SP-04 | accepted |
| 33 | C9 | compound; process statement | CK-03 | accepted: removed |
| 34 | [decided: pilot plan, chunk 2, 2026-10-24] | source unresolvable | IR provenance | accepted: moot, C9 removed; the general point stands and goes to chunk 3 |
| 35 | R1 ... because ... | dependency and reason in one relation | CK-03 | disputed: the schema defines a relation as `<id> <verb> <id> because <reason>` |
| 36 | R2 ... because ... | as 35 | CK-03 | disputed: as 35 |
| 37 | A2. Review and merge ... Depends: C6 | two actions; depends on a proposed claim | SP-01 | disputed: as 4; an ask that depends on a proposed claim is the normal case, since the ask is what ratifies it |
| 38 | E4 ... "B-131 is closed"; allegro docs/plans/... | semicolon in evidence | SP-09 | disputed: an evidence pointer is a list, not prose |

Tally: 27 accepted, 11 disputed. Three of the accepted findings changed the specifications: terms are defined at first use as well as listed; relations are not rendered; What changed items carry a named pointer. Two of the disputed findings changed the reviewer's instructions: the relation form, and SP-20's exemption.

# Round 2, on the second rendering and the amended IR

Same reviewer role, model and inputs, plus the vocabulary the reader's corpus defines and the list of forms the schema defines as not defects. Reviewed 2026-10-25.

Verdict: not readable for RD-1, on the one-claim test. Counts: 284 prose words; 22 findings (prose 10, IR 12); 35.2 prose findings per thousand words, down from 82.0; 3 undefined or borrowed terms; 2 unresolved referents.

| # | Quoted text | Defect (reviewer) | Rule | Disposition |
|---|---|---|---|---|
| 1 | The portfolio register refresh for the 1.5.0 migration round, meaning ... | the lead defines a term and states the outcome in one sentence | SP-01 | accepted as a specification defect: defining at first use collides with one claim per sentence when the first use is the lead; the paraphraser now keeps introduced terms out of the lead sentence |
| 2 | for the 1.5.0 migration round | 1.5.0 without "methodology" | SP-05 | accepted |
| 3 | projects pinned in the Portfolio register now pin methodology 1.5.0 | "pinned" in two senses | SP-04 | accepted: "listed in" |
| 4 | the heading of the block that W-008 ... requires | "the block" undefined | SP-03; SP-04 | accepted: the heading is now quoted |
| 5 | was opened 2026-09-02 and was still open on 2026-10-25 | two claims | SP-01 | accepted: split |
| 6 | Eight rows, those of the projects listed above | no named pointer | SP-13 | accepted: the rows are named |
| 7 | it reads "pinned 1.4.0" and names serverless-web-app-template #4 as open | two claims | SP-01 | accepted: split |
| 8 | deviation D-1 (the per-chunk gate deviation against W-001, two delivery modes, human-gated) | nested gloss | SP-05 | accepted: reworded |
| 9 | the per-chunk gate | undefined term | SP-04 | disputed: the phrase is W-001's own language, which RD-1 knows; the reviewer's vocabulary list did not include W-001's text |
| 10 | adjudication | undefined term | SP-04 | disputed: a methodology process term (interim adjudication), omitted from the vocabulary given to the reviewer; the claim is reworded anyway to the proposals' own status |
| 11 | Purpose: ... closes the 1.5.0 migration round | header contradicts ask A1 | consistency | accepted: a true inconsistency; the Purpose now says the refresh records the round, and the round closes when the template's PR merges |
| 12 | Source: ... ; checkouts ... | semicolon in Source | SP-09 | disputed: a header field is a list, not prose; reworded anyway under 13 |
| 13 | the owner's merges of eight of the nine migration PRs | merges not evidenced | IR Source | accepted: the Source now names what was observed, the pins, not the merges |
| 14 | The eight are | referent in another claim | CK-01 | accepted: "The eight projects pinning 1.5.0 are" |
| 15 | the block that W-008 requires. evidence: E2 | evidence shows a heading string, not a requirement | claim-evidence | accepted: the claim now states the heading string E2 searched for |
| 16 | carries no W-008 block. evidence: E2 | as 15 | claim-evidence | accepted: as 15 |
| 17 | C6 | compound | CK-03 | accepted: split |
| 18 | C8 | compound | CK-03 | accepted: split |
| 19 | D-1 ... is retired. evidence: E4, E5 | evidence does not link B-131 to D-1 | claim-evidence | accepted: E4 now cites D-1's disposition line, "tracked as B-131" |
| 20 | C9, C10 carry decided | they are register edits, like C7, C8, C11 | provenance | accepted: the third signal on this point (paraphraser round 2, reviewer round 2, and the pipeline's chunk 2 IR ask A5); both now carry proposed |
| 21 | awaiting adjudication | evidence says draft proposal | claim-evidence | accepted: reworded to the proposals' own status |
| 22 | A2 ... Depends: C7, C8, C11 | omits C9, C10 | relations | accepted |

Tally: 19 accepted, 3 disputed. One specification change: an introduced term is defined in a sentence of its own, never inside the lead. One open question for the owner: the readability test's second question, "does each sentence state one claim?", as the reviewer applies it fails a sentence such as "opened on 2026-09-02 and still open on 2026-10-25"; whether that is the intended bar is a reader-catalog ruling for chunk 3.

# Round 3, on the third rendering and the third IR

Same reviewer role and model, with the reader's vocabulary supplied. Reviewed 2026-10-25.

Verdict: readable for RD-1. Counts: 317 prose words; 16 findings (prose 8, IR 8); 25.2 prose findings per thousand words, down from 35.2 and 82.0; 1 undefined or borrowed term; 0 unresolved referents.

| # | Quoted text | Defect (reviewer) | Rule | Disposition |
|---|---|---|---|---|
| 1 | is ready for your review, and one pull request still needs a merge | two claims in the lead | SP-01 | accepted, not fixed: the lead states the outcome and the decision needed in one sentence by design; whether that is one claim is the owner's ruling under ask A7 of the pipeline's chunk 2 IR |
| 2 | so the migration round closes | term used one sentence before its definition | SP-04 | accepted: the paraphraser followed its contract, which put the definition at first use; the contract should put the definition before the first use |
| 3 | A migration round is the set of ... | a definition inside an ask | W-008 part 1 | accepted: same cause as 2; the definition belongs before the Asks heading or in Terms introduced alone |
| 4 | now pin methodology 1.5.0 | "now" under What is already covered reads as post-deliverable state | W-008 part 2 | accepted: an observation dated 2026-10-25 reads as settled only with its date; the paraphraser dropped the date line it had in round 2 |
| 5 | the heading of the block that W-008 ... requires | a second claim and 27 words | SP-01; SP-02 | accepted, not fixed: the gloss names the heading's purpose, which the round 2 reviewer asked for |
| 6 | contains the heading "cached from W-008" | the quoted string is a fragment of the heading | SP-21 | accepted: the full heading is "Reporting and writing — cached from W-008; do not edit here" |
| 7 | documentation-standards-delta.md and conceptual-model-methodology-delta.md | not linked | SP-05 | accepted, not fixed in this round |
| 8 | one pull request still needs a merge | the lead names one of two merges | SP-13 | accepted, not fixed: the second merge is this PR itself |
| 9 | Source: ... | the Source omits E4 and E5 | IR header | accepted |
| 10 | listed with a pin in the Portfolio register | evidence shows Classifications, not a register listing | claim-evidence | accepted in part: E5 is the register; C1 should cite it too |
| 11 | contains the heading ..., the heading of the block that W-008 requires | compound claim | CK-03 | accepted, as 5 |
| 12 | E2 is a string search | the evidence does not show that W-008 requires the block | claim-evidence | accepted in part: the requirement is W-008's own text, which the claim could cite |
| 13 | D-1 ... is retired. evidence: E4, E5 | evidence shows B-131 closed, not D-1 retired | claim-evidence | accepted: E4 shows the disposition that ties D-1 to B-131 and B-131's closure; the claim's wording "is retired" is an inference from both, and should say so |
| 14 | R3. C11 depends-on C12 ... | the reason does not concern C12 | relation form | accepted: a wrong target; R3 now relates C11 to E4's two facts by a claim, fixed in the IR |
| 15 | [proposed: this IR] | no IR identifier | provenance | disputed: the schema permits "this IR" |
| 16 | The migration PR ... was opened on 2026-09-02 | evidence does not show that #4 is the migration PR | claim-evidence | accepted in part: the PR's title says so; E3 should quote it |

Tally: 15 accepted (6 fixed or to fix in the IR, 9 recorded for the paraphraser contract or the owner's ruling), 1 disputed. Delivered on the readable verdict. The remaining findings are claim-evidence precision and the placement of an introduced term's definition, both now in the pipeline's chunk 2 record.
