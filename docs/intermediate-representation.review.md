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
| 1a | old | 2,884 | 148 | | | |
| 1b | revised | 2,884 | 148 | | | |
