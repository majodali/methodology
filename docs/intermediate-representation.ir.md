# IR: The intermediate representation specification

Reader: RD-4
Purpose: document. The complete model of the specification docs/intermediate-representation.md: what an IR is, how it is formed, checked, rendered, reviewed and kept.
Status: rendered (count 7, round 8; edited for communication-pipeline evaluation case 015, rendered by the reasoning role; count 6 accepted and delivered by the owner 2026-11-01)
Source: the owner's adoption of 2026-11-02 of communication-pipeline evaluation case 015's changes 1 to 30, of which changes 2, 3, 5 (case 013's changes 1 to 3), 14 to 20 and 26 amend this specification (count 7); the owner's adoption of 2026-10-30 of communication-pipeline evaluation case 012's fifteen changes, of which changes 1, 2, 4 to 9, 11, 13 and 14 amend this specification (count 6); the owner's adoption of 2026-10-30 of communication-pipeline evaluation cases 010 and 011's recommended changes, of which case 010's changes 1, 5, 9, 11, 12 and 13 and case 011's change 1 amend this specification (count 5); the owner's adoption of 2026-10-29 of communication-pipeline evaluation case 009's nineteen changes, of which changes 2, 14, 15 and 18 amend this specification (count 4); the owner's decision of 2026-10-27 on signal-based meta-review triggers (count 3); communication-pipeline evaluation case 008 (owner decision of 2026-10-27, change 5) for count 2; for count 1, docs/intermediate-representation.md at v1.5.0 plus PR #50 (main, 89964a7); the owner's ruling of 2026-10-26 on stranger rounds and meta-review (PR #51, unmerged); the per-finding analysis of PR #51's ten rounds in the communication-pipeline project, eval/analysis/pr51-findings.md.
Normative: yes
Footprint: docs/intermediate-representation.md; docs/intermediate-representation.ir.md; docs/intermediate-representation.review.md; docs/records/intermediate-representation-history.md; docs/releases.md; docs/vocabulary.md

## Terms

T1. Intermediate representation (IR). defined-at: vocabulary.md#def-intermediate-representation [decided: owner, 2026-10-24]

T2. Reasoning role. defined-at: vocabulary.md#def-reasoning-role [decided: owner, 2026-10-24]

T3. Paraphraser. defined-at: vocabulary.md#def-paraphraser [decided: owner, 2026-10-24]

T4. Stranger. defined-at: vocabulary.md#def-stranger [decided: owner, 2026-10-23]

T5. Reader catalog. defined-at: style.md#readers [decided: owner, 2026-10-26]

T6. Convergence. defined-at: vocabulary.md#def-convergence [decided: owner, 2026-10-23]

T7. Definition site. defined-at: vocabulary.md#def-definition-site [decided: owner, 2026-10-26]

T8. Provenance status. defined-at: vocabulary.md#def-provenance-status [decided: owner, 2026-10-27]

T9. Referent. defined-at: vocabulary.md#def-referent [decided: owner, 2026-10-27]

T10. Cluster. defined-at: vocabulary.md#def-cluster [decided: owner, 2026-10-27]

T11. Render map. defined-at: vocabulary.md#def-render-map [decided: owner, 2026-10-27]

T12. Review record. defined-at: vocabulary.md#def-review-record [decided: owner, 2026-10-27]

T13. Round. defined-at: vocabulary.md#def-round [decided: owner, 2026-10-27]

T14. Count. defined-at: vocabulary.md#def-count [decided: owner, 2026-10-27]

T15. Meta-review. defined-at: vocabulary.md#def-meta-review [decided: owner, 2026-10-27]

T16. Footprint. defined-at: vocabulary.md#def-footprint [decided: owner, 2026-10-27]

T17. Register fact. defined-at: vocabulary.md#def-register-fact [decided: owner, 2026-10-27]

T18. Normative text. defined-at: vocabulary.md#def-normative-text [decided: owner, 2026-10-27]

T19. Limit. defined-at: vocabulary.md#def-limit [decided: owner, 2026-10-27]

T20. Meta-review signal. defined-at: vocabulary.md#def-meta-review-signal [decided: owner, 2026-10-27]

T21. Restatement: the stranger's own account of the text, in at most 200 words, written before the stranger reads the IR. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-restatement [decided: owner, 2026-10-27]

T24. Passage. defined-at: vocabulary.md#def-passage [decided: owner, 2026-10-30]

T25. Topic claim. defined-at: vocabulary.md#def-topic-claim [decided: owner, 2026-10-30]

T26. Confirmation. defined-at: vocabulary.md#def-confirmation [decided: owner, 2026-10-30]

T27. Project-specific term. defined-at: intermediate-representation.md#project-specific-term [decided: pipeline schema v1.2, 2026-10-25]

T28. Withdrawal. defined-at: vocabulary.md#def-withdrawal [decided: owner, 2026-10-30]

T29. Decision on a finding. defined-at: vocabulary.md#def-decision-on-a-finding [decided: owner, 2026-10-30]

T30. Omission. defined-at: vocabulary.md#def-omission [decided: owner, 2026-10-30]

T31. Fix pass. defined-at: vocabulary.md#def-fix-pass [decided: owner, 2026-10-30]

T32. New defect. defined-at: vocabulary.md#def-new-defect [decided: owner, 2026-10-30]

T35. Awaiting restatement: the review-record mark on a structural fix, owed to a recurring mismatch, whose hold no later restatement has yet tested. defined-at: https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-awaiting-restatement [decided: owner, 2026-10-30]

T36. IR-only. defined-at: vocabulary.md#def-ir-only-document [decided: owner, 2026-10-30; renamed at count 6's acceptance to match C13, C217 and C219]

T37. Structural fix. defined-at: intermediate-representation.md#structural-fix [decided: owner, 2026-10-29]

T38. Paraphrase test. defined-at: intermediate-representation.md#paraphrase-test [decided: owner, 2026-11-02, case 015 terms by the default]

T39. Term the text introduces: a term the text defines or links to a vocabulary entry. [proposed: this IR]

## Claims

### Plain purpose

C305. This specification says how a text is first written as a numbered list of statements, then turned into prose and reviewed by fresh readers. [inferred: R85]

C306. Agents that write or review such texts read this specification, and so does the human owner who decides on its rules. [inferred: R86]

### Purpose and scope

C1. For each text that requires an IR, the reasoning role writes the IR before any prose of the text exists. [decided: owner, 2026-10-30]

C4. The IR prevents three failure modes of directly written prose: claims compressed into one sentence, referents left unnamed, and conversation terms used as if defined. [decided: owner, 2026-10-24]

C5. Any project that adopts W-009 (the methodology corpus writes its deliverables IR first) by declaration uses this specification. [decided: owner, 2026-11-01]
C149. W-009 requires this specification. [decided: methodology PR #49, 2026-10-26]

C150. The specification's status is active. [decided: methodology PR #49, 2026-10-26]

C179. The specification is a methodology Specification, the document type. [decided: methodology PR #49, 2026-10-26]

C151. The reader is assumed to know W-008 (reports map their deliverables), P-008 (terms are defined once and linked at first use) and the style guide. [decided: owner, 2026-11-01]
C166. The human owner reads the specification as RD-4 does. [decided: methodology PR #49, 2026-10-26]

C175. RD-4 reads the specification in the reasoning, paraphraser or stranger role. [decided: methodology PR #49, 2026-10-26]

C6. A case this specification does not name is decided by the human owner when accepting the deliverable. [decided: owner, 2026-10-27]

### Document form

C7. An IR is a markdown file named `<subject>.ir.md`. [decided: pipeline schema v1.2, 2026-10-25]

C8. The IR sits beside the prose it produces, or under `docs/records/` when the prose is a chat message or a PR body. [decided: owner, 2026-10-24]

C9. The IR opens with header fields. [decided: pipeline schema v1.2, 2026-10-25]

C167. The IR holds five sections in a fixed order: Terms, Claims, Relations, Evidence, Asks. [decided: pipeline schema v1.2, 2026-10-25]

C10. The Claims section may use any sub-headings. [decided: pipeline schema v1.2, 2026-10-25]

C11. The Reader header holds one reader catalog identifier. [decided: pipeline schema v1.2, 2026-10-25]

C12. The Purpose header holds `report` or `document`, then one sentence saying what the text is for. [decided: owner, 2026-10-30]

C13. The Status header holds one of `draft`, `reviewed`, `rendered`, `delivered` or `delivered IR-only`. [decided: owner, 2026-10-30; reworded in count 7, round 1]

C338. The status may be followed by a parenthesis holding the counts this specification asks the reasoning role to record. [decided: owner, 2026-10-30; split from C13 in count 7, round 1]

C14. The Source header names the conversation, document or event that occasioned the IR. [decided: pipeline schema v1.2, 2026-10-25]

C15. The optional Normative header holds `yes` when the prose is normative text. [decided: owner, 2026-10-25]

C16. The optional Footprint header lists files or directories separated by semicolons. [decided: pipeline schema v1.3, 2026-10-26]

C142. A footprint directory ends in `/` and covers every file under it. [decided: pipeline schema v1.3, 2026-10-26]

C17. A `report` is read by someone who shares the conversation: RD-1 (the owner, in conversation), RD-2 (the owner, returning) or RD-3 (a delegating agent). [decided: pipeline schema v1.2, 2026-10-25; reworded in count 7, round 1]

C18. A `document` is read by someone who does not share the conversation: RD-4 (a fresh agent session) or RD-5 (an external reader). [decided: pipeline schema v1.2, 2026-10-25; reworded in count 7, round 1]

C19. Prose that will live under `docs/` is a `document`. [decided: owner, 2026-10-25]

### Element kinds

C20. Every element has an identifier and a body. [decided: pipeline schema v1.2, 2026-10-25]

C21. An identifier is a kind letter and a number, unique within the IR. [decided: pipeline schema v1.2, 2026-10-25]

C22. A split claim takes a new number, never a suffix. [decided: pipeline schema v1.2, 2026-10-25]

C23. A term element (`T`) holds the word or phrase and either `defined-at:` with a link to its definition site or its meaning in the text. [decided: owner, 2026-10-30]

C24. A term is defined once per IR. [decided: pipeline schema v1.2, 2026-10-25]

C25. Every project-specific term used in a claim appears as a term element. [decided: pipeline schema v1.2, 2026-10-25]

C27. A term without a definition site has status proposed. [decided: methodology PR #48, 2026-10-26]

C257. When the IR is the deliverable, the IR's own Asks section lists each proposed term for ratification. evidence: E7. [decided: owner, 2026-10-30]

C28. A claim element (`C`) makes one statement. [decided: pipeline schema v1.2, 2026-10-25]

C29. A claim may carry `evidence: E<n>`. [decided: pipeline schema v1.2, 2026-10-25]

C30. In a report to RD-1 or RD-2, `part: covered` or `part: changed` places a claim under *What is already covered* or *What changed*. [decided: pipeline schema v1.2, 2026-10-25; reworded after count 7 round 1 confirmation]

C31. A cluster element (`G`) holds `cluster:` and an ordered list of claim identifiers. [decided: owner, 2026-10-30]

C226. A topic claim is the claim that states the cluster's subject. [decided: owner, 2026-10-30]

C240. A cluster's list may open with a topic claim. [decided: owner, 2026-10-30]

C32. A claim belongs to at most one cluster. [decided: pipeline schema v1.2, 2026-10-25]

C33. A relation element (`R`) has the form `C<a> <verb> C<b> because <reason>`, with the verb one of `supports`, `depends-on`, `contradicts`, `refines`. [decided: pipeline schema v1.2, 2026-10-25]

C34. The reason of a relation is one sentence or a claim identifier. [decided: pipeline schema v1.2, 2026-10-25]

C36. An evidence element (`E`) holds a pointer (a file and line, a commit, a message date or a URL) with what the pointer shows. [decided: pipeline schema v1.2, 2026-10-25]

C37. Evidence is cited by a claim's `evidence:` field, never free-standing. [decided: pipeline schema v1.2, 2026-10-25]

C38. An ask element (`A`) holds a decision or action requested of the reader and `Depends:` naming the claims or asks the request rests on. [decided: pipeline schema v1.2, 2026-10-25]

C39. Every IR for RD-1 or RD-2 has an Asks section, holding asks or the single line `A0. No asks.` [decided: pipeline schema v1.2, 2026-10-25]

### The referent rule

C40. A claim names each referent inside itself. [decided: pipeline schema v1.2, 2026-10-25]

C42. The bare pronouns are it, this, that, these and those, with no noun after. [decided: pipeline schema v1.2, 2026-10-25]

C41. A bare pronoun inside a claim is legal only when its antecedent is a noun phrase earlier in the claim that holds the pronoun. [decided: owner, 2026-10-30]

C35. A reference from one claim to another is a relation, never a pronoun inside the claim. [decided: pipeline schema v1.2, 2026-10-25]

C163. The bare determiner phrases are the word "the" followed by other, above, former, latter or same, with no noun after. [decided: pipeline schema v1.2, 2026-10-25]

C231. A bare determiner phrase inside a claim is legal only when its antecedent is a noun phrase earlier in the claim that holds the phrase. [decided: owner, 2026-10-30]

C43. A determiner followed by the noun it names, such as "this specification", is not bare. [decided: methodology PR #49, 2026-10-26]

### Provenance

C259. A term carries a provenance status. [decided: owner, 2026-11-01]
C292. A claim carries a provenance status. [decided: owner, 2026-11-01]
C293. A cluster carries a provenance status. [decided: owner, 2026-11-01]
C260. A relation carries no provenance status. [decided: owner, 2026-11-01]
C294. An evidence element carries no provenance status. [decided: owner, 2026-11-01]
C295. An ask carries no provenance status. [decided: owner, 2026-11-01]
C44. The status is the last thing in the element, in square brackets. [decided: owner, 2026-11-01]
C165. A relation is the reasoning role's inference by definition. [decided: pipeline schema v1.2, 2026-10-25]

C46. The status decided, written `[decided: <who>, <date>]` or `[decided: <source>]`, marks an element ratified by the human owner or quoted from a document the human owner ratified. [decided: owner, 2026-10-30]

C48. The status inferred, written `[inferred: R<n>]`, marks an element the reasoning role derived, citing the relation that derives it. [decided: pipeline schema v1.2, 2026-10-25]

C47. The status proposed, written `[proposed: <IR id or "this IR">]`, marks an element put forward and awaiting ratification. [decided: pipeline schema v1.2, 2026-10-25]

C49. A term with status proposed is an unratified term. [decided: pipeline schema v1.2, 2026-10-25]

C50. The count of unratified terms is the mechanical measure of unratified vocabulary, one indicator of convergence. [decided: owner, 2026-10-23]

### Mechanical checks

C303. The IR has sixteen mechanical checks, one per row of the table below. [inferred: R84]

C51. A checking program or a stranger reports each mechanical check as a finding. [decided: pipeline schema v1.2, 2026-10-25; reworded in count 7, round 7]

C52. methodology-tools runs the checks as `mtool ir check`. [decided: methodology PR #48, 2026-10-26]

C53. CK-01, referent rule, fires when a claim contains a bare form of the referent rule with no noun-phrase antecedent earlier in that claim. [decided: pipeline schema v1.2, 2026-10-25]

C54. CK-02, claim length, fires when a claim exceeds 40 words. [decided: pipeline schema v1.2, 2026-10-25]

C55. CK-03, compound claim, fires when a claim joins two clauses that could each stand as a claim, by `and`, `but`, `so`, a semicolon or an em-dash. [decided: pipeline schema v1.2, 2026-10-25]

C56. For CK-03, a semicolon or a final `, and` that follows a colon separates list items and is not a join. [decided: methodology PR #49, 2026-10-26]

C57. CK-04, undefined term, fires when a project-specific term appears in a claim and is neither a term element nor linked to a definition site. [decided: pipeline schema v1.2, 2026-10-25]

C58. For CK-04, a project-specific term is a bolded term or a capitalized multi-word phrase that is not the name of a person, product or place. [decided: owner, 2026-10-30]

C232. For CK-04, a term in the project's `docs/vocabulary.md` is also a project-specific term. [decided: owner, 2026-10-30]

C59. CK-05, provenance, fires when a term, claim or cluster has no status, or a status without its required fields. [decided: pipeline schema v1.2, 2026-10-25]

C60. CK-06, dangling reference, fires when a relation, cluster, `evidence:` or `Depends:` names an identifier that does not resolve. [decided: pipeline schema v1.2, 2026-10-25]

C61. CK-07, header, fires when the Reader header is not a catalog identifier or the Purpose header lacks `report` or `document`. [decided: pipeline schema v1.2, 2026-10-25]

C62. CK-08, asks section, fires when an IR for RD-1 or RD-2 has no Asks section. [decided: pipeline schema v1.2, 2026-10-25]

C63. CK-09, cluster membership, fires when a claim appears in two clusters. [decided: pipeline schema v1.2, 2026-10-25]

C64. CK-10, section order, fires when the five sections are absent or out of order. [decided: pipeline schema v1.2, 2026-10-25]

C65. CK-11, definition site, fires when a term's `defined-at:` target does not resolve. [decided: pipeline schema v1.2, 2026-10-25]

C66. CK-12, identifier uniqueness, fires when two elements carry one identifier. [decided: methodology PR #49, 2026-10-26]

C67. CK-13, term uniqueness, fires when two term elements name one term. [decided: owner, 2026-10-26]

C68. CK-14, review record, fires when an IR whose Status is `reviewed` or `delivered` after rounds has no review record beside it, or a review record without a verdict per round. [decided: owner, 2026-10-26]

C69. CK-15, round trip, fires when the render map omits a claim, names an identifier the IR does not hold, or is absent from paraphrased prose. [decided: pipeline schema v1.4, 2026-10-26]

C70. CK-16, element form, fires when a line inside a section is neither an element, a heading, a continuation of the element above, nor a comment. [decided: pipeline schema v1.4, 2026-10-26]

### Rendering and review

C71. Prose is rendered from the IR when a rendering condition selects rendering. [decided: owner, 2026-10-24]

C72. The paraphraser renders one claim as one sentence. [decided: pipeline schema v1.2, 2026-10-25]

C174. The paraphraser renders one cluster as one paragraph in the cluster's order or, when its claims fall under different parts, as one paragraph per part. [decided: owner, 2026-10-30; reworded in count 7, round 4]

C73. The paraphraser introduces no new claim. [decided: pipeline schema v1.2, 2026-10-25]

C180. The paraphraser drops no claim. [decided: pipeline schema v1.2, 2026-10-25]

C74. The paraphraser may add connective prose: a sentence that asserts nothing the IR holds and exists to join claims. [decided: pipeline schema v1.2, 2026-10-25]

C75. The paraphraser renders no relation and no evidence as a sentence. [decided: pipeline schema v1.2, 2026-10-25; reworded in count 7, round 3]

C220. The renderer is the paraphraser or, for normative text, the reasoning role. evidence: E4. [decided: owner, 2026-10-30]

C76. The renderer links a term with a definition site at its first use in the unit. [inferred: R44]

C173. The unit for P-008 is the whole text for a report and the section for a document. [decided: methodology PR #48, 2026-10-26]

C164. The renderer does not link a later use of a term with a definition site. [decided: owner, 2026-11-01]
C77. The renderer defines a term with no definition site in a sentence of its own before its first use. [inferred: R45]

C153. When a report delivers the text, the reasoning role lists under *Terms introduced* each term with no definition site, for ratification. [decided: owner, 2026-11-01; reworded after count 7 round 1 confirmation; reworded in count 7, round 6]
C78. For RD-5, the first use of a term with a definition site carries its definition in parentheses instead of a link. [decided: methodology PR #48, 2026-10-26]

C79. For RD-1 or RD-2, the renderer places a claim under the part its `part:` field names. [inferred: R46]

C80. Without a `part:` field, a decided claim renders under *What is already covered*. [decided: methodology PR #50, 2026-10-26]

C154. Without a `part:` field, a proposed or inferred claim renders under *What changed*. [decided: methodology PR #50, 2026-10-26]

C81. When rendering, the renderer follows the style guide's rows for the IR's reader. [decided: pipeline schema v1.2, 2026-10-25]

C82. The renderer states an empty Asks section as "No asks." [inferred: R47]

C83. The paraphraser appends a render map as one comment line reading `render map:` and, per claim, the paragraph it landed in, as `C1→¶1 C2→¶1 …`. [decided: pipeline schema v1.2, 2026-10-25]

C176. A paraphrase could change the force of normative text. [decided: owner, 2026-10-25]

C85. When the reasoning role renders, it appends the render map in the paraphraser's form. [decided: owner, 2026-10-27]

C86. The reasoning role makes a fix to rendered prose in the IR first. [decided: owner, 2026-10-27]

C169. After a fix to the IR, the reasoning role renders the prose again or edits it to match the IR. [decided: owner, 2026-10-27]

C87. The reasoning role rephrases or removes words in a fix to prose before it adds words. evidence: E2. [decided: owner, 2026-10-30]

C340. A state header names whether the sentences under it state what is done now or what the text aims at. [decided: owner, 2026-11-02, case 015 change 14; added after count 7 round 2 confirmation]

C143. The reasoning role adds words in a fix only for a missing definition or referent, a state header, or a rewording note. evidence: E2, E9. [decided: owner, 2026-11-02, case 015 change 14; reworded after count 7 round 2 confirmation]

C279. The reasoning role adds no rule in a fix beyond the changes the owner adopted for the count. evidence: E8. [decided: owner, 2026-11-01]
C280. When a finding needs a new rule, the reasoning role lists the finding for the owner with a proposed wording. evidence: E8. [decided: owner, 2026-11-01]
C281. Until the owner decides, a finding that needs a new rule counts against the verdict only under the verdict's four conditions. evidence: E8. [decided: owner, 2026-11-01; reworded in count 7, round 6]
C317. When the fix a finding needs would change a decided claim, the reasoning role does not write a claim around the finding. evidence: E9. [decided: owner, 2026-11-02, case 015 change 5, from case 013 change 1]
C318. The reasoning role puts such a finding to the owner with a proposed wording. evidence: E9. [decided: owner, 2026-11-02, case 015 change 5, from case 013 change 1; reworded in count 7, round 6]
C346. The fix of such a finding waits for the owner's answer. evidence: E9. [decided: owner, 2026-11-02, case 015 change 5, from case 013 change 1; split from C318 in count 7, round 6]
C319. The next round opens after the owner answers that finding. evidence: E9. [decided: owner, 2026-11-02, case 015 change 5, from case 013 change 1]

C282. When a fix rewords a decided claim, the reasoning role keeps the claim's decided source. evidence: E8. [decided: owner, 2026-11-01]
C304. The reasoning role notes the rewording as `reworded in count N, round M`. evidence: E8. [decided: owner, 2026-11-01]
C283. The owner's acceptance of a text ratifies the text's reworded decided claims, unless the owner names one. evidence: E9. [decided: owner, 2026-11-02, case 015 change 19]
C307. When a fix separates the present from what the text aims at, the reasoning role moves the sentence under a state header. [decided: owner, 2026-11-02, case 015 change 15; reworded after count 7 round 2 confirmation]
C308. In a fix, the reasoning role does not mark a single sentence with "Today". evidence: E9. [decided: owner, 2026-11-02, case 015 change 15]
C309. In a fix, the reasoning role keeps the connective prose that joins a rule to a reason the IR holds as its own claim. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15]
C313. When a fix brings in a term no vocabulary or IR element defines, the reasoning role adds it, as proposed, to the IR's Terms section. [decided: owner, 2026-11-02, case 015 change 5, from case 013 change 3; reworded in count 7, round 1; reworded after count 7 round 2 confirmation]
C310. The fix rules govern every fix, including an edit outside a round to an IR whose Status is reviewed. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15]
C311. In an edit outside a round to a reviewed IR, the reasoning role cuts each claim the edit makes a duplicate. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15]
C312. In an edit outside a round to a reviewed IR, the reasoning role amends each claim the edit makes stale. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15]
C314. The renderer lists each IR term defined outside the methodology vocabulary and the project's `docs/vocabulary.md` in a Terms section before the body. evidence: E9. [decided: owner, 2026-11-02, case 015 change 5, from case 013 change 2; reworded in count 7, round 6]
C315. Each entry of that Terms section gives the term, its IR definition and, when the term has a definition site, its link. evidence: E9. [decided: owner, 2026-11-02, case 015 change 5, from case 013 change 2; reworded after count 7 round 6 confirmation]
C316. When a term draws an undefined-term finding in two rounds, the reasoning role adds the term to that Terms section. [decided: owner, 2026-11-02, case 015 change 5, from case 013 change 2; reworded after count 7 round 2 confirmation]
### Stranger rounds

C88. The reasoning role runs a stranger review in rounds until a round returns the verdict readable or the count reaches the limit. [decided: owner, 2026-10-30]

C89. The limit is ten rounds. [decided: owner, 2026-10-26]

C90. The rounds apply to every stranger review the rendering conditions select. [decided: owner, 2026-10-26]

C91. The reasoning role starts each round by dispatching a stranger with a fresh context, never itself and never an earlier round's instance. [decided: methodology PR #50, 2026-10-26]

C92. The stranger reviews the IR and the prose against the reader's readability test. [decided: methodology PR #50, 2026-10-26]

C266. In each round's brief to the stranger, the reasoning role lists each passage awaiting restatement. evidence: E8, E9. [decided: owner, 2026-11-02, case 015 change 16]
C267. Before reading the IR, the stranger restates each listed passage in one sentence. evidence: E8. [decided: owner, 2026-11-01]
C268. The reasoning role checks each listed passage's structural fix against the stranger's one-sentence restatement of the passage. evidence: E8, E9. [decided: owner, 2026-11-02, case 015 change 16]
C339. A round is one stranger's review of the text and the fixes made after that review. [decided: owner, 2026-11-02, case 015 change 26; reworded in count 7, round 4]


C211. A restatement mismatch is a disagreement the stranger finds between its restatement and the IR. [decided: owner, 2026-10-27; reworded in count 7, round 1]

C263. A claim or a qualifier the restatement leaves out is an omission, not a restatement mismatch. evidence: E8. [decided: owner, 2026-11-01]
C264. A restatement that says a rule has no qualifier the IR holds has a mismatch. evidence: E8. [decided: owner, 2026-11-01]
C228. A passage is the prose sentences that carry one claim or one cluster. [decided: owner, 2026-10-30]

C290. The round's stranger instance is the stranger the reasoning role dispatched for the round. [inferred: R83]

C233. Confirmation is the step at which the round's stranger instance says whether each fix holds. [decided: owner, 2026-10-30]

C258. At confirmation, the round's stranger instance withdraws a finding other than a restatement mismatch by saying the finding no longer applies to the prose. [decided: owner, 2026-10-30]

C93. In a round, the verdict is readable when four conditions hold. evidence: E9. [decided: owner, 2026-11-02, case 015 change 26; reworded in count 7, round 2]
C203. The first condition: the restatement has no restatement mismatch with the IR. evidence: E8. [decided: owner, 2026-11-01]
C227. Each restatement mismatch counts against the verdict. evidence: E8. [decided: owner, 2026-11-01]
C195. The round's stranger instance never withdraws a restatement mismatch at confirmation. evidence: E3. [decided: owner, 2026-10-30]

C265. An omission does not count against the verdict. [inferred: R80]

C221. The second condition: the stranger finds no contradiction. [decided: owner, 2026-10-30]

C194. Each contradiction finding counts against the verdict, unless the round's stranger instance withdrew the finding at confirmation on a reason that quotes the prose. evidence: E3. [decided: owner, 2026-11-01]
C234. The third condition: the stranger finds no undefined term, a term neither defined in the text nor linked to a definition site. [decided: owner, 2026-10-30; reworded in count 7, round 2]

C235. Each undefined-term finding counts against the verdict, unless the round's stranger instance withdrew the finding at confirmation on a reason that quotes the prose. evidence: E3. [decided: owner, 2026-11-01]
C328. The paraphrase test asks the stranger to restate the text for the human reader the Reader line names, without any term the text introduces. [decided: owner, 2026-11-02, case 015 change 26; reworded in count 7, round 1]

C341. A term the text introduces is one the text defines or links to a vocabulary entry. [proposed: this IR]
C337. The fourth condition: the stranger's restatement passes the paraphrase test. evidence: E9. [decided: owner, 2026-11-02, case 015 change 26]
C329. Each passage the stranger cannot restate without a term the text introduces counts against the verdict. evidence: E9. [decided: owner, 2026-11-02, case 015 change 26]
C330. In each round's brief, the reasoning role names the human reader the text's Reader line names. evidence: E9. [decided: owner, 2026-11-02, case 015 change 26]
C331. The review record keeps each restatement as written. evidence: E9. [decided: owner, 2026-11-02, case 015 change 26]
C94. The reasoning role treats a finding that proposes fewer words, a plainer phrase or a removed repetition like any other finding. [inferred: R48]

C95. The reasoning role records in the review record each round's findings, the verdict, and the reasoning role's own decision on each finding. [decided: owner, 2026-10-30; reworded in count 7, round 3]

C261. The reasoning role's decision on a finding is one of two: fixed, or declined with a reason. [decided: owner, 2026-10-30]

C262. A confirmed or unfixed mark is not a decision on a finding: the mark records whether the round's stranger instance confirmed a fix. [inferred: R79]

C155. The text delivered after a readable verdict is the text that round read, with the round's fixes applied. [decided: owner, 2026-10-27; reworded in count 7, round 4]

C97. At a readable verdict, the reasoning role fixes each finding not waiting for the owner, IR first, under the fix rules. [decided: owner, 2026-10-27; reworded after count 7 round 5 confirmation; reworded in count 7, round 7]

C345. At a readable verdict, a finding whose fix waits for the owner stays unfixed. [inferred: R88]

C347. The reasoning role lists that finding for the owner. [inferred: R89]

C156. At a readable verdict, the round's stranger instance confirms each fix not marked awaiting restatement. evidence: E8, E9. [decided: owner, 2026-11-02, case 015 change 16]
C301. When a readable round's fix pass marks a structural fix awaiting restatement, the reasoning role keeps the mark. evidence: E8, E9. [decided: owner, 2026-11-02, case 015 change 16; reworded in count 7, round 6]

C302. The reasoning role lists the passage of a fix still awaiting restatement at a readable verdict in the next count's round 1 brief. evidence: E8, E9. [decided: owner, 2026-11-02, case 015 change 16]

C182. A finding whose fix the readable round's stranger instance does not confirm is unfixed. [decided: owner, 2026-10-27]

C202. The reasoning role marks each finding of the readable round confirmed or unfixed in the review record. evidence: E9. [decided: owner, 2026-11-02, case 015 change 14]

C248. An unconfirmed fix's words stay in the delivered prose. [decided: owner, 2026-10-30]

C183. The reasoning role fixes an unfixed finding of the readable round at the next edit of an active document. [decided: owner, 2026-10-27]

C254. At that edit, the reasoning role revises the unconfirmed words. [decided: owner, 2026-11-01]
C291. The next count's stranger instances review the revised words. [decided: owner, 2026-11-01]
C98. After a verdict of not readable, the reasoning role fixes the IR and then the prose. [decided: owner, 2026-10-26]

C157. The next round reviews the fixed IR and the fixed prose. [decided: owner, 2026-10-26]

C320. A structural fix is one of two fixes for a misreading that a rewording does not settle. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15; reworded in count 7, round 5]
C344. The first structural fix moves the sentence out of the structure that produces the misreading: a list, a section or an adjacency. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15; split from C320 in count 7, round 5]
C321. The second structural fix changes the claim to the reading of the mismatched restatements, when that reading is true. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15; reworded in count 7, round 6]
C323. When restatement mismatches name one claim in two rounds, the reasoning role makes a structural fix before the next round. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15 and change 3; reworded in count 7, round 6; reworded after count 7 round 7 confirmation]
C348. The two rounds may fall in one count or across two. evidence: E9. [decided: owner, 2026-11-02, case 015 change 3; split from C323 after count 7 round 7 confirmation]
C324. The reasoning role marks the structural fix made for a recurring mismatch awaiting restatement in the review record. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15]
C325. A fix the round's stranger instance confirms only in part counts as a fix not held. [decided: owner, 2026-11-02, case 015 change 15; reworded in count 7, round 1]

C269. A fix pass is the reasoning role's fixes of one round's findings, in the IR and then in the prose. evidence: E8. [decided: owner, 2026-11-01]
C327. Each project that runs rounds names, in its own documents, the checks that run after each fix pass and the lines the review record holds. [decided: owner, 2026-11-02, case 015 change 16; reworded in count 7, round 1]
C272. The reasoning role names the fix commit to the round's stranger instance. evidence: E8. [decided: owner, 2026-11-01]
C273. The round's stranger instance reads the prose and the IR at the fix commit, in full, before answering. evidence: E8. [decided: owner, 2026-11-01]
C274. A new defect is a defect a fix introduces. evidence: E8. [decided: owner, 2026-11-01]
C297. The round's stranger instance names each new defect at confirmation. evidence: E8. [decided: owner, 2026-11-01]
C275. The next round opens after the reasoning role records the round's confirmation. evidence: E8. [decided: owner, 2026-11-01]
C298. Before the next round opens, the reasoning role makes the fixes the confirmation calls for. evidence: E8. [decided: owner, 2026-11-01]
C99. At the limit the reasoning role does not deliver the text before the owner's decision. [decided: owner, 2026-10-26]

C197. At the limit, the reasoning role fixes the final round's findings in the IR and then in the prose. evidence: E3. [decided: owner, 2026-10-29]

C198. The final round's stranger instance confirms each fix not marked awaiting restatement before the owner's decision. evidence: E3, E9. [decided: owner, 2026-11-02, case 015 change 15]

C199. The reasoning role marks each finding of the final round confirmed or unfixed in the review record. evidence: E3. [decided: owner, 2026-10-30]
C326. At the limit, a fix still awaiting restatement in the final round counts as unfixed. evidence: E9. [decided: owner, 2026-11-02, case 015 change 15]

C276. At a readable verdict and at the limit, the reasoning role does not fix in the count a new defect the confirmation names. evidence: E8. [decided: owner, 2026-11-01]
C277. The reasoning role lists each new defect of that confirmation for the owner. evidence: E8. [decided: owner, 2026-11-01]
C278. The reasoning role fixes the new defect in the next edit of the text. evidence: E8. [decided: owner, 2026-11-01]
C158. At the end of a count, the reasoning role sets the IR's Status to `reviewed`. [decided: owner, 2026-10-27]

C144. At the limit the reasoning role states in the review record that the limit was reached. [decided: owner, 2026-10-26]

C101. Rework is an edit of the IR and the text by the reasoning role. [decided: owner, 2026-10-27]

C100. The owner decides, when accepting or rejecting a text at the limit, whether the text is delivered, reworked or withdrawn. [decided: owner, 2026-10-26]

C186. When the owner decides delivery, the reasoning role delivers the text. [decided: owner, 2026-10-26]

C171. Rework starts a new count from round one. [decided: owner, 2026-10-27]

C172. The reasoning role keeps the ended count's review record through rework. [decided: owner, 2026-10-27]

C102. When the text at the limit is an amendment, the owner decides under Article 8 (amendments, versions, and migration). [decided: owner, 2026-10-30; reworded after count 7 round 6 confirmation]

C103. The review record holds, per round, the word count of the prose and the claim count of the IR. [decided: owner, 2026-10-27]

### Meta-review


C333. The owner decides whether a meta-review runs. evidence: E9. [decided: owner, 2026-11-02, case 015 change 17]

C332. At the end of a count, the reasoning role reports to the owner the meta-review signals that fired, or that the count reached the limit. evidence: E9. [decided: owner, 2026-11-02, case 015 change 17]

C192. The owner may dispatch a meta-review of any text. [decided: owner, 2026-10-27]

C187. The first signal: in two or more rounds, a fix was not held at confirmation. evidence: E4, E9. [decided: owner, 2026-11-02, case 015 change 2]

C188. The second signal: a finding declined in an earlier round was raised again. [decided: owner, 2026-10-27]

C208. The second signal also fires when restatement mismatches named one claim in two rounds, whether in one count or across two. evidence: E9. [decided: owner, 2026-11-02, case 015 change 3; reworded in count 7, round 6; reworded in count 7, round 7]

C190. The fourth signal: in round 3 or later, a stranger found a contradiction in a passage an earlier round's fix touched. evidence: E3. [decided: owner, 2026-10-29]

C284. Communication-pipeline evaluation case 012 struck the third signal, a measure of the prose's growth per IR claim, on 2026-10-30. evidence: E8. [decided: owner, 2026-11-01; reworded in count 7, round 3]
C288. The first, second and fourth signals keep their numbers. [inferred: R81]

C105. At the end of a count, the reasoning role checks the signals against the review record. evidence: E8. [decided: owner, 2026-11-01]
C191. The reasoning role writes `Meta-review: pending` when a signal fired or the count reached the limit. evidence: E9. [decided: owner, 2026-11-02, case 015 change 17]

C239. When no signal fired and the count did not reach the limit, the reasoning role writes `Meta-review: not indicated`. evidence: E9. [decided: owner, 2026-11-02, case 015 change 17]

C209. The `Meta-review:` line names the signals checked. [decided: owner, 2026-10-27]
C334. The `Meta-review:` line takes one of three values: pending, not indicated or delivered. evidence: E9. [decided: owner, 2026-11-02, case 015 change 17]
C335. A check that cannot read a review-record line stops with an error. evidence: E9. [decided: owner, 2026-11-02, case 015 change 17]
C336. The reasoning role corrects an unreadable review-record line before writing the `Meta-review:` line. evidence: E9. [decided: owner, 2026-11-02, case 015 change 17]

C107. A session the owner starts, the meta-review session, performs the meta-review. [decided: owner, 2026-10-26]

C108. The meta-review session delivers the meta-review as a report to the owner. [decided: owner, 2026-10-27]

C159. On delivery of the meta-review, the reasoning role sets the review record's line to `Meta-review: delivered` with a link. [decided: owner, 2026-10-27]

C109. A `Meta-review: pending` line in an accepted deliverable's review record is a finding of the next form audit under Article 9 (audits). [decided: owner, 2026-11-02, case 015 change 17; reworded in count 7, round 1]

### Rendering conditions

C246. The rendering conditions settle, for one IR, whether prose is rendered, who renders it and whether the stranger rounds run. [inferred: R66]

C204. A dependent ask is an ask with a `Depends:` field. [decided: pipeline branch point v1.1, 2026-10-25]

C110. The inputs are the IR's reader, purpose, Normative header, claim count, proposed-term count, count of dependent asks, longest claim and two owner inputs. [decided: owner, 2026-10-30]

C205. The first owner input is whether the owner asked for a review. [decided: owner, 2026-10-30]

C229. The second owner input is whether the owner designated the document IR-only. [decided: owner, 2026-10-30]

C111. A checking program runs the mechanical checks in every case. [decided: pipeline schema v1.2, 2026-10-25; reworded in count 7, round 7]

C112. The first row of the Rendering conditions table whose condition holds decides. [decided: methodology PR #50, 2026-10-26]

C113. When the header carries `Normative: yes`, the reasoning role renders and runs the stranger rounds. [decided: owner, 2026-10-26]

C114. When the owner asked for a review, or the purpose is `document`, or the reader is RD-4 or RD-5, the paraphraser renders. [decided: pipeline branch point v1.1, 2026-10-25]

C170. When the owner asked for a review, or the purpose is `document`, or the reader is RD-4 or RD-5, the stranger rounds run. [decided: pipeline branch point v1.1, 2026-10-25]

C115. When proposed terms exceed zero, the paraphraser renders, with the ratification ask. [decided: pipeline branch point v1.1, 2026-10-25]

C116. When the reader is RD-2, the paraphraser renders. [decided: pipeline branch point v1.1, 2026-10-25]

C117. When the reader is RD-1 and the IR has more than six claims, a dependent ask, or a claim over 30 words, the paraphraser renders. [decided: pipeline branch point v1.1, 2026-10-25]

C118. When the reader is RD-3 and the IR has more than twelve claims or a dependent ask, the paraphraser renders. [decided: pipeline branch point v1.1, 2026-10-25]

C119. Otherwise, for RD-1 or RD-3, the reasoning role delivers the IR as it stands. [decided: pipeline branch point v1.1, 2026-10-25]

C120. The counts in the conditions are provisional. [decided: methodology PR #49, 2026-10-26]

C145. A change to a count is an editorial change while it changes no obligation. [decided: methodology PR #49, 2026-10-26]

### The footprint

C121. An IR whose deliverable is a chat message has no footprint. [decided: pipeline schema v1.3, 2026-10-26]

C177. No branch carries a chat message. [decided: pipeline schema v1.3, 2026-10-26]

C122. When the Footprint header is absent or empty, no comparison is made. [decided: pipeline schema v1.3, 2026-10-26]

C123. Before delivery, the reasoning role, or a checking program, compares the Footprint header with the files the branch changed since its base. [decided: pipeline schema v1.3, 2026-10-26; reworded in count 7, round 7]

C124. A file is changed when the branch's diff adds, modifies, deletes or renames it. [decided: pipeline schema v1.3, 2026-10-26]

C146. The IR and its review record are not counted as changed files. [decided: pipeline schema v1.3, 2026-10-26]

C125. A changed file that no declared entry covers is a surprise. [decided: pipeline schema v1.3, 2026-10-26]

C126. A declared file that did not change, or a declared directory under which no file changed, is a miss. [decided: pipeline schema v1.3, 2026-10-26]

C127. The counts of surprises and misses measure one indicator of convergence: how far the footprint's prediction missed. [decided: owner, 2026-10-23]

C128. The reasoning role records the unratified-term count, the surprise count and the miss count in the Status parenthesis when the IR is delivered. [decided: pipeline schema v1.3, 2026-10-26]

### When an IR is required

C129. A document always starts as an IR. [decided: owner, 2026-10-25]

C130. A report to RD-2 always starts as an IR. [decided: pipeline branch point v1.1, 2026-10-25]

C131. A report to RD-1 or RD-3 that introduces no term, records no decision and states no register fact may be written as prose directly. [decided: owner, 2026-10-25]

C342. A register fact is a statement about the state of a register or of a row in one. [decided: methodology vocabulary, register fact; added in count 7, round 3]

C206. The reasoning role runs the style guide's mechanical checks on prose it writes directly. [decided: owner, 2026-10-30]

C132. A term, a decision or a register fact requires the IR. [decided: owner, 2026-10-25]

C178. A term, a decision and a register fact are each content a model would hold. [decided: owner, 2026-10-25]

### Lifecycle

C133. An IR's mutability follows the state of its prose: active or delivered. [decided: pipeline schema v1.2, 2026-10-25]

C134. The reasoning role edits the IR of an active document whenever the document is edited. [decided: pipeline schema v1.2, 2026-10-25]

C160. A disagreement between an active document and its IR is a defect in the prose. [decided: pipeline schema v1.2, 2026-10-25]

C135. The IR of a delivered report is a record. [decided: pipeline schema v1.2, 2026-10-25]

C185. At delivery, the reasoning role sets the Status of a report's IR to `delivered`. [decided: pipeline schema v1.2, 2026-10-25]

C161. The reasoning role does not edit the IR of a delivered report. [decided: owner, 2026-10-30]

C136. On ratification, the reasoning role adds a row with a `def-` anchor for the ratified term to the project vocabulary. [decided: methodology PR #48, 2026-10-26]

C181. The vocabulary row of a ratified term is the term's definition site. [decided: methodology PR #48, 2026-10-26]

### IR-only documents (added 2026-10-30)

C217. A document the owner designates IR-only, whose header does not carry `Normative: yes`, is delivered as its IR with no rendering and no stranger rounds. [decided: owner, 2026-10-30]

C218. An IR-only document's Status reads `delivered IR-only`. [decided: owner, 2026-10-30]

C219. CK-14 exempts an IR whose Status is `delivered IR-only`. [decided: owner, 2026-10-30]

## Relations

R1. C6 refines C4 because an unnamed case is decided by the owner instead of by an added paragraph.

R2. C27 depends-on C47 because an inline definition is the rendering of a proposed status.

R3. C35 refines C40 because a cross-claim reference is a referent the relation names.

R4. C50 depends-on C49 because the indicator counts unratified terms.

R5. C71 depends-on C110 because the conditions decide whether rendering happens.

R6. C220 refines C72 because normative text swaps the renderer and keeps the rule of one claim per sentence.

R30. C176 supports C220 because the risk to force is the reason for the renderer.

R31. C177 supports C121 because a footprint is a branch comparison.

R32. C178 supports C132 because model content is what the IR holds.

R7. C85 refines C83 because the renderer changes and the map stays.

R8. C86 supports C134 because fixing the IR first keeps the two from disagreeing.

R9. C143 refines C87 because the two cases that need words are the exception to rephrasing.

R10. C93 refines C92 because the verdict is defined by restatement, not by finding count.

R11. C94 supports C87 because a reviewer that reports excess words lets fixes reduce them.

R12. C98 depends-on C86 because a fix after a round is a fix to rendered prose, made in the IR first.

R13. C101 refines C100 because rework is one of the owner's three outcomes.

R14. C102 refines C100 because, when the text is an amendment, Article 8 governs the owner's decision at the limit.

R16. C332 depends-on C88 because the count and its record exist only under the rounds rule.

R34. C187 refines C332 because each signal is one condition the reasoning role reports.

R35. C188 refines C332 because each signal is one condition the reasoning role reports.

R37. C190 refines C332 because each signal is one condition the reasoning role reports.

R17. C113 depends-on C220 because the first row selects the reasoning role as renderer.

R18. C116 depends-on C130 because the returning owner's report needs a state paragraph only the paraphraser writes.

R19. C128 depends-on C50 because the Status parenthesis holds the indicator readings.

R20. C128 depends-on C127 because the Status parenthesis holds the indicator readings.

R21. C69 depends-on C83 because the round-trip check reads the render map.

R23. C68 depends-on C95 because the check verifies the record the rounds produce.

R24. C129 depends-on C18 because a document is defined by its reader.

R25. C158 refines C13 because the status rule names when `reviewed` is set.

R27. C156 depends-on C97 because the instance confirms the fixes the reasoning role made.

R33. C183 depends-on C182 because the next edit owes what the instance did not confirm.

R28. C183 depends-on C161 because a delivered report has no next edit, so only an active document takes one.

R40. C194 refines C93 because a contradiction finding stops counting only when the round's stranger instance withdraws it on a reason that quotes the prose.

R41. C195 refines C194 because the confirming instance has read the IR and can no longer restate as a stranger.

R42. C197 refines C99 because the fixes precede the owner's decision that C99 waits for.

R43. C198 depends-on C197 because the instance confirms the fixes the reasoning role made.

R44. C76 depends-on C220 because the link is placed when the text is rendered, and the renderer renders; the source, methodology PR #48, names no actor.

R45. C77 depends-on C220 because the definition is written when the text is rendered, and the renderer renders; the source, methodology PR #46, names no actor.

R46. C79 depends-on C220 because the placement is made when the text is rendered, and the renderer renders; the source, the pipeline schema v1.2, names no actor.

R47. C82 depends-on C220 because the Asks section is stated when the text is rendered, and the renderer renders; the source, methodology PR #46, names no actor.

R48. C94 depends-on C95 because the reasoning role records its decision on each finding; the source, the owner's ratification of 2026-10-27 of a passive claim, names no actor.

R50. C202 depends-on C95 because the reasoning role records its decision on each finding; the source, communication-pipeline evaluation case 008 change 5 ("the record marks each confirmed or unfixed"), names no actor.

R53. C226 refines C31 because a cluster renders as one paragraph (C174), and the claim placed first states the paragraph's subject.

R54. C161 depends-on C134 because the reasoning role is the actor that edits an IR; the source, the pipeline schema v1.2, names no actor.

R55. C228 refines C266 because a claim renders as one sentence (C72) and a cluster as one paragraph (C174), so the prose that carries one of them is the unit a listed passage names.

R58. C233 refines C156 because the instance's confirming of each fix is the step the term names.

R59. C87 depends-on C86 because the reasoning role makes every fix to rendered prose, and the owner's ratification of 2026-10-27 named no actor.

R60. C143 depends-on C86 because the reasoning role makes every fix to rendered prose, and the owner's ratification of 2026-10-27 named no actor.

R61. C199 depends-on C197 because the reasoning role fixes the final round's findings and writes the review record, and case 009 change 18 named no actor.

R65. C88 depends-on C91 because the reasoning role starts each round; the owner's ruling of 2026-10-26 named no actor.

R66. C246 refines C71 because the table's rows decide when prose is rendered and by whom.

R68. C195 depends-on C233 because the round's stranger instance is the one that confirms and withdraws; case 009 change 2 named no actor.

R70. C164 depends-on C220 because the renderer places every link; methodology PR #48 named no actor.

R71. C248 depends-on C155 because the delivered text is the text the round read with the round's fixes applied, and C202 marks the fixes the instance did not confirm.

R72. C254 refines C183 because the next edit's fix of an unfixed finding changes the words the instance did not confirm.

R74. C206 depends-on C131 because the author who writes prose directly is the one who can run the checks on it; the owner's ruling of 2026-10-25 named no actor.

R77. C258 refines C194 because the withdrawal the second and third conditions exempt is the instance's own statement at confirmation, and the first condition's row excludes a restatement mismatch from it (C195).

R78. C261 refines C95 because the record holds the decision on each finding, and a finding is either fixed or declined.

R79. C262 refines C261 because the reasoning role marks a fix confirmed or unfixed from the instance's confirmation (C202, C199), while a decision on a finding is the reasoning role's own.

R80. C265 depends-on C263 because an omission is not a restatement mismatch, and only a mismatch counts under the first condition.

R81. C288 depends-on C284 because the review records of earlier counts name the first, second and fourth signals by number.

R83. C290 depends-on C91 because the reasoning role starts each round by dispatching a fresh stranger, and that stranger answers at the round's confirmation.

R84. C303 refines C51 because the table holds one row per check, CK-01 to CK-16, and a count stated in a sentence carries the number for a reader who skims the table.

R85. C305 refines C1 because the plain purpose states the Purpose section's rule without the specification's terms, the form communication-pipeline evaluation case 015 change 28 asks of a document.

R86. C306 refines C175 because the readers the Reader line names are agents in the three roles and the human owner.

R88. C345 depends-on C346 because the fix waits for the owner's answer and no next round opens at a readable verdict; C182 marks a finding whose fix is not confirmed unfixed.

R89. C347 depends-on C318 because the reasoning role has put the finding to the owner, and no next round opens at a readable verdict to carry the owner's answer.

## Evidence

E1. docs/records/stranger-rounds-until-readable.review.md (kept on main from the closed branch of PR #51 since 2026-10-29): ten rounds, 232 findings, verdict not readable in every round; prose 2,635 to 4,516 words.

E2. communication-pipeline eval/analysis/pr51-findings.md: words required by about 18 findings and added for 139; 150 of 232 findings on fix-introduced text; the IR stopped changing after round 2.

E3. communication-pipeline eval/cases/009-meta-review-vision-rounds-2026-10-29.md, Outcome, changes 2, 14, 15 and 18; adopted by the owner on 2026-10-29 ("adopt all nineteen as proposed").

E4. communication-pipeline eval/cases/010-meta-review-ir-spec-count-4-2026-10-30.md, Outcome, changes 1, 5, 9, 11, 12 and 13; adopted by the owner on 2026-10-30 ("For cases 010 and 011 - go with all recommendations, all terms ratified.").

E7. methodology docs/roadmap.ir.md ask A2 and docs/records/ir-only-documents.ir.md ask A2: two IR-only deliverables whose own Asks sections asked the owner to ratify their proposed terms.

E8. communication-pipeline eval/cases/012-meta-review-branch-point-v1.9-and-ir-spec-count-5-2026-10-30.md, Outcome, changes 1 to 15, and the owner's decision of 2026-10-30: all fifteen adopted as recommended; the terms omission, fix pass, new defect, claims check, step-6 fix, awaiting restatement and unparsed line ratified as vocabulary rows.

E9. communication-pipeline eval/cases/015-ruleset-simplification-review-2026-11-02.md, Outcome, changes 1 to 30, adopted by the owner on 2026-11-02 (changes 31 to 35 declined), the case's decision line; change 5 carries case 013's changes 1 to 3 here.

## Asks

A10. Accept or reject count 7 of the specification. Under communication-pipeline evaluation case 015 change 19, acceptance ratifies the wording of each decided claim count 7 rewords, unless the owner names one. Depends: C93, C143, C202, C283, C305 to C348.

A12. Ratify or strike the term "a term the text introduces" (T39) and its definition, C341, which the paraphrase test rests on; branch point v1.11 asks the same. Depends: C341.
