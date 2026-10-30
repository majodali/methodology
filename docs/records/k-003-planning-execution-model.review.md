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
| 1 | 261 | 43 | pending | pending | pending |

### Round 1, count 1, 2026-10-30

Brief: `k003-r1-brief.md` in the reasoning role's scratchpad, dispatched by the Orchestrator. Prose 261 words (whitespace-separated words of K-003 from its heading to the next rule's heading, the render map stripped, by `wordCount` in the communication-pipeline's `scripts/ir.mjs`); IR 43 claims. The stranger model, the findings, the decision on each finding, the `Mismatches:` line, the confirmation line and the verdict are recorded here when the stranger reports.
