# Intermediate representation

This specification says how a text is first written as a numbered list of statements, then turned into prose and reviewed by fresh readers. Agents that write or review such texts read this specification, and so does the human owner who decides on its rules.

Status: active; count 7 under review (round 6) for communication-pipeline evaluation case 015's adopted changes. Count 6 is the version the owner last accepted, on 2026-11-01. A methodology [Specification](vocabulary.md#def-specification), the document type, required by
[W-009](rules/working-agreement.md#w-009--the-methodology-corpus-writes-its-deliverables-ir-first)
(the methodology corpus writes its deliverables [IR](vocabulary.md#def-intermediate-representation) first). Any project
that adopts W-009 by declaration uses this specification.

Reader: RD-4 (a fresh agent session, [reader catalog](style.md#readers))
in the [reasoning role](vocabulary.md#def-reasoning-role),
[paraphraser](vocabulary.md#def-paraphraser) or
[stranger](vocabulary.md#def-stranger) role. The human owner reads
the specification as RD-4 does. Assumed to know:
[W-008](rules/working-agreement.md#w-008--reports-map-their-deliverables)
(reports map their deliverables),
[P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use)
(terms are defined once and linked at first use), and the
[style guide](style.md).

## Terms

Two terms of this specification are defined in the communication-pipeline project's vocabulary:

- [Restatement](https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-restatement): the stranger's own account of the text, in at most 200 words, written before the stranger reads the [IR](vocabulary.md#def-intermediate-representation).
- [Awaiting restatement](https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-awaiting-restatement): the review-record mark on a structural fix, owed to a recurring mismatch, whose hold no later restatement has yet tested.

## Purpose and scope

For each text [that requires](#texts-that-require-an-ir) an
[intermediate representation](vocabulary.md#def-intermediate-representation)
(IR), the [reasoning role](vocabulary.md#def-reasoning-role) writes the IR before any prose of the text exists. The IR prevents three failure modes of directly written prose: claims compressed into one sentence, [referents](vocabulary.md#def-referent) left unnamed, and conversation terms used as if defined.

A case this specification does not name is decided by the human owner
when accepting the deliverable.

## Document form

An IR is a markdown file named `<subject>.ir.md`. The IR sits beside
the prose it produces, or under `docs/records/` when the prose is a
chat message or a PR body. The IR opens with header fields. The IR
holds five sections in a fixed order: Terms, Claims, Relations,
Evidence, Asks. The Claims section may use any sub-headings.

| Header | Value |
|---|---|
| Reader | one [reader catalog](style.md#readers) identifier |
| Purpose | `report` or `document`, then one sentence saying what the text is for |
| Status | `draft`, `reviewed`, `rendered`, `delivered` or [`delivered IR-only`](vocabulary.md#def-ir-only-document), optionally followed by a parenthesis holding the counts this specification asks the reasoning role to record |
| Source | the conversation, document or event that occasioned the IR |
| Normative | optional: `yes` when the prose is [normative text](vocabulary.md#def-normative-text) |
| Footprint | optional: files or directories separated by semicolons. A directory ends in `/` and covers every file under it |

A `report` is read by someone who shares the conversation:
[RD-1](style.md#readers) (the owner, in conversation), [RD-2](style.md#readers) (the owner, returning) or
[RD-3](style.md#readers) (a delegating agent). A `document` is read by someone who does
not share the conversation: [RD-4](style.md#readers) (a fresh agent session) or
[RD-5](style.md#readers) (an external reader). Prose that will live under `docs/` is a
`document`.

## Element kinds

Every element has an identifier and a body. An identifier is a kind
letter and a number, unique within the IR. A split claim takes a new
number, never a suffix.

### Kinds that carry a provenance status

| Kind | Letter | [Provenance status](vocabulary.md#def-provenance-status) | Body and rule |
|---|---|---|---|
| Term | `T` | carries a provenance status | the word or phrase and either `defined-at:` with a link to its [definition site](vocabulary.md#def-definition-site) or its meaning in the text. A term is defined once per IR. Every [project-specific term](#project-specific-term) used in a claim appears as a term element. A term without a definition site has status [proposed](#provenance). When the IR is the deliverable, the IR's own Asks section lists each proposed term for ratification |
| Claim | `C` | carries a provenance status | one statement. A claim may carry `evidence: E<n>`. In a report to RD-1 or RD-2, `part: covered` or `part: changed` places a claim under *What is already covered* or *What changed* |
| [Cluster](vocabulary.md#def-cluster) | `G` | carries a provenance status | `cluster:` and an ordered list of claim identifiers. A [topic claim](vocabulary.md#def-topic-claim) is the claim that states the cluster's subject. A cluster's list may open with a topic claim. A claim belongs to at most one cluster |

### Kinds that carry no provenance status

| Kind | Letter | Provenance status | Body and rule |
|---|---|---|---|
| Relation | `R` | carries no provenance status | `C<a> <verb> C<b> because <reason>`, with the verb one of `supports`, `depends-on`, `contradicts`, `refines`. The reason is one sentence or a claim identifier |
| Evidence | `E` | carries no provenance status | a pointer (a file and line, a commit, a message date or a URL) with what the pointer shows. Evidence is cited by a claim's `evidence:` field, never free-standing |
| Ask | `A` | carries no provenance status | a decision or action requested of the reader, and `Depends:` naming the claims or asks the request rests on. Every IR for RD-1 or RD-2 has an Asks section, holding asks or the single line `A0. No asks.` |

### The referent rule

A claim names each [referent](vocabulary.md#def-referent) inside itself. The bare pronouns are it, this, that, these and those, with no
noun after. A bare pronoun is
legal only when its antecedent is a noun phrase earlier in the claim
that holds the pronoun. A reference from one claim to another is a relation, never a pronoun inside the claim. The bare determiner phrases are the word "the" followed
by other, above, former, latter or same, with no noun after. A bare determiner phrase is legal only when its antecedent is a noun phrase earlier in the claim that holds the phrase. A
determiner followed by the noun it names, such as "this
specification", is not bare.

### Provenance

The status is the last thing in the element, in square brackets. A relation is the
[reasoning role](vocabulary.md#def-reasoning-role)'s inference by
definition.

| Status | Form | Marks |
|---|---|---|
| decided | `[decided: <who>, <date>]` or `[decided: <source>]` | an element ratified by the human owner or quoted from a document the human owner ratified |
| proposed | `[proposed: <IR id or "this IR">]` | an element put forward and awaiting ratification |
| inferred | `[inferred: R<n>]` | an element the reasoning role derived, citing the relation that derives it |

A term with status proposed is an unratified term. The count of unratified terms is the mechanical measure of unratified vocabulary, one indicator of [convergence](vocabulary.md#def-convergence).

## Mechanical checks

The IR has sixteen mechanical checks, one per row of the table below. A lint or a [stranger](vocabulary.md#def-stranger) reports each check
as a finding. [methodology-tools](https://github.com/majodali/methodology-tools) runs the checks as `mtool ir check`.

| Check | Name | Fires when |
|---|---|---|
| CK-01 | referent rule | a claim contains a bare form of the referent rule with no noun-phrase antecedent earlier in that claim |
| CK-02 | claim length | a claim exceeds 40 words |
| CK-03 | compound claim | a claim joins two clauses that could each stand as a claim, by `and`, `but`, `so`, a semicolon or an em-dash. A semicolon or a final `, and` that follows a colon separates list items and is not a join |
| CK-04 | undefined term | a project-specific term appears in a claim and is neither a term element nor linked to a [definition site](vocabulary.md#def-definition-site). <a id="project-specific-term"></a>A project-specific term is a bolded term or a capitalized multi-word phrase that is not the name of a person, product or place. A term in the project's `docs/vocabulary.md` is also a project-specific term |
| CK-05 | provenance | a term, claim or cluster has no status, or a status without its required fields |
| CK-06 | dangling reference | a relation, cluster, `evidence:` or `Depends:` names an identifier that does not resolve |
| CK-07 | header | the Reader header is not a catalog identifier or the Purpose header lacks `report` or `document` |
| CK-08 | asks section | an IR for RD-1 or RD-2 has no Asks section |
| CK-09 | cluster membership | a claim appears in two clusters |
| CK-10 | section order | the five sections are absent or out of order |
| CK-11 | definition site | a term's `defined-at:` target does not resolve |
| CK-12 | identifier uniqueness | two elements carry one identifier |
| CK-13 | term uniqueness | two term elements name one term |
| CK-14 | review record | an IR whose Status is `reviewed` or `delivered` after [rounds](vocabulary.md#def-round) has no [review record](vocabulary.md#def-review-record) beside it, or a review record without a [verdict](#the-verdict) per round; an IR whose Status is `delivered IR-only` is exempt |
| CK-15 | round trip | the [render map](vocabulary.md#def-render-map) (Rendering and review) omits a claim, names an identifier the IR does not hold, or is absent from paraphrased prose |
| CK-16 | element form | a line inside a section is neither an element, a heading, a continuation of the element above, nor a comment |

<a id="rendering-rule"></a>

## Rendering and review

Prose is rendered from the IR when a [rendering condition](#rendering-conditions)
selects rendering. The
[paraphraser](vocabulary.md#def-paraphraser) renders one claim as one
sentence. The paraphraser renders one cluster as one paragraph in the cluster's order or, when its claims fall under different parts, as one paragraph per part. The paraphraser introduces no new claim. The
paraphraser drops no claim. The
paraphraser may add connective prose: a sentence that asserts nothing
the IR holds and exists to join claims. The paraphraser renders no relation and no evidence as a sentence.

The renderer is the paraphraser or, for [normative text](vocabulary.md#def-normative-text), the [reasoning role](vocabulary.md#def-reasoning-role). A paraphrase could change the force of normative text. The unit for [P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use) is the whole text for a report and the section for a document. The renderer links a term with a [definition site](vocabulary.md#def-definition-site) at its first use in the unit. The renderer does not link a later use
of a term with a definition site. The renderer defines a term the IR introduces in a sentence of its own before its first use. When a report delivers the text, the reasoning role lists under [*Terms introduced*](vocabulary.md#def-terms-introduced) each term the IR introduces, for ratification. When neither the [methodology vocabulary](vocabulary.md) nor the project's `docs/vocabulary.md` defines an IR term, the renderer puts the IR's Terms section before the body. Each entry of that Terms section gives the term, its IR definition and its link. When a term draws an undefined-term finding in two [rounds](vocabulary.md#def-round), the reasoning role adds the term to that Terms section. For [RD-5](style.md#readers),
the first use of a term with a definition site carries its
definition in parentheses instead of a link. For RD-1 or RD-2, the renderer places a claim under the part its `part:` field names. Without a `part:`
field, a decided claim renders under *What is already covered*. A
proposed or inferred claim without a `part:` field renders under
*What changed*. When rendering, the renderer follows the style guide's rows for the IR's reader. The renderer states an empty Asks section as "No asks."

The paraphraser appends a render map: one comment line reading
`render map:` and, per claim, the paragraph it landed in, as
`C1→¶1 C2→¶1 …`. When the
reasoning role renders, it appends the render map in the
paraphraser's form.

The reasoning role makes a fix to rendered prose in the IR first.
After a fix to the IR, the reasoning role renders the prose again or
edits it to match the IR. The reasoning role rephrases or
removes words in a fix to prose before it adds words. When a fix rewords a decided claim, the reasoning role keeps the claim's decided source. The reasoning role notes the rewording as `reworded in count N, round M`. A state header names whether the sentences under it state what is done now or what the text aims at. The reasoning role adds words in a fix only for a missing definition or referent, a state header, or a rewording note. The reasoning role adds no rule in a fix beyond the [changes the owner adopted](https://github.com/majodali/communication-pipeline/blob/main/eval/README.md#meta-review-records) for the [count](vocabulary.md#def-count). When a finding needs a new rule, the reasoning role lists the finding for the owner with a proposed wording. Until the owner decides, a finding that needs a new rule counts against the [verdict](#the-verdict) as its kind does under the verdict's four conditions. When the fix a finding needs would change a decided claim, the reasoning role does not write a claim around the finding. The reasoning role puts such a finding to the owner with a proposed wording, and the fix waits for the owner's answer. The next round opens after the owner answers that finding. The owner's acceptance of a text ratifies the text's reworded decided claims, unless the owner names one. When a fix separates the present from what the text aims at, the reasoning role moves the sentence under a state header. In a fix, the reasoning role does not mark a single sentence with "Today". In a fix, the reasoning role keeps the connective prose that joins a rule to a reason the IR holds as its own claim. When a fix brings in a term no vocabulary or IR element defines, the reasoning role adds it, as proposed, to the IR's Terms section.

The fix rules govern every fix, including an edit outside a round to an IR whose Status is reviewed. In an edit outside a round to a reviewed IR, the reasoning role cuts each claim the edit makes a duplicate. In such an edit, the reasoning role also amends each claim the edit makes stale.

### Stranger rounds

#### The verdict

In a [round](vocabulary.md#def-round), the verdict is readable when four conditions hold. A round is one stranger's review of the text and the fixes made after that review. A restatement mismatch is a disagreement the [stranger](vocabulary.md#def-stranger) finds between its [restatement](https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-restatement) and the IR. A claim or a qualifier the restatement leaves out is an [omission](vocabulary.md#def-omission), not a restatement mismatch. A restatement that says a rule has no qualifier the IR holds has a mismatch. A [passage](vocabulary.md#def-passage) is the prose sentences that carry one claim or one cluster. The round's stranger instance is the stranger the reasoning role dispatched for the round. [Confirmation](vocabulary.md#def-confirmation) is the step at which the round's stranger instance says whether each fix holds. At confirmation, the round's stranger instance [withdraws](vocabulary.md#def-withdrawal) a finding other than a restatement mismatch by saying the finding no longer applies to the prose. A term the text introduces is one the text defines or links to a vocabulary entry. The <a id="paraphrase-test"></a>paraphrase test asks the stranger to restate the text for the human reader the Reader line names, without any term the text introduces.

The conditions, each with what counts against the verdict and what does not:

| Condition | Counts against the verdict | Does not count against the verdict |
|---|---|---|
| The first condition: the restatement has no restatement mismatch with the IR. | Each restatement mismatch counts against the verdict. The round's stranger instance never withdraws a restatement mismatch at confirmation. | An omission does not count against the verdict. |
| The second condition: the stranger finds no contradiction. | Each contradiction finding counts against the verdict, unless the round's stranger instance withdrew the finding at confirmation on a reason that quotes the prose. | — |
| The third condition: the stranger finds no undefined term, a term neither defined in the text nor linked to a definition site. | Each undefined-term finding counts against the verdict, unless the round's stranger instance withdrew the finding at confirmation on a reason that quotes the prose. | — |
| The fourth condition: the stranger's restatement passes the paraphrase test. | Each passage the stranger cannot restate without a term the text introduces counts against the verdict. | — |

<a id="the-count"></a>
#### Rounds, the limit and rework

The [limit](vocabulary.md#def-limit) is ten rounds. The reasoning role runs a stranger review in rounds until a round returns the verdict readable or the [count](vocabulary.md#def-count) reaches the limit. The rounds apply to every
stranger review the rendering conditions select.

The [reasoning role](vocabulary.md#def-reasoning-role) starts each
round by dispatching a stranger with a fresh context, never itself and
never an earlier round's instance. The stranger reviews the IR and
the prose against the reader's readability test
([reader catalog](style.md#readers)). In each round's brief, the reasoning role names the human reader the text's Reader line names. In each round's brief to the stranger, the reasoning role lists each passage [awaiting restatement](https://github.com/majodali/communication-pipeline/blob/main/docs/vocabulary.md#def-awaiting-restatement). Before reading the IR, the stranger restates each listed passage in one sentence. The reasoning role treats a finding that proposes fewer words, a plainer phrase or a removed repetition like any other finding.

The reasoning role records in the [review record](vocabulary.md#def-review-record) each round's findings, the verdict, and the reasoning role's own decision on each finding. The reasoning role's [decision on a finding](vocabulary.md#def-decision-on-a-finding) is one of two: fixed, or declined with a reason. A confirmed or unfixed mark is not a decision on a finding: the mark records whether the round's stranger instance confirmed a fix. The review record
holds, per round, the word count of the prose and the claim count of
the IR. The review record keeps each restatement as written. The reasoning role checks each listed passage's [structural fix](#structural-fix) against the stranger's one-sentence restatement of the passage.

The text delivered after a readable verdict is the text that round read, with the round's fixes applied. At a readable verdict, the reasoning role fixes the round's findings under the fix rules, in the IR and then in the prose. At a readable verdict, a finding whose fix waits for the owner stays unfixed, and the reasoning role lists it for the owner. At a readable verdict, the round's stranger instance confirms each fix not marked awaiting restatement. A structural fix marked awaiting restatement in a readable round's [fix pass](vocabulary.md#def-fix-pass) keeps the mark. The reasoning role lists the passage of a fix still awaiting restatement at a readable verdict in the next count's round 1 brief. A finding whose fix the readable round's stranger instance does not
confirm is unfixed. The reasoning role marks each finding of the readable round confirmed or unfixed in the review record. An unconfirmed fix's words stay in the delivered prose. The reasoning role fixes an unfixed finding of the readable round at
the next edit of an active document. At that edit, the reasoning role revises the unconfirmed words. The next count's stranger instances review the revised words. After a verdict of not readable, the
reasoning role fixes the IR and then the prose. The next round
reviews the fixed IR and the fixed prose.

<a id="structural-fix"></a>A structural fix is one of two fixes for a misreading that a rewording does not settle. The first structural fix moves the sentence out of the structure that produces the misreading: a list, a section or an adjacency. The second structural fix changes the claim to the strangers' reading, when that reading is true. A rewording alone is not a structural fix. When restatement mismatches name one claim in two rounds of the text's counts, the reasoning role makes a structural fix before the next round. The reasoning role marks the structural fix made for a recurring mismatch awaiting restatement in the review record.

A fix pass is the reasoning role's fixes of one round's findings, in the IR and then in the prose. Each project that runs rounds names, in its own documents, the checks that run after each fix pass and the lines the review record holds. A fix the round's stranger instance confirms only in part counts as a fix not held. The reasoning role names the fix commit to the round's stranger instance. The round's stranger instance reads the prose and the IR at the fix commit, in full, before answering. A [new defect](vocabulary.md#def-new-defect) is a defect a fix introduces. The round's stranger instance names each new defect at confirmation. The next round opens after the reasoning role records the round's confirmation. Before the next round opens, the reasoning role makes the fixes the confirmation calls for. At the end of a count, the reasoning role sets the IR's Status to
`reviewed`.

At the limit the reasoning role does not deliver the text before
the owner's decision. At the limit, the reasoning role fixes the final round's findings in the IR and then in the prose. The final round's stranger instance confirms each fix not marked awaiting restatement before the owner's decision. The reasoning role marks each finding of the final round confirmed or unfixed in the review record. At the limit, a fix still awaiting restatement in the final round counts as unfixed. At a readable verdict and at the limit, the reasoning role does not fix in the count a new defect the confirmation names. The reasoning role lists each new defect of that confirmation for the owner. The reasoning role fixes the new defect in the next edit of the text. At the
limit the reasoning role states in the review record that the limit
was reached. Rework is an edit of the IR
and the text by the reasoning role. The owner decides, when accepting
or rejecting a text at the limit, whether the text is delivered,
reworked or withdrawn. When the owner decides delivery, the
reasoning role delivers the text. Rework starts a new count from
round one.
The reasoning role keeps the ended count's review record through
rework. When the text at the limit is an amendment, the owner's decision is the amendment's adjudication under
[Article 8](constitution.md#article-8--amendments-versions-and-migration)
(amendments, versions, and migration).

### Meta-review

#### Who decides on a meta-review

The owner decides whether a [meta-review](vocabulary.md#def-meta-review) runs. At the end of a count, the reasoning role reports to the owner the [meta-review signals](vocabulary.md#def-meta-review-signal) that fired, or that the count reached the limit. The owner may dispatch a meta-review of any text. A session the owner starts, the meta-review session, performs the meta-review. The meta-review session delivers the meta-review as a report to the owner.

#### The signals

A meta-review signal is one of three
conditions in a review record. The first
signal: in two or more rounds, a fix was not held at confirmation. The second signal: a finding declined in an earlier round was raised again. The second signal also fires when restatement mismatches named one claim in two rounds of the text's counts. The fourth signal: in round 3 or later, a stranger found a contradiction in a passage an
earlier round's fix touched. Communication-pipeline evaluation case [012](https://github.com/majodali/communication-pipeline/blob/main/eval/cases/012-meta-review-branch-point-v1.9-and-ir-spec-count-5-2026-10-30.md) struck the third signal, a measure of the prose's growth per IR claim, on 2026-10-30. The first, second and fourth signals keep their numbers. At the end of a count, the reasoning
role checks the signals against the review record.

#### The Meta-review line

The reasoning role writes `Meta-review: pending` when a signal fired or the count reached the limit. When no signal fired and the count did not reach the limit, the reasoning role writes `Meta-review: not indicated`. The `Meta-review:` line names the signals checked. The `Meta-review:` line takes one of three values: pending, not indicated or delivered. A check that cannot read a review-record line stops with an error. The reasoning role corrects an unreadable review-record line before writing the `Meta-review:` line.

On delivery of the meta-review, the reasoning role sets the
review record's line to `Meta-review: delivered` with a link. A `Meta-review: pending` line in an accepted
deliverable's review record is a finding of the next [form audit](constitution.md#article-9--audits) under
Article 9 (audits).

## Rendering conditions

The rendering conditions settle, for one IR, whether prose is rendered, who renders it and whether the stranger rounds run. The first row whose condition holds decides. A dependent ask is an ask with a `Depends:` field. The inputs are the IR's reader, purpose, Normative header, claim count, proposed-term count, count of dependent asks, longest claim and two owner inputs. The first owner input is whether the owner asked for a review. The second owner input is whether the owner designated the document IR-only. A lint runs the mechanical checks in every case.

| Condition | What follows |
|---|---|
| the owner designated the document [IR-only](vocabulary.md#def-ir-only-document) and the header does not carry `Normative: yes` | no rendering and no [stranger](vocabulary.md#def-stranger) rounds; the IR is the deliverable, and its Status reads `delivered IR-only` |
| the header carries `Normative: yes` | the [reasoning role](vocabulary.md#def-reasoning-role) renders and runs the stranger rounds |
| the owner asked for a review, or purpose is `document`, or reader is RD-4 or RD-5 | the [paraphraser](vocabulary.md#def-paraphraser) renders. The [stranger](vocabulary.md#def-stranger) rounds run |
| proposed terms > 0 | the paraphraser renders, with the ratification ask |
| reader is RD-2 | the paraphraser renders |
| reader is RD-1 and (claims > 6 or dependent asks > 0 or longest claim > 30 words) | the paraphraser renders |
| reader is RD-3 and (claims > 12 or dependent asks > 0) | the paraphraser renders |
| otherwise, for RD-1 or RD-3 | the reasoning role delivers the IR as it stands |

The counts in the conditions are provisional. A change to a count is
an [editorial change](vocabulary.md#def-editorial-change) while it
changes no obligation.

## The footprint

Before delivery, the
[reasoning role](vocabulary.md#def-reasoning-role), or a lint,
compares the Footprint header with the files the branch changed since
its base. An IR whose deliverable is a chat message has no [footprint](vocabulary.md#def-footprint). No branch carries a chat message. When the Footprint header is absent or empty, no comparison is made. A file is changed when the branch's diff adds, modifies,
deletes or renames it. The IR and its review record are not counted as
changed files. A changed file that no declared entry covers is a
surprise. A declared file that did not change, or a declared directory
under which no file changed, is a miss. The counts of surprises and misses measure one indicator of [convergence](vocabulary.md#def-convergence): how far the footprint's prediction missed. The reasoning role
records the unratified-term count, the surprise count and the miss
count in the Status parenthesis when the IR is delivered.

## Texts that require an IR

A document always starts as an IR. A report to [RD-2](style.md#readers) always starts as
an IR. A report to RD-1 or RD-3 that introduces no term, records no decision and states no [register fact](vocabulary.md#def-register-fact) may be written as prose directly. A register fact is a statement about the state of a [register](vocabulary.md#def-register) or of a row in one. The [reasoning role](vocabulary.md#def-reasoning-role) runs the style guide's mechanical checks on prose it writes directly. A term, a decision or a register fact
requires the IR. A term, a decision and a register fact are each
content a model would hold.

## Lifecycle

An IR's mutability follows the state of its prose: active or
delivered. The reasoning role edits the IR of an active document whenever the
document is edited. A disagreement
between an active document and its IR is a defect in the prose. The IR of a delivered report is a record. At delivery, the reasoning
role sets the Status of a report's IR to `delivered`.
The reasoning role does not edit the IR of a delivered report.
On ratification, the reasoning role adds a row with a `def-` anchor
for the ratified term to the project vocabulary. The vocabulary row of a ratified term is the term's
[definition site](vocabulary.md#def-definition-site).

<!-- render map: C305→¶1 C306→¶1 C1→¶6 C4→¶6 C5→¶2 C149→¶2 C150→¶2 C179→¶2 C151→¶3 C166→¶3 C175→¶3 C6→¶7 C7→¶8 C8→¶8 C9→¶8 C167→¶8 C10→¶8 C11→¶19 C12→¶9 C13→¶9 C338→¶9 C14→¶9 C15→¶9 C16→¶9 C142→¶9 C17→¶10 C18→¶10 C19→¶10 C20→¶11 C21→¶11 C22→¶11 C23→¶12 C24→¶12 C25→¶12 C27→¶12 C257→¶12 C28→¶12 C29→¶12 C30→¶12 C31→¶12 C226→¶12 C240→¶12 C32→¶12 C33→¶13 C34→¶13 C36→¶13 C37→¶13 C38→¶13 C39→¶13 C40→¶14 C42→¶14 C41→¶14 C35→¶14 C163→¶14 C231→¶14 C43→¶14 C259→¶12 C292→¶12 C293→¶12 C260→¶13 C294→¶12 C295→¶13 C44→¶15 C165→¶15 C46→¶16 C47→¶16 C48→¶16 C49→¶17 C50→¶17 C303→¶18 C51→¶18 C52→¶18 C53→¶19 C54→¶19 C55→¶19 C56→¶19 C57→¶19 C58→¶19 C232→¶19 C59→¶19 C60→¶19 C61→¶19 C62→¶19 C63→¶19 C64→¶19 C65→¶19 C66→¶19 C67→¶19 C68→¶19 C69→¶19 C70→¶19 C71→¶21 C72→¶21 C174→¶21 C73→¶21 C180→¶21 C74→¶21 C75→¶21 C220→¶22 C76→¶22 C173→¶22 C164→¶22 C77→¶22 C153→¶22 C78→¶22 C79→¶22 C80→¶22 C154→¶22 C81→¶22 C82→¶22 C83→¶23 C176→¶22 C85→¶23 C86→¶24 C169→¶24 C87→¶24 C340→¶24 C143→¶24 C279→¶24 C280→¶24 C281→¶24 C317→¶24 C318→¶24 C319→¶24 C282→¶24 C304→¶24 C283→¶24 C307→¶24 C308→¶24 C309→¶24 C313→¶24 C310→¶25 C311→¶25 C312→¶25 C314→¶22 C315→¶22 C316→¶22 C88→¶30 C89→¶30 C90→¶30 C91→¶31 C92→¶31 C266→¶31 C267→¶31 C268→¶32 C339→¶26 C93→¶26 C211→¶26 C263→¶26 C264→¶26 C228→¶26 C290→¶26 C233→¶26 C258→¶26 C203→¶28 C227→¶28 C195→¶28 C265→¶28 C221→¶28 C194→¶28 C234→¶28 C235→¶28 C328→¶26 C341→¶26 C337→¶28 C329→¶28 C330→¶31 C331→¶32 C94→¶31 C95→¶32 C261→¶32 C262→¶32 C155→¶33 C97→¶33 C345→¶33 C156→¶33 C301→¶33 C302→¶33 C182→¶33 C202→¶33 C248→¶33 C183→¶33 C254→¶33 C291→¶33 C98→¶33 C157→¶33 C320→¶34 C344→¶34 C321→¶34 C322→¶34 C323→¶34 C324→¶34 C325→¶35 C269→¶35 C327→¶35 C272→¶35 C273→¶35 C274→¶35 C297→¶35 C275→¶35 C298→¶35 C99→¶36 C197→¶36 C198→¶36 C199→¶36 C326→¶36 C276→¶36 C277→¶36 C278→¶36 C158→¶35 C144→¶36 C101→¶36 C100→¶36 C186→¶36 C171→¶36 C172→¶36 C102→¶36 C103→¶32 C333→¶37 C332→¶37 C192→¶37 C187→¶38 C188→¶38 C208→¶38 C190→¶38 C284→¶38 C288→¶38 C105→¶38 C191→¶39 C239→¶39 C209→¶39 C334→¶39 C335→¶39 C336→¶39 C107→¶37 C108→¶37 C159→¶40 C109→¶40 C246→¶41 C204→¶41 C110→¶41 C205→¶41 C229→¶41 C111→¶41 C112→¶41 C113→¶42 C114→¶42 C170→¶42 C115→¶42 C116→¶42 C117→¶42 C118→¶42 C119→¶42 C120→¶43 C145→¶43 C121→¶44 C177→¶44 C122→¶44 C123→¶44 C124→¶44 C146→¶44 C125→¶44 C126→¶44 C127→¶44 C128→¶44 C129→¶45 C130→¶45 C131→¶45 C342→¶45 C206→¶45 C132→¶45 C178→¶45 C133→¶46 C134→¶46 C160→¶46 C135→¶46 C185→¶46 C161→¶46 C136→¶46 C181→¶46 C217→¶42 C218→¶42 C219→¶19 -->
