# IR: Normative text gets a second stranger round, and the IR declares its footprint

Reader: RD-4 (a fresh agent session) reading the intermediate-representation specification; the human owner adjudicates the amendment.
Purpose: document. The amendment to the intermediate-representation specification that makes a second stranger round the default for normative text and adopts the optional Footprint header from the pipeline's schema v1.3.
Status: reviewed (two stranger rounds at normative-second-round.review.md, disposition D3; round 1: 28 findings, not readable; round 2: 29 findings, not readable, all fixed; the owner decides on a third round at adjudication)
Source: the owner's rulings at the communication pipeline's chunk 4 gate, 2026-10-26 ("Second stranger review on normative text is a good call"; the term footprint ratified); the pipeline's schema v1.3 and evaluation case 004.
Normative: yes
Footprint: docs/intermediate-representation.md; docs/records/; docs/releases.md; docs/backlog.md; docs/registers/portfolio.md

## Terms

T1. Footprint: the files or directories an IR declares its work is expected to touch, compared after the work with the files the branch changed. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-footprint [decided: owner, 2026-10-26]

## Claims

### The second round

C1. Normative text rendered by the reasoning role is reviewed by a stranger, the findings are fixed, and a stranger reviews the fixed text again. [decided: owner, 2026-10-26]

C2. The second round reports the readability verdict after fixes, which the first round cannot. [decided: evaluation case 004, 2026-10-26]

C3. Four normative texts reviewed once in October 2026 were all judged not readable before fixes, and none was measured after. evidence: E1. [decided: evaluation case 004, 2026-10-26]

C4. A second round costs one more reviewer run, between 146 and 273 seconds and between 83 and 121 thousand tokens on the frugal tier in those four cases. evidence: E1. [decided: evaluation case 004, 2026-10-26]

C5. The second round applies to normative text only. [decided: owner, 2026-10-26]

C14. A report keeps one stranger round, run only on request for RD-1 or RD-3. [decided: owner, 2026-10-25]

### The footprint header

C6. An IR may carry an optional Footprint header listing the files or directories its work is expected to touch. [decided: owner, 2026-10-26]

C7. After the work, the declared footprint is compared with the files the branch changed: a changed file not declared is a surprise, and a declared file not changed is a miss. [decided: pipeline schema v1.3, 2026-10-26]

C8. The surprise and miss counts are the mechanical reading of the prediction-surprise indicator of convergence. [decided: owner, 2026-10-26]

C9. methodology-tools reads the Footprint header and runs the comparison as `mtool ir footprint`. [proposed: this IR]

### Registers

C10. The communication-pipeline project's declared exit changes: the repository is kept, with its evaluation corpus, until the owner is satisfied that the process works well in all projects. [decided: owner, 2026-10-26]

C11. The Portfolio register row for communication-pipeline records the changed exit and the completed graduation. [inferred: R1]

C12. The convergence work item in the Backlog closes its open point on the Protects: field and records P-007 and P-008 as adopted. [decided: PRs #47 and #48, 2026-10-26]

C13. The amendment is normative content for the methodology-corpus type and mints no duty elsewhere. [proposed: this IR]

## Relations

R1. C11 depends-on C10 because the register copies the declared exit from the project.

## Evidence

E1. communication-pipeline eval/cases/004-normative-text-reviews-2026-10-26.md, Findings and Measures tables.

E2. communication-pipeline docs/ir-schema.md, Changes, v1.3; scripts/footprint.mjs.

E3. The owner's message of 2026-10-26 at the chunk 4 gate.

## Asks

A1. Adjudicate the amendment: accept, amend, or reject. Depends: C1, C6.

A2. Confirm that `mtool ir footprint` is wanted in methodology-tools, or leave the comparison to the pipeline's script. Depends: C9.
