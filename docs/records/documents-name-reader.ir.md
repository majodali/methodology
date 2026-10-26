# IR: Documents name their reader and define their terms once

Reader: RD-4 (a fresh agent session) reading the two new P- rules; the human owner adjudicates the amendment.
Purpose: document. The amendment that adds P-007 (documents state their reader) and P-008 (terms are defined once and linked at first use), moves the reader catalog and the term lifecycle into the style guide and the vocabulary, and lists the mechanical checks a lint can run.
Status: draft
Source: Allegro's documentation-standards proposal (docs/plans/documentation-standards-delta.md, 2026-10-16); the communication pipeline's reader catalog, term lifecycle and style specification (chunks 1 to 3); the owner's rulings of 2026-10-25 on term handling.
Normative: yes

## Terms

T1. Reader catalog: the methodology's set of defined readers, each with what it is assumed to know and the question a reviewer answers to judge a text readable for it. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-reader-catalog [decided: owner, 2026-10-24]

T2. Definition site: the one place a term is defined, a vocabulary row or the heading of the document that defines it, carrying an anchor every other use links to. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-definition-site [decided: owner, 2026-10-25]

T3. Readability test: the question a reviewer answers to judge a text readable for one catalog reader. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-readability-test [decided: owner, 2026-10-25]

T4. Reader statement: the opening of a document that names who it is for and what that reader is assumed to know, with a link to where that knowledge is defined. [proposed: this IR]

## Claims

### P-007, documents state their reader

C1. A document under docs/ opens with a reader statement. [proposed: this IR]

C2. The reader statement names a catalog reader by identifier, or describes the reader when no catalog entry fits. [proposed: this IR]

C3. A text that assumes the conversation that produced it is a report under W-008 (reports map their deliverables), not a document. [decided: Allegro proposal P-007, 2026-10-16]

C4. Without a named reader, readable has no test. [decided: Allegro proposal P-007, 2026-10-16]

C5. The reader catalog holds five readers: RD-1, the human owner in conversation; RD-2, the human owner returning; RD-3, a delegating agent; RD-4, a fresh agent session; RD-5, an external reader. [decided: owner, 2026-10-25]

C6. RD-1, RD-2 and RD-3 are report audiences under W-008, and RD-4 and RD-5 are document readers. [decided: owner, 2026-10-25]

C7. Each catalog entry carries a readability test. [decided: owner, 2026-10-25]

C8. The catalog is added to only when a real text had a reader none of the entries describes, and the text is cited. [decided: owner, 2026-10-25]

C9. The catalog lives in the style guide, and the vocabulary entry points to it. [proposed: this IR]

### P-008, terms are defined once

C10. A term with a project-specific meaning has one definition site. [decided: Allegro proposal P-008, 2026-10-16]

C11. A definition site carries an anchor of the form `<a id="def-<slug>"></a>`. [decided: owner, 2026-10-25]

C12. A document that uses a term is its definition site or links the site at the term's first use in the unit. [decided: owner, 2026-10-25]

C13. The unit is the whole document for a report and the section for a reference document. [decided: owner, 2026-10-25]

C14. After the first use in the unit, the term is written bare. [decided: owner, 2026-10-25]

C15. For RD-5, the external reader, the link is replaced by an inline gloss. [decided: owner, 2026-10-25]

C16. A term with no definition site is defined in one sentence at its first use and listed under terms introduced. [decided: owner, 2026-10-25]

C17. Ratification by the human owner adds the term's row to the project vocabulary, which becomes its definition site. [decided: owner, 2026-10-25]

C18. A word used in more than one sense across a corpus is listed in the vocabulary with the sense to prefer in each case. [decided: Allegro proposal P-008, 2026-10-16]

C19. Frequency of use needs no separate rule, because a term used often is one that reached a vocabulary early. [decided: owner, 2026-10-25]

### The mechanical checks

C20. The style guide lists, per house decision, the check a lint runs. [proposed: this IR]

C32. A listed check makes the mechanical part of the editing pass fail instead of relying on memory. [decided: Allegro proposal section 5, 2026-10-16]

C21. Each check is a warning, because the mechanical pattern approximates the rule. [proposed: this IR]

C22. The checks are the lint column of the pilot's style specification, run on the pilot's 26 documents and on this repository's amendment PRs. [decided: pilot chunks 2 and 3, 2026-10-25]

C23. methodology-tools implements the checks as `mtool style`. [proposed: this IR]

### Ratified terms

C24. The owner ratified the term migration round on 2026-10-26. [decided: owner, 2026-10-26]

C25. The owner ratified the part name terms introduced on 2026-10-26. [decided: owner, 2026-10-26]

C26. Both terms gain vocabulary rows with anchors under this amendment. [inferred: R1]

### Why and impact

C27. P-007 and P-008 protect sound abstraction. [decided: owner, 2026-10-24]

C28. Two projects evidence each rule: Allegro's documentation census and the pilot's eval corpus. [proposed: this IR]

C29. The P- rules bind new and edited prose only, and existing documents migrate by editorial passes. [decided: style guide, Migration]

C30. The amendment mints no coverage duty, because a reader statement and a term link are content of a document that already exists. [inferred: R2]

C31. The adjudication criterion for convergence practices is: adopt by the invariant each protects, smallest set first; standard types need a second project. [decided: owner, 2026-10-23]

## Relations

R1. C26 depends-on C17 because ratification creates a definition site, and the vocabulary row is that site.

R2. C30 depends-on C29 because a duty on edited prose adds no document.

R3. C28 supports C31 because the criterion asks for a second project.

## Evidence

E1. allegro docs/plans/documentation-standards-delta.md, sections 3 (P-007, P-008) and 5 (checks that tooling can run), 2026-10-16; docs/documentation-census.md.

E2. communication-pipeline docs/readers.md (v1), docs/term-lifecycle.md (v1), docs/style-spec.md (v1), at the merge of its PR #3 and on its branch chunk-3-measurement.

E3. communication-pipeline eval/cases/002-lint-on-own-documents-2026-10-25.md: 43 violations and 130 warnings fell to 0 and 30 on the pilot's own documents.

E4. methodology PR #44 (migration round) and PR #46 (terms introduced), merged 2026-10-26 with the terms ratified in the owner's message.

## Asks

A1. Adjudicate the amendment: accept, amend, or reject. Depends: C1, C10.

A2. Ratify or strike the term reader statement (T4).

A3. Confirm that the reader catalog lives in the style guide rather than in the vocabulary. Depends: C9.
