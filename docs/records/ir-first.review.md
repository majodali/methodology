# Review record: W-009 and the intermediate-representation specification

Reader of the reviewed text: RD-4 (a fresh agent session). Reviewer:
the communication pipeline's stranger reviewer (haiku, fresh context),
2026-10-26, disposition D3. Text reviewed: W-009, the specification
as first adopted (a mechanical transform of the pipeline's schema
v1.2), and the vocabulary entry. 2,362 words; 49 findings; 20.7 per
thousand words; verdict before fixes: not readable for RD-4. The
specification was rewritten in the methodology's own terms after the
review, so most rows below are fixed by the rewrite.

| # | Finding (shortened) | Disposition |
|---|---|---|
| 1, 19, 46 | the rule header, the status line and the History section carry the pipeline's own history | the Motivated-by field names evidencing instances by design (Article 6); the status line and History now name the source project as a Portfolio project and nothing of its internal history |
| 2, 18, 24, 42 | "pilot", "chunks", "case 001", "evaluation corpus" undefined | fixed: removed; the project is named and linked |
| 3, 41, 45, 48 | decisions and rulings cited with no link | fixed: the plan, the branch-point document, PR #44 and the vocabulary's convergence entry are linked |
| 4 | "every claim carries its evidence" | fixed: "and, where it has one, its evidence" |
| 5, 43 | "register fact" and "register" undefined | fixed: defined in the specification; the sentence shortened |
| 6, 9, 14, 15, 20, 28, 49 | long or two-claim sentences; semicolons | fixed: split |
| 7, 11, 12 | W-009's scope omits RD-4 and RD-5; the MAY covers all reports; documents always start as an IR | fixed: W-009 now covers documents and RD-4/RD-5 prose, limits the MAY to RD-1 and RD-3 |
| 8 | "exceeds thresholds" does not match the condition table | fixed: "when the rendering conditions select rendering"; the section is renamed Rendering conditions |
| 10 | "normative text" undefined; "its author" versus "reasoning role" | fixed: defined in W-009 and the header table; "the reasoning role that wrote the IR" in both |
| 13 | the round-trip check is a mechanism W-009 does not require | by design: a specification may define more than the rule requires; the check is stated as a check, not a duty |
| 16 | "Agent bootstrap" unlinked | fixed |
| 17, 30, 37, 38, 44 | referents ("does", "does not", "It", "those three") | fixed |
| 21, 31 | two readers in one Reader line; reader class joined with a file location | fixed: split |
| 22, 47 | "every element carries a provenance status" contradicts Provenance | fixed in the Purpose and the vocabulary entry |
| 23 | "the the" | fixed |
| 25 | "(v1.1, below)" | fixed: removed |
| 26 | identifier uniqueness has no check | fixed: CK-12 |
| 27 | CK checks have no names | fixed: a Name column |
| 29 | P-008 named inconsistently | fixed: full name everywhere |
| 32, 33, 34, 35, 36 | designation, formal-model horizon, unit, render map, "a model would hold" undefined | fixed: designation and the Backlog's horizon pointed at; unit cites P-008; render map given its form; connective prose defined against the IR |
| 39 | "decided from the IR alone" | fixed: "and one further input" |
| 40 | Normative header absent from the Document form | fixed: added as optional |
