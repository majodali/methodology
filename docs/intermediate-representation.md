# Intermediate representation

Status: active. A Methodology-level specification required by
[W-009](rules/working-agreement.md#w-009--the-methodology-corpus-writes-its-deliverables-ir-first)
(the methodology corpus writes its deliverables IR first). Any project
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
[style guide](style.md), including its Readers table.

## Purpose and scope

The [reasoning role](vocabulary.md#def-reasoning-role) writes an
[intermediate representation](vocabulary.md#def-intermediate-representation)
(IR) before any prose of the communication exists. The IR prevents
three failure modes of prose written directly: several claims
compressed into one sentence, referents left unnamed, and conversation
terms used as if defined.

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
| Purpose | `report` or `document`, then one sentence saying what the communication is for |
| Status | `draft`, `reviewed`, `rendered` or `delivered`, optionally followed by a parenthesis holding the counts this specification asks the reasoning role to record |
| Source | the conversation, document or event that occasioned the IR |
| Normative | optional: `yes` when the prose is [normative text](vocabulary.md#def-normative-text) |
| Footprint | optional: files or directories separated by semicolons. A directory ends in `/` and covers every file under it |

A `report` is read by someone who shares the conversation:
[RD-1](style.md#readers), [RD-2](style.md#readers) or
[RD-3](style.md#readers). A `document` is read by someone who does
not share the conversation: [RD-4](style.md#readers) or
[RD-5](style.md#readers). Prose that will live under `docs/` is a
`document`.

## Element kinds

Every element has an identifier and a body. An identifier is a kind
letter and a number, unique within the IR. A split claim takes a new
number, never a suffix.

| Kind | Letter | Body and rule |
|---|---|---|
| Term | `T` | the word or phrase and either `defined-at:` with a link to its [definition site](vocabulary.md#def-definition-site) or its meaning in the communication. A term is defined once per IR. Every project-specific term used in a claim appears as a term element. A term without a definition site has status proposed. The reasoning role lists a proposed term for ratification |
| Claim | `C` | one statement. A claim may carry `evidence: E<n>`. In a report to RD-1 or RD-2, a claim may carry `part: covered` or `part: changed` |
| Cluster | `G` | `cluster:` and an ordered list of claim identifiers, with an optional topic claim first. A claim belongs to at most one cluster |
| Relation | `R` | `C<a> <verb> C<b> because <reason>`, with the verb one of `supports`, `depends-on`, `contradicts`, `refines`. The reason is one sentence or a claim identifier. A reference from one claim to another is a relation, never a pronoun inside the claim |
| Evidence | `E` | a pointer (a file and line, a commit, a message date or a URL) with what the pointer shows. Evidence is cited by a claim's `evidence:` field, never free-standing |
| Ask | `A` | a decision or action requested of the reader, and `Depends:` naming the claims or asks the request rests on. Every IR for RD-1 or RD-2 has an Asks section, holding asks or the single line `A0. No asks.` |

### The referent rule

A claim names each [referent](vocabulary.md#def-referent) inside itself. A bare pronoun or determiner phrase is
legal only when its antecedent is a noun phrase earlier in that
claim. The bare pronouns are it, this, that, these and those, with no
noun after. The bare determiner phrases are the word "the" followed
by other, above, former, latter or same, with no noun after. A
determiner followed by the noun it names, such as "this
specification", is not bare.

### Provenance

Each term, claim and cluster, and no other element, ends with one
status in square brackets. A relation is the
[reasoning role](vocabulary.md#def-reasoning-role)'s inference by
definition.

| Status | Form | Marks |
|---|---|---|
| decided | `[decided: <who>, <date>]` or `[decided: <source>]` | an element ratified by the human owner or quoted from a governed document |
| proposed | `[proposed: <IR id or "this IR">]` | an element put forward and awaiting ratification |
| inferred | `[inferred: R<n>]` | an element the reasoning role derived, citing the relation that derives it |

A term with status proposed is an unratified term. The count of
unratified terms is the mechanical reading of the
unratified-vocabulary indicator of
[convergence](vocabulary.md#def-convergence).

## Mechanical checks

A lint or a [stranger](vocabulary.md#def-stranger) reports each check
as a finding. methodology-tools runs the checks as `mtool ir check`.

| Check | Name | Fires when |
|---|---|---|
| CK-01 | referent rule | a claim contains a bare form of the referent rule with no noun-phrase antecedent earlier in that claim |
| CK-02 | claim length | a claim exceeds 40 words |
| CK-03 | compound claim | a claim joins two clauses that could each stand as a claim, by `and`, `but`, `so`, a semicolon or an em-dash. A semicolon or a final `, and` that follows a colon separates list items and is not a join |
| CK-04 | undefined term | a project-specific term appears in a claim and is neither a term element nor linked to a [definition site](vocabulary.md#def-definition-site). A project-specific term is a bolded term, a capitalized multi-word phrase that is not the name of a person, product or place, or a term in the project's `docs/vocabulary.md` |
| CK-05 | provenance | a term, claim or cluster has no status, or a status without its required fields |
| CK-06 | dangling reference | a relation, cluster, `evidence:` or `Depends:` names an identifier that does not resolve |
| CK-07 | header | the Reader header is not a catalog identifier or the Purpose header lacks `report` or `document` |
| CK-08 | asks section | an IR for RD-1 or RD-2 has no Asks section |
| CK-09 | cluster membership | a claim appears in two clusters |
| CK-10 | section order | the five sections are absent or out of order |
| CK-11 | definition site | a term's `defined-at:` target does not resolve |
| CK-12 | identifier uniqueness | two elements carry one identifier |
| CK-13 | term uniqueness | two term elements name one term |
| CK-14 | review record | an IR whose Status is `reviewed` or `delivered` after rounds has no review record beside it, or a review record without a verdict per round |
| CK-15 | round trip | the render map (Rendering rule) omits a claim, names an identifier the IR does not hold, or is absent from paraphrased prose |
| CK-16 | element form | a line inside a section is neither an element, a heading, a continuation of the element above, nor a comment |

## Rendering rule

Prose is rendered from the IR when a rendering condition (table below)
selects rendering. The
[paraphraser](vocabulary.md#def-paraphraser) renders one claim as one
sentence. The paraphraser renders one cluster as one paragraph in the
cluster's order. The paraphraser introduces no new claim. The
paraphraser drops no claim. The
paraphraser may add connective prose: a sentence that asserts nothing
the IR holds and exists to join claims. Relations and
evidence are not rendered as sentences.

The unit
[P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use)
(terms are defined once and linked at first use) defines is the whole
text for a report and the section for a document. A term with a
[definition site](vocabulary.md#def-definition-site) is linked at its
first use in the unit. Later uses
of a term with a definition site in the unit are not linked. A term the IR introduces is
defined in a sentence of its own before its first use. A term the IR
introduces is listed under
[*Terms introduced*](vocabulary.md#def-terms-introduced). For [RD-5](style.md#readers),
the first use of a term with a definition site carries its
definition in parentheses instead of a link. For RD-1 or RD-2, a claim
renders under the part its `part:` field names. Without a `part:`
field, a decided claim renders under *What is already covered*. A
proposed or inferred claim without a `part:` field renders under
*What changed*. The rendering follows the style guide's rows for the
IR's reader. The rendering states an empty Asks section as "No asks."

The paraphraser appends a render map: one HTML comment line reading
`render map:` and, per claim, the paragraph it landed in, as
`C1→¶1 C2→¶1 …`. Normative text is rendered by the
[reasoning role](vocabulary.md#def-reasoning-role), not by the
paraphraser. A paraphrase could change the force of normative text. When the
reasoning role renders, it appends the render map in the
paraphraser's form.

The reasoning role makes a fix to rendered prose in the IR first.
After a fix to the IR, the reasoning role renders the prose again or
edits it to match the IR. A fix to prose rephrases or
removes words before it adds words. A fix adds words only to supply a
missing definition or a missing referent.

### Stranger rounds

In a [round](vocabulary.md#def-round), the verdict is readable when three conditions hold: the stranger's restatement of the
text's problem, terms and decisions matches the IR; the stranger finds
no contradiction; the stranger finds no undefined term. The [limit](vocabulary.md#def-limit) is ten rounds. A [stranger](vocabulary.md#def-stranger) review runs in rounds until a round returns the verdict readable or the [count](vocabulary.md#def-count) reaches the limit. The rounds apply to every
stranger review the rendering conditions select.

The [reasoning role](vocabulary.md#def-reasoning-role) starts each
round by dispatching a stranger with a fresh context, never itself and
never an earlier round's instance. The stranger reviews the IR and
the prose against the reader's readability test
([reader catalog](style.md#readers)). A finding that proposes fewer words, a plainer phrase or a
removed repetition is treated like any other finding.

The reasoning role records each round's findings, each finding's disposition, and the verdict in the [review record](vocabulary.md#def-review-record). The review record
holds, per round, the word count of the prose and the claim count of
the IR.

The text delivered after a readable verdict is the judged text with
the round's fixes applied, each finding confirmed or marked unfixed. At a readable verdict,
the reasoning role fixes the round's findings in the IR and then in
the prose. The readable round's stranger instance confirms each fix
before delivery. A finding whose fix the instance does not confirm is unfixed. The reasoning role fixes an unfixed finding of the readable round at
the next edit of an active document. After a verdict of not readable, the
reasoning role fixes the IR and then the prose. The next round
reviews the fixed IR and the fixed prose. At the end of a count, the reasoning role sets the IR's Status to
`reviewed`.

At the limit the reasoning role does not deliver the text. At the
limit the reasoning role states in the review record that the limit
was reached. Rework is an edit of the IR
and the text by the reasoning role. The owner decides, when accepting
or rejecting a text at the limit, whether the text is delivered,
reworked or withdrawn. Rework starts a new count from round one.
The review record of the ended count is kept through rework. For an amendment, the owner's decision is its adjudication under
[Article 8](constitution.md#article-8--amendments-versions-and-migration)
(amendments, versions, and migration).

### Meta-review

A text whose review record holds three or more rounds in one count is a [meta-review](vocabulary.md#def-meta-review) subject. The reasoning role
asks the owner, in the report that delivers a meta-review subject, to
dispatch its meta-review. When the reasoning role starts a third
round, it writes the line `Meta-review: pending` in the review
record.

A session the owner starts, the meta-review session, performs the
meta-review. The meta-review session delivers the meta-review as a
report to the owner. On delivery of the meta-review, the reasoning role sets the
review record's line to `Meta-review: delivered` with a link. A
`Meta-review: pending` line in the review record of an accepted
deliverable is a finding of the next form audit under
[Article 9](constitution.md#article-9--audits) (audits).

## Rendering conditions

The inputs are the IR's reader, purpose, Normative
header, claim count, proposed-term count, count of dependent asks
(asks with a `Depends:` field), and longest claim, plus whether the owner
asked for a review. A lint runs the mechanical checks in every case. The
first row whose condition holds decides.

| Condition | What follows |
|---|---|
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

An IR whose deliverable is a chat message has no footprint. No branch
carries a chat message. When the Footprint header is absent or
empty, no comparison is made. Before delivery, the
[reasoning role](vocabulary.md#def-reasoning-role), or a lint,
compares the Footprint header with the files the branch changed since
its base. A file is changed when the branch's diff adds, modifies,
deletes or renames it. The IR and its review record are not counted as
changed files. A changed file that no declared entry covers is a
surprise. A declared file that did not change, or a declared directory
under which no file changed, is a miss. The counts of surprises and
misses are the mechanical reading of the prediction-surprise indicator
of [convergence](vocabulary.md#def-convergence). The reasoning role
records the unratified-term count, the surprise count and the miss
count in the Status parenthesis when the IR is delivered.

## When an IR is required

A document always starts as an IR. A report to [RD-2](style.md#readers) always starts as
an IR. A report
to RD-1 or RD-3 that introduces no term, records no decision and states no [register fact](vocabulary.md#def-register-fact) may be written as prose directly, under the
style guide's mechanical checks. A term, a decision or a register fact
requires the IR. A term, a decision and a register fact are each
content a model would hold.

## Lifecycle

An IR's mutability follows the state of its prose: active or
delivered. The reasoning role edits the IR of an active document whenever the
document is edited. A disagreement
between an active document and its IR is a defect in the prose. The IR of a delivered report is a record. At delivery, the reasoning
role sets the Status of a report's IR to `delivered`.
The IR of a delivered report is not edited after delivery.
On ratification, the reasoning role adds a row with a `def-` anchor
for the ratified term to the project vocabulary. The vocabulary row of a ratified term is the term's
[definition site](vocabulary.md#def-definition-site).

## History

The specification was adopted on 2026-10-26 at v1.2 of the
communication-pipeline project's schema and is amended here since.
CK-12 was added at adoption after a stranger review. The Footprint
header and the second stranger round were added on 2026-10-26. The rounds until readable, the limit of ten and the meta-review were
added by owner ruling of 2026-10-26. The fixing and confirmation of
the readable round's findings before delivery were added on
2026-10-27, by owner decision on communication-pipeline evaluation
case 008. The owner placed the meta-review in the
communication-pipeline project until that project is archived, and in
the methodology repository after. The specification was rewritten from
its IR, `intermediate-representation.ir.md` beside this file, after
ten [stranger](vocabulary.md#def-stranger) rounds on the amendment
text of methodology PR #51 ended without a readable verdict. The ten
rounds grew the prose from 2,635 words to 4,516. The record is the
communication-pipeline project's
[analysis of the ten rounds](https://github.com/majodali/communication-pipeline/blob/main/eval/analysis/pr51-findings.md).

<!-- render map: C149→¶1 C150→¶1 C179→¶1 C5→¶1 C151→¶1 C166→¶1 C175→¶1 C1→¶2 C4→¶2 C6→¶3 C7→¶4 C8→¶4 C9→¶4 C167→¶4 C10→¶4 C11→¶5 C12→¶5 C13→¶5 C14→¶5 C15→¶5 C16→¶5 C142→¶5 C17→¶6 C18→¶6 C19→¶6 C20→¶7 C21→¶7 C22→¶7 C23→¶8 C24→¶8 C25→¶8 C27→¶8 C152→¶8 C28→¶8 C29→¶8 C30→¶8 C31→¶8 C32→¶8 C33→¶8 C34→¶8 C35→¶8 C36→¶8 C37→¶8 C38→¶8 C39→¶8 C40→¶9 C41→¶9 C42→¶9 C163→¶9 C43→¶9 C44→¶10 C165→¶10 C46→¶11 C47→¶11 C48→¶11 C49→¶12 C50→¶12 C51→¶13 C52→¶13 C53→¶14 C54→¶14 C55→¶14 C56→¶14 C57→¶14 C58→¶14 C59→¶14 C60→¶14 C61→¶14 C62→¶14 C63→¶14 C64→¶14 C65→¶14 C66→¶14 C67→¶14 C68→¶14 C69→¶14 C70→¶14 C71→¶15 C72→¶15 C174→¶15 C73→¶15 C180→¶15 C74→¶15 C75→¶15 C173→¶16 C76→¶16 C164→¶16 C77→¶16 C153→¶16 C78→¶16 C79→¶16 C80→¶16 C154→¶16 C81→¶16 C82→¶16 C83→¶17 C84→¶17 C176→¶17 C85→¶17 C86→¶18 C169→¶18 C87→¶18 C143→¶18 C88→¶19 C93→¶19 C89→¶19 C90→¶19 C91→¶20 C92→¶20 C94→¶20 C95→¶21 C103→¶21 C155→¶22 C97→¶22 C156→¶22 C182→¶22 C183→¶22 C98→¶22 C157→¶22 C158→¶22 C99→¶23 C144→¶23 C100→¶23 C101→¶23 C171→¶23 C172→¶23 C102→¶23 C104→¶24 C106→¶24 C105→¶24 C107→¶25 C108→¶25 C159→¶25 C109→¶25 C110→¶26 C111→¶26 C112→¶26 C113→¶27 C114→¶27 C170→¶27 C115→¶27 C116→¶27 C117→¶27 C118→¶27 C119→¶27 C120→¶28 C145→¶28 C121→¶29 C177→¶29 C122→¶29 C123→¶29 C124→¶29 C146→¶29 C125→¶29 C126→¶29 C127→¶29 C128→¶29 C129→¶30 C130→¶30 C132→¶30 C178→¶30 C131→¶30 C133→¶31 C134→¶31 C160→¶31 C135→¶31 C185→¶31 C161→¶31 C136→¶31 C181→¶31 C138→¶32 C139→¶32 C147→¶32 C148→¶32 C184→¶32 C162→¶32 C140→¶32 -->
