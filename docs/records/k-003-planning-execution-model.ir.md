# IR: A declared planning/execution model is the source of progress truth

Reader: RD-4 (a fresh agent session) reading K-003 (the Backlog is the single source of progress truth) as amended; the owner adjudicates the amendment.
Purpose: document. The amendment of K-003 in place, by which a project whose Classification declares a planning/execution model takes that model as its referent for what is done and what is next, with the vocabulary rows and the release-register entry the amendment needs.
Status: rendered (count 1, round 1 not readable, 3 findings fixed and 4 declined, confirmation pending; rendered by the reasoning role on 2026-10-30; unratified terms 0)
Source: the project-orchestrator proposal "A declared planning/execution model is the source of progress truth" and its IR (93 claims, 17 terms) at project-orchestrator commit 25e92e8, approved for carrying by the owner at node P3-N007's verifying gate on 2026-10-30; the owner's decision of 2026-10-30 that the proposal lands in this repository as a methodology change, by pull request.
Normative: yes
Footprint: docs/rules/knowledge.md; docs/vocabulary.md; docs/releases.md; docs/records/k-003-planning-execution-model.ir.md; docs/records/k-003-planning-execution-model.review.md

## Terms

T1. Planning/execution model. defined-at: ../vocabulary.md#def-planning-execution-model [decided: owner, 2026-10-28]

T2. Backlog: the one dependency-ordered register of completed and upcoming work that K-003 requires of every project. defined-at: https://github.com/majodali/methodology/blob/v1.6.0/docs/rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth [decided: methodology v1.6.0, K-003]

T3. Classification. defined-at: ../vocabulary.md#def-classification [decided: methodology vocabulary]

T4. Implementation map: the Backlog's completed section, whose checked entries describe what actually shipped. defined-at: https://github.com/majodali/methodology/blob/v1.6.0/docs/rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth [decided: methodology v1.6.0, K-003]

T5. List of what is next. defined-at: ../vocabulary.md#def-list-of-what-is-next [decided: owner, 2026-10-30]

T6. Rendering. defined-at: ../vocabulary.md#def-rendering [decided: owner, 2026-10-30]

T7. Referent: in K-003, the one record a reader consults for what is done and what is next. defined-at: ../vocabulary.md#def-referent [decided: methodology v1.6.0, K-003]

T8. Node: one unit of work at any level of a project's plan hierarchy. defined-at: https://github.com/majodali/project-orchestrator/blob/198768a21da88d3b702563ae0a26a6dacfcace26/docs/process/README.md#def-node [decided: project-orchestrator process specification]

T9. Custom definitions section: the section of a Classification that holds a project's custom definitions, by citation or in full. defined-at: https://github.com/majodali/methodology/blob/v1.6.0/docs/constitution.md#article-7--the-c0-baseline-custom-definitions-and-the-sandbox [decided: Constitution Article 7]

T10. Project model: the project-orchestrator document type that describes each part of a project and records which nodes create, modify and use the part. defined-at: https://github.com/majodali/project-orchestrator/blob/38138c9b952ad995fc2e16725768564ae79a6571/docs/process/project-model.md [decided: owner, 2026-10-29]

T11. Slice: the first five entries of the project-orchestrator Project model, built by node P3-N006 (the thin end-to-end slice) and pinned at commit 86a1330. defined-at: https://github.com/majodali/project-orchestrator/blob/86a13308f70574abc0223ddb4f044b7e43ca1eb6/docs/project-model-slice-record.md [decided: project-orchestrator P3-N006 plan, 2026-10-29]

T12. Owner. defined-at: ../vocabulary.md#def-human-owner [decided: methodology vocabulary]

T13. Release register. defined-at: ../vocabulary.md#def-release-register [decided: methodology vocabulary]

T14. Portfolio register. defined-at: ../vocabulary.md#def-portfolio-register [decided: methodology vocabulary]

T15. Provenance: the invariant by which every claim a governed document makes can be traced to the decision, evidence or source that produced it. defined-at: ../vocabulary.md#def-provenance [decided: methodology vocabulary]

T16. Workflow. defined-at: ../vocabulary.md#def-workflow [decided: methodology vocabulary]

T17. Register. defined-at: ../vocabulary.md#def-register [decided: methodology vocabulary]

## Claims

### The amended statement

C1. K-003's statement gains one sentence at its end: "Where the project's Classification declares a planning/execution model, that model is the referent instead, and the Backlog's implementation map and list of what is next are renderings of it." evidence: E1, E4. [decided: owner, 2026-10-30]


C2. The appended sentence is an exception to the two referent clauses before it, "The Backlog is the referent for what is done and what is next" and "no other document may claim that role". evidence: E1. [decided: owner, 2026-10-30]


### The header fields

C3. K-003's Motivated-by line gains a citation of the evidencing instance, the record of the project-orchestrator Project model at commit 86a1330. evidence: E1, E3. [decided: owner, 2026-10-30]

