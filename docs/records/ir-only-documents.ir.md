# IR: IR-only documents

Reader: RD-2
Purpose: proposal. The owner's decision of 2026-10-30 that some documents are delivered as their IR alone, with no prose rendering and no stranger rounds, and the three texts the decision changes: W-009, the IR specification's rendering rule, and the communication-pipeline's branch point.
Status: delivered IR-only (the owner adopted the option on 2026-10-30 while approving the roadmap; this record is the first document delivered under it after the roadmap itself; mtool ir check 0 violations; unratified terms 0)
Source: the owner's message of 2026-10-30 approving the roadmap IR: "I find the IR very readable, for this and some other documents IR-only will work, no prose version required. We should update the docs/comms pipeline to include that option."
Footprint: docs/records/ir-only-documents.ir.md; docs/rules/working-agreement.md; docs/intermediate-representation.md; docs/intermediate-representation.ir.md; docs/vocabulary.md; docs/releases.md; communication-pipeline docs/branch-point.md

## Terms

T1. IR-only document. defined-at: vocabulary.md#def-ir-only-document [decided: owner, 2026-10-30]

T2. Intermediate representation. defined-at: vocabulary.md#def-intermediate-representation [decided: methodology vocabulary]

T3. Paraphraser. defined-at: vocabulary.md#def-paraphraser [decided: methodology vocabulary]

T4. Stranger. defined-at: vocabulary.md#def-stranger [decided: methodology vocabulary]

## Claims

### The decision

C1. The owner may designate a document IR-only. [decided: owner, 2026-10-30]

C2. An IR-only document is delivered as its IR, with no prose rendering and no stranger rounds. [decided: owner, 2026-10-30]

C3. The IR check (the mechanical checks CK-01 onward of the IR specification) is the only gate an IR-only document passes before delivery. [decided: owner, 2026-10-30]

C4. An IR-only document's Status line reads `delivered IR-only`, with the date and the owner's designation. [decided: owner, 2026-10-30]

C5. The owner's designation is recorded in the IR's Status line or in the owner's message the IR cites as Source. [decided: owner, 2026-10-30]

C6. The roadmap document (docs/roadmap.ir.md) was the first IR-only document, designated on 2026-10-30. [decided: owner, 2026-10-30]

### What stays as it was

C7. Normative text, a rule, a specification or any text whose words bind, is never IR-only: it is rendered by the reasoning role and reviewed by a stranger, as W-009 requires. [decided: owner, 2026-10-30]

C8. A document the owner has not designated IR-only follows W-009 and the rendering conditions unchanged. [decided: owner, 2026-10-30]

C9. A report to RD-1 or RD-3 that the rendering conditions leave unrendered was already delivered as its IR under W-009; the designation extends that delivery to documents for RD-2, RD-4 and RD-5. [decided: methodology W-009 and the IR specification's rendering conditions]

### The three text changes

C10. W-009's Statement gains one sentence after "Otherwise the IR is delivered as it stands": "A document the owner designates IR-only is delivered as its IR, whatever its reader, and no prose is rendered for it." [proposed: this IR]

C11. The IR specification's rendering conditions gain a first row: the owner designates the document IR-only, disposition: no rendering and no rounds; the IR is the deliverable. [proposed: this IR]

C12. The IR specification's Status vocabulary gains `delivered IR-only`. [proposed: this IR]

C13. The communication-pipeline's branch point gains the row BP-00: the owner designates the document IR-only, disposition D0, taking precedence over every other row except BP-01 and BP-02a. [proposed: this IR]

C14. BP-02a keeps its precedence because normative text is never IR-only (C7). [inferred: R2]

C15. The methodology vocabulary gains the row IR-only document. [proposed: this IR]

C16. The release register's Unreleased entry records the change as an amendment to W-009 and the IR specification. [proposed: this IR]

### Why

C17. The owner found the roadmap IR readable without prose, and expects the same of other documents whose readers are the owner and agent sessions. [decided: owner, 2026-10-30]

C18. An IR-only document costs one authoring pass and one mechanical check, where a rendered document costs a paraphraser pass and between one and ten stranger rounds. [inferred: R3]

## Relations

R1. C2 depends-on C1 because the delivery form follows from the designation.

R2. C14 depends-on C7 because the precedence rule encodes the exception for normative text.

R3. C18 depends-on C2 because the saved cost is the rendering and the rounds the designation removes.

R4. C13 depends-on C11 because the branch point implements the IR specification's rendering conditions.

## Evidence

E1. docs/roadmap.ir.md, Status line of 2026-10-30: delivered IR-only, approved by the owner with its five proposed claims confirmed.

E2. docs/rules/working-agreement.md, W-009 Statement, the sentence "Otherwise the IR is delivered as it stands."

E3. communication-pipeline docs/branch-point.md, the dispositions table (D0 lint only, D1 render, D2 render and review, D3 review, reasoning-role rendered) and the conditions table BP-01 to BP-09.

E4. docs/vision.review.md and docs/intermediate-representation.review.md: ten and four rounds respectively for two rendered documents.

## Asks

A1. Confirm the three text changes C10 to C13 as applied in the same commit as this record. Default: confirm. Depends: C10, C11, C12, C13.

A2. Ratify or strike the term IR-only document. Default: ratify. Depends: T1.
