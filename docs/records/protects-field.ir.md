# IR: Rules name the invariant they protect

Reader: RD-4 (a fresh agent session) reading Article 5 and a rule header; the human owner adjudicates the amendment.
Purpose: document. The amendment to Constitution Article 5 that adds an optional `Protects:` header field naming the convergence invariant a rule protects, with the three invariants defined in the vocabulary.
Status: reviewed (one stranger review at protects-field.review.md, disposition D3; 20 findings, 14 fixed; verdict before fixes: not readable for RD-4)
Source: the owner's "Convergence and Divergence" (2026-10-22); the convergence work item in the Backlog, open point "a `Protects:` header field on rules"; the pilot plan's settled decision 5 (2026-10-24).
Normative: yes

## Terms

T1. Convergence: a project is convergent while the cost for its owners to understand, change and verify it grows more slowly than the project. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-convergence [decided: owner, 2026-10-22]

T2. Invariant: one of three properties a convergent project keeps as it grows: provenance, sound abstraction, proportional verification. [proposed: this IR]

T3. Provenance: every claim a governed document makes can be traced to the decision, evidence or source that produced it. [proposed: this IR]

T4. Sound abstraction: every term and structure a governed document uses has one definition and is used as defined. [proposed: this IR]

T5. Proportional verification: the effort spent checking a change grows with the change's footprint, the files and claims it touches, and not with the size of the project. [proposed: this IR]

## Claims

### The rule form

C1. Article 5 lists the fields every rule has. [decided: constitution, Article 5]

C2. A rule MAY carry a `Protects:` header field naming one or more of the three invariants. [proposed: this IR]

C3. The `Protects:` field sits after `Cites:` in the rule header. [proposed: this IR]

C4. A `Protects:` value names each invariant, followed by an em-dash and one clause saying how the rule protects it, with several invariants separated by semicolons. [proposed: this IR]

C5. A rule without a `Protects:` field is not defective. [proposed: this IR]

C6. The owner's essay names the three invariants, and does not define them in a governed document. [decided: owner, 2026-10-22]

C7. The definitions of the three invariants in this amendment are proposed wordings for the owner to confirm or replace. [proposed: this IR]

C8. W-008 (reports map their deliverables) carries the first `Protects:` field. [proposed: this IR]

C9. A review round MAY use the `Protects:` fields to ask, per invariant, which rules protect it and whether the set is complete. [proposed: this IR]

### Why

C10. The owner's adjudication criterion for convergence practices is to adopt by the invariant each practice protects, smallest set first. [decided: owner, 2026-10-23]

C11. Applying the criterion needs each rule to name its invariant. [inferred: R1]

C12. Each pipeline stage cites the invariant it protects. [decided: owner, 2026-10-24]

C13. A field that is optional adds no coverage duty, so the amendment accommodates every project. [proposed: this IR]

C14. The amendment is a constitutional change, and the release that carries it is a minor release. [decided: release process, docs/releases.md v1.5.0 precedent]

## Relations

R1. C11 depends-on C10 because a criterion stated per invariant cannot be applied to a rule that names none.

R2. C8 depends-on C2 because the first instance needs the field to exist.

## Evidence

E1. docs/backlog.md, the convergence work item: "Open: ... a `Protects:` header field on rules".

E2. communication-pipeline docs/plans/pipeline-pilot.md, settled decision 5.

E3. docs/constitution.md, Article 5, at v1.5.0; docs/rules/README.md, "Rule ID and header format".

E4. docs/releases.md, v1.5.0: "Minor — normative content, one constitutional change".

## Asks

A1. Adjudicate the amendment: accept, amend, or reject.

A2. Confirm or replace the three invariant definitions (T3, T4, T5), and ratify or strike the term invariant (T2). Depends: C7.

A3. Decide whether the owner's essay enters the methodology repository as the invariants' definition site, in place of the vocabulary rows. Depends: C6.