C4. The project-orchestrator Project model at commit 86a1330 rendered the implementation map and the list of what is next. evidence: E3. [decided: project-orchestrator slice record at commit 86a1330]

C5. The renderings of the project-orchestrator Project model at commit 86a1330 were compared with the project-orchestrator Backlog. evidence: E3. [decided: project-orchestrator slice record at commit 86a1330]

C6. K-003's Motivated-by line names the project-orchestrator proposal and the owner's approval of the proposal for carrying at project-orchestrator node P3-N007 on 2026-10-30. evidence: E4. [proposed: this IR]

C7. K-003's Cites line names Constitution Article 7 for the Custom definitions section in which a Classification declares a planning/execution model. [proposed: this IR]

C8. A Classification declares a planning/execution model by an entry in its Custom definitions section. evidence: E1. [decided: owner, 2026-10-30]

C9. The declaring entry is a definition by citation under Article 7. evidence: E1. [decided: owner, 2026-10-30]

C10. The declaring entry names the types that make up the planning/execution model. evidence: E1. [decided: owner, 2026-10-30]

C11. The declaration needs no new Classification field. evidence: E1. [decided: owner, 2026-10-30]

C12. K-003's Protects line names provenance, because each claim of what is done and what is next traces to one record. [proposed: this IR]

### The vocabulary

C13. The vocabulary gains a row for list of what is next, a term the owner ratified at node P3-N007's verifying gate on 2026-10-30. evidence: E4. [decided: owner, 2026-10-30]

C14. The vocabulary gains a row for rendering, a term the owner ratified at node P3-N007's verifying gate on 2026-10-30. evidence: E4. [decided: owner, 2026-10-30]

C15. For a project whose Classification declares no planning/execution model, the list of what is next is the Backlog's upcoming section. evidence: E1. [decided: owner, 2026-10-30]

C16. For a project whose Classification declares a planning/execution model, the list of what is next is rendered from the model, one item per node not yet done. evidence: E1. [decided: owner, 2026-10-30]

C17. Under the amendment, the rendered list of what is next holds nodes only. evidence: E1. [decided: owner, 2026-10-30]

C18. Under the amendment, an open Backlog entry that names no node stays in the Backlog's upcoming section as the Backlog's own content, outside the rendered list. evidence: E1. [decided: owner, 2026-10-30]

C19. An open Backlog entry joins the list of what is next when the entry becomes a node, or when a node's plan takes the entry in. evidence: E1. [decided: owner, 2026-10-30]

C20. The vocabulary's Referent row gains the sense K-003 gives the word: the one record a reader consults for what is done and what is next. [inferred: R1]

C21. The vocabulary row for planning/execution model is on this repository's main branch since commit 350f75f and is unreleased at v1.6.0. evidence: E2. [decided: methodology main, commit 350f75f]

C22. The vocabulary row for planning/execution model ships in the release that carries the amendment, or in an earlier release. [inferred: R2]

### The release-register entry

C23. The Release-register entry's title is "A declared planning/execution model is the source of progress truth". evidence: E1. [decided: owner, 2026-10-30]

C24. The entry's PR field names this amendment's pull request, in the form of the register's other Unreleased entries. evidence: E5. [proposed: this IR]

C25. The entry names project-orchestrator as the suggesting project, with RU-021 (the planning/execution model is the source of progress truth) and the slice at commit 86a1330. evidence: E1. [decided: owner, 2026-10-30]

C26. On 2026-10-28 the owner decided that each project's planning/execution model is the primary source of truth about progress. evidence: E6. [decided: owner, 2026-10-28]

C27. A project that keeps a planning/execution model beside a Backlog under K-003 as released records what is done and what is next twice. [inferred: R3]

C28. The comparison of the slice's renderings with the project-orchestrator Backlog listed eleven differences. evidence: E3. [decided: project-orchestrator slice record at commit 86a1330]

C29. The comparison left none of the eleven differences unexplained. evidence: E3. [decided: project-orchestrator slice record at commit 86a1330]

C30. In both disagreements among the eleven differences, the Backlog showed finished work as unfinished while the model showed the work as done. evidence: E3. [decided: project-orchestrator slice record at commit 86a1330]

C31. The impact assessment covers every row of the Portfolio register at v1.6.0. evidence: E7. [decided: owner, 2026-10-30]

C32. The methodology repository is accommodated, because K-003 gains one sentence and the methodology's Classification declares no planning/execution model. evidence: E8. [decided: owner, 2026-10-30]

C33. methodology-tools is accommodated, because the sentence binds methodology-tools only once its Classification declares a planning/execution model, which the methodology's roadmap expects at the pilot. evidence: E9. [decided: owner, 2026-10-30]

C34. project-orchestrator is accommodated as the evidencing instance, and declares its planning/execution model only after the amendment is released and pinned there. evidence: E1. [decided: owner, 2026-10-29]

