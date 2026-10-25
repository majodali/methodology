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