C35. allegro, in-real-life, in-real-life-ops, in-real-life-org, project-orchestrator-service, serverless-web-app-template and communication-pipeline are accommodated, because the sentence binds each only once its Classification declares a planning/execution model. evidence: E7. [decided: owner, 2026-10-30]

C36. The thirteen rows the Portfolio register marks implicit C0 are unaffected, because K-003 applies from criticality tier C1. evidence: E7. [decided: owner, 2026-10-30]

C37. The amendment keeps K-003's title, so links to the rule's anchor keep resolving. evidence: E4. [decided: owner, 2026-10-30]

C38. For a project that declares a planning/execution model, the rule's statement governs, because the title is the rule's name and not its text. evidence: E1. [decided: owner, 2026-10-30]

C39. The amendment leaves K-003's sentence on Workflow stage designations unchanged. evidence: E1. [decided: owner, 2026-10-29]

C40. The migration note says a project that declares no planning/execution model changes nothing. evidence: E1. [decided: owner, 2026-10-30]

C41. The migration note says a project that declares a planning/execution model renders its Backlog's implementation map and list of what is next from the model from the declaration on. evidence: E1. [decided: owner, 2026-10-30]

C42. From the declaration on, such a project rewrites its checked entries by that rendering of the implementation map. evidence: E1. [decided: owner, 2026-10-30]

C43. K-003's duty to rewrite checked entries stands under the amendment, met by that rendering. [inferred: R4]

## Relations

R1. C20 depends-on C1 because P-008 (terms are defined once and linked at first use) lists a term used in two senses with the sense to prefer in each use, and the vocabulary's Referent row holds only the IR sense.

R2. C22 depends-on C21 because a released rule cannot link an unreleased vocabulary entry.

R3. C27 depends-on C26 because a model that is the source of progress truth records what is done and what is next, and K-003 as released makes the Backlog record both.

R4. C43 depends-on C42 because a rendering that restates the completed section rewrites its checked entries.

R5. C28 supports C1 because the renderings the appended sentence requires were produced from a model and compared with a Backlog.

R6. C30 supports C27 because the two records of progress already disagree in the evidencing instance.

## Evidence

E1. The project-orchestrator proposal and its IR at commit 25e92e8ef541e0929e7e447f582edc15d3ec7629, docs/proposals/planning-execution-model-is-progress-truth.md and planning-execution-model-is-progress-truth.ir.md: sections "The change", "Open Backlog entries that name no node", "How a Classification declares a model" and "Release-register entry"; IR claims C8 to C17, C27 to C29, C54 to C69, C76, C77 and C83, terms T1 to T17. The proposal's quote of K-003 (its E1, at methodology v1.6.0, commit 3e34829) was re-checked on 2026-10-30 against this repository's main at commit e049bc6, the K-003 section from its heading to the next rule's heading: byte-identical, no drift.

E2. docs/vocabulary.md at commit 350f75f (2026-10-29), the row planning/execution model; unchanged at main, commit e049bc6; absent at tag v1.6.0.

E3. project-orchestrator docs/project-model.md and docs/project-model-slice-record.md at commit 86a13308f70574abc0223ddb4f044b7e43ca1eb6, section 3 of the slice record: five implementation-map rows; five what-is-next results, each "no open item"; the differences ML1 to ML7, BL1, BL2, DG1 and DG2; "No difference is unexplained."

E4. project-orchestrator docs/plans/p3-n007-type-declared-amendment-drafted.md at commit 25e92e8, section "Gate record, 2026-10-30, at verifying": the proposal approved for carrying as it stands; "the appended sentence stays one sentence of 29 words, and the referent clauses and the title stay as written, yielding to the exception"; ten terms ratified, list of what is next and rendering among them; the crossing commit is 1b9e207.

E5. docs/releases.md at main, commit e049bc6, section Unreleased: each entry's PR field reads "this amendment's PR."

E6. docs/vision.ir.md at main, commit e049bc6: claims C8, C19 and C20, each decided by the owner on 2026-10-28.

E7. docs/registers/portfolio.md at v1.6.0: 23 rows, ten at C1 or C2 and thirteen marked implicit C0.

E8. docs/classification.md at main, commit e049bc6, section Custom definitions: "No custom definitions."

E9. docs/roadmap.ir.md at main, commit e049bc6: claim C28, "At the pilot, methodology-tools declares its planning/execution model in its Classification, and K-003's amended clause then applies to it."

## Asks

A1. The owner, under Article 8 (amendments, versions, and migration): accept the amendment, accept it with amendments, or reject it. Depends: C1, C22.

A2. The owner: ratify or strike the four proposed claims, the Motivated-by wording (C6), the Cites entry (C7), the Protects line (C12) and the PR field (C24). Depends: C6, C7, C12, C24.

