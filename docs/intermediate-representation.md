# Intermediate representation

Status: active. A Methodology-level specification, adopted
2026-10-26. Its origin is recorded under History. Required by
[W-009](rules/working-agreement.md#w-009--the-methodology-corpus-writes-its-deliverables-ir-first)
(the methodology corpus writes its deliverables IR first). Any project
that adopts W-009 by declaration uses this specification.

Reader: RD-4 (a fresh agent session, [reader catalog](style.md#readers))
in the reasoning, paraphraser or stranger role. The human owner reads
the specification as RD-4 does when reading an IR instead of the
prose rendered from the IR. Assumed to know:
[W-008](rules/working-agreement.md#w-008--reports-map-their-deliverables)
(reports map their deliverables),
[P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use)
(terms are defined once and linked at first use), and the
[style guide](style.md), including its Readers table.

## Purpose

An [intermediate representation](vocabulary.md#def-intermediate-representation)
(IR) is the structured form the
[reasoning role](vocabulary.md#def-reasoning-role) writes before any
prose exists. It holds the terms, claims, relations, evidence and
asks of one communication. Every element carries an identifier. Every
term, claim and cluster also carries a provenance status. Prose is
rendered from the IR by the [paraphraser](vocabulary.md#def-paraphraser)
role when the rendering conditions below select rendering. Normative text is rendered by the
reasoning role instead. When no condition selects rendering, the IR
is delivered as it stands.

The IR removes three failure modes of prose written directly:
several claims compressed into one sentence, referents left unnamed,
and terms borrowed from the conversation and used as if defined.

## Document form

An IR is a markdown file named `<subject>.ir.md`. It sits beside the
prose it produces, or under `docs/records/` when the prose is a chat
message or a PR body. It opens with header fields and then holds
five sections in a fixed order: Terms, Claims, Relations, Evidence,
Asks. The Claims section may use any sub-headings.

| Header field | Value |
|---|---|
| Reader | one entry from the [reader catalog](style.md#readers), by identifier |
| Purpose | `report` or `document`, then one sentence saying what the communication is for |
| Status | `draft` · `reviewed` · `rendered` · `delivered`. Each value may be followed by a parenthesis. The parenthesis holds the counts defined under Provenance and under The footprint. The parenthesis also holds the words `review flag` when the owner asked for a review. The reasoning role sets `draft` at creation. It sets `rendered` when prose exists. It sets `reviewed` when the stranger rounds end, by a readable verdict or by the limit, or when the mechanical checks pass for an IR that gets no rounds. It sets `delivered` when the text is sent to its reader |
| Source | the conversation, document or event that occasioned it |
| Normative | optional: `yes` when the prose is normative text, that is a rule, a specification, or any text whose words bind |
| Footprint | optional: the files or directories the IR's deliverable is expected to change, separated by semicolons. A directory ends in `/`. A declared directory covers every file under it. The deliverable of an IR for a PR body is the pull request's changes, which its branch carries. The header is omitted or empty when no branch carries the deliverable, as for a chat message. A footprint declared on an IR whose deliverable no branch carries is ignored |

A `report` is read by someone who shares the conversation: RD-1 (the
human owner in conversation), RD-2 (the human owner returning) or RD-3
(a delegating agent). A `document` is read by someone who does not
share the conversation: RD-4 (a fresh agent session) or RD-5 (an
external reader). A text that will live under `docs/`, outside `docs/records/`, is a
`document`.

## Element kinds

Every element has an identifier and a body. Terms, claims and clusters
also carry a provenance status. Relations, evidence and asks do not.
Identifiers are a kind letter and a number, unique within the
IR (CK-12, identifier uniqueness). A split claim takes a new number, never a suffix:
`C29`, not `C1a`.

| Kind | Letter | Body | Rule |
|---|---|---|---|
| Term | `T` | the word or phrase; its meaning in this communication; `defined-at:` a link to its definition site when one exists | A term is defined once per IR. CK-13 (term uniqueness) tests the mechanical part, equal names. Two definitions of one concept under different names are a stranger finding. Every project-specific term used in a claim appears here or is linked to its definition site (CK-04, undefined term). A term with a definition site links it and does not restate it. A term without one is proposed, rendered as a defining sentence of its own before its first use, and listed for ratification (P-008). |
| Claim | `C` | one statement | A claim makes one statement and names every referent inside itself (the referent rule below). A claim may carry `evidence: E<n>` and, for a report to RD-1 or RD-2, `part: covered` or `part: changed`. A `part:` field decides the claim's part. Without a part, a decided claim renders under *What is already covered*. A proposed or inferred claim renders under *What changed*, because a proposed claim is new and an inferred claim is the reasoning role's inference, not a settled decision (W-008, reports map their deliverables). |
| Cluster | `G` | `cluster: C<a>, C<b>, …` with an optional topic claim first | The paraphraser renders a cluster as one paragraph, in the order given. A claim belongs to at most one cluster. |
| Relation | `R` | `C<a> <verb> C<b> because <reason>` | Verbs: `supports`, `depends-on`, `contradicts`, `refines`. The reason is one sentence or a claim identifier. Cross-claim references are relations, never pronouns in a claim. |
| Evidence | `E` | a pointer (file and line, commit, message date, URL) and what it shows | Evidence is cited by a claim's `evidence:` field, never free-standing. |
| Ask | `A` | a decision or action requested of the reader; `Depends:` the claims or asks it rests on | Every IR for RD-1 or RD-2 (either human-owner reader) has an Asks section, holding asks or the single line `A0. No asks.` |

### The referent rule

A referent is anything a claim refers to: a document, a project, a
rule, a person, a role, an earlier claim's subject. A claim names each
referent inside itself. A bare pronoun or determiner phrase (`it`,
`this`, `that`, `these`, `those`, `the other`, `the above`, `the
former`, `the latter`, `the same`) is legal only when its antecedent
is a noun phrase earlier in that claim. A determiner followed by the
noun it names ("this specification") names its referent and is not
bare. A claim that needs an earlier claim refers
to it by identifier inside a relation, or restates the referent by
name.

### Provenance

Each term, claim and cluster ends with one status in square brackets.
Relations, evidence and asks carry none: a relation is the reasoning
role's inference by definition, evidence is a pointer, and an ask is a
request.

| Status | Form | Meaning |
|---|---|---|
| decided | `[decided: <who>, <date>]` or `[decided: <source>]` | ratified by the human owner, or quoted from a governed document |
| proposed | `[proposed: <IR id or "this IR">]` | put forward here; awaits ratification |
| inferred | `[inferred: R<n>]` | derived by the reasoning role; the relation that derives it is cited |

A term with status `proposed` is an unratified term. The reasoning
role records the count of unratified terms in the Status header's
parenthesis when the IR is delivered. The count is the mechanical
reading of the unratified-vocabulary indicator of
[convergence](vocabulary.md#def-convergence).

## Mechanical checks

A lint or a stranger reports each of these as a finding, except
where a row says information. methodology-tools runs them as
`mtool ir check`.

| Check | Name | Finding when |
|---|---|---|
| CK-01 | referent rule | a claim contains a pronoun or determiner phrase from the referent rule with no noun-phrase antecedent earlier in that claim. "This specification restates" names its referent and passes; "This is fine" does not |
| CK-02 | claim length | a claim exceeds 40 words |
| CK-03 | compound claim | a claim joins two clauses that could each stand as a claim, by `and`, `but`, `so`, a semicolon or an em-dash. A semicolon or a final `, and` that follows a colon separates list items and is not a join |
| CK-04 | undefined term | a project-specific term appears in a claim and is neither a `T` element nor linked to a definition site |
| CK-05 | provenance | a term, claim or cluster has no provenance status, or a status without its required fields |
| CK-06 | dangling reference | a relation, cluster, `evidence:` or `Depends:` names an identifier that does not resolve |
| CK-07 | header | the Reader header is not a catalog identifier, or the Purpose header lacks `report` or `document`, or the two disagree: a `report` for RD-4 or RD-5, or a `document` for RD-1, RD-2 or RD-3 |
| CK-08 | asks section | an IR for RD-1 or RD-2 has no Asks section |
| CK-09 | cluster membership | a claim appears in two clusters |
| CK-10 | section order | the five sections are absent or out of order |
| CK-11 | definition site | a term's `defined-at:` target does not resolve |
| CK-12 | identifier uniqueness | two elements carry the same identifier |
| CK-13 | term uniqueness | two `T` elements have equal names after lower-casing |
| CK-15 | round trip | reported by the round-trip check, which runs only when prose was rendered: a claim absent from the render map (Rendering rule) (violation); an identifier in the map that the IR does not hold (violation). The check also reports the ratio of prose sentences to claims, as information |
| CK-14 | review record | three conditions hold: the rendering conditions select stranger rounds for the IR; the Status is `reviewed` or `delivered`; no review record `<subject>.review.md` with a verdict per round sits beside the IR |

What counts as a project-specific term for CK-04: any bolded term, any
capitalized multi-word phrase that is not the name of a person,
product or place, and any term in the project's `docs/vocabulary.md`.

## Rendering rule

The paraphraser renders one claim as one sentence, or one cluster as
one paragraph in the cluster's order. The paraphraser introduces no new claim and drops no claim. A new claim is caught by the stranger, who reports a sentence in the
prose that no claim of the IR holds. A dropped claim is caught by the
round-trip check. The paraphraser may add connective prose: a sentence
that asserts nothing the IR holds and exists to join claims for the
reader. Relations and evidence are not rendered as sentences. A term
with a definition site is linked at its first use in the unit. The
unit is defined by P-008 (terms are defined once and linked at first
use): the whole text for a report and the section for a document.
After the first use the term is written without a link. A term the IR introduces is defined in a
sentence of its own before its first use and listed under *Terms
introduced*. For RD-5 a link becomes an inline gloss. For the
human-owner readers, a claim renders under the part its `part:` field
names. Without one, a decided claim renders under *What is already
covered*, and a proposed or inferred claim under *What changed*. The rendering follows the style
guide's rows for the IR's reader. The rendering states an empty part in the words W-008 gives for
that part.

Normative text is rendered by the reasoning role, the agent that
wrote the IR, not by the paraphraser, because a paraphrase could
change its force. The reasoning role then runs the stranger rounds
of the next subsection.

Whoever rendered the prose appends a render map: the paraphraser,
or the reasoning role for normative text. The render map is one
comment line of the form `<!-- render map: C1→¶1 C2→¶1 … -->`
listing where each claim landed. `C1→¶1` reads: claim C1 landed in paragraph 1, paragraphs
counted from the start of the prose. The render map is part of the
prose file. When the prose is sent as a chat message or a PR body,
the sent copy omits the render map, and the prose file beside the
IR keeps it. The round-trip check is a lint that reads the map (CK-15, round
trip). It reports claims absent from the map. It reports identifiers
in the map that the IR does not hold. It reports the ratio of prose
sentences to claims as information.

### Stranger rounds

A stranger review runs in rounds until a round returns the verdict
readable. The reasoning role, the agent that wrote the IR, starts
each round by dispatching a stranger. The stranger is an agent
instance with a fresh context. The stranger is never the reasoning
role itself and never the instance of an earlier round. The stranger
reviews the IR and the rendered prose against the reader's
readability test ([reader catalog](style.md#readers)) and returns
findings and a verdict. The reasoning role records the round's
findings, each finding's disposition, and the verdict in the review
record, the file `<subject>.review.md` beside the IR (CK-14, review
record).

A verdict of readable ends the review. The text delivered is the
text that round judged. The reasoning role records that verdict in the review record, and
writes `readable` in the IR's Status parenthesis. Findings a readable round lists are recorded by the reasoning role
in the review record as accepted findings. The reasoning role fixes the accepted findings at the text's next
edit. An edit that leaves an accepted finding unfixed is a defect in
the edit. That edit starts new rounds when the rendering conditions
select rounds for the edited text.

A verdict of not readable is followed by fixes to the IR. When the
reasoning role rendered the prose, the reasoning role fixes the prose
too. When the paraphraser rendered the prose, the reasoning role
sends the fixed IR to the paraphraser, which renders it again with a
new render map. The next round reviews the fixed IR and the prose as
it then stands.

The review stops after ten rounds without a readable verdict. At the limit the reasoning role does not deliver the text. The
reasoning role sets the IR's Status to `reviewed`, as at any end of
the rounds. The review record states that the limit was reached. The
owner decides, when accepting or rejecting the deliverable, whether
the text is delivered, reworked or withdrawn. Rework restarts the
rounds with a new count from one. An amendment is a change to the
methodology corpus. For an amendment the owner's decision is its
adjudication under
[Article 8](constitution.md#article-8--amendments-versions-and-migration)
(amendments, versions, and migration).

The rounds apply to every stranger review the rendering conditions
select, whatever the text's purpose.

### Meta-review

A meta-review is a review of a text's review record and of the text
itself, reporting to the owner whether the process needs a change. A
text whose review record holds three or more rounds is a meta-review
subject. When the reasoning role starts a third round, it writes the
line `Meta-review: pending` in the review record. The reasoning role
also names the subject in the asks of the report that delivers the
text (W-008). The meta-review is performed by a session that had no
part in the text's rounds. While the communication-pipeline project
exists, that session is one of its sessions, and afterwards a session
of the methodology repository (History records the arrangement). The
meta-review is due before the owner accepts the deliverable, and the
performing session delivers it as its report to the owner. When it is
delivered, the review record's line becomes `Meta-review: delivered`,
with a link. A `Meta-review: pending` line in the review record of an
accepted deliverable is a defect the next audit reports.

## Rendering conditions

Whether prose is rendered from an IR, and whether stranger rounds
review the prose, is decided from the IR and the owner's review flag.
The review flag is set, as the words `review flag` in the Status
parenthesis, when the owner asked for a review of the IR's prose. The inputs from the IR are its reader, its purpose and its Normative
header, plus four counts: claims, proposed terms, dependent asks (asks
with a `Depends:` field), and the words of its longest claim. The mechanical checks run in every
case. The first row whose condition holds decides.

| Condition | What follows |
|---|---|
| the header carries `Normative: yes` | the reasoning role renders and runs the stranger rounds (Rendering rule, Stranger rounds) |
| the review flag is set | the paraphraser renders, then the stranger rounds |
| purpose is `document` | the paraphraser renders, then the stranger rounds |
| reader is RD-4 or RD-5 | the paraphraser renders, then the stranger rounds |
| proposed terms > 0 | the paraphraser renders. The asks include, per proposed term, an ask that the owner ratify or strike that term (W-008, terms introduced) |
| reader is RD-2 | the paraphraser renders |
| reader is RD-1 and (claims > 6 or dependent asks > 0 or longest claim > 30 words) | the paraphraser renders |
| reader is RD-3 and (claims > 12 or dependent asks > 0) | the paraphraser renders |
| reader is RD-1 or RD-3 | the checks only; the IR is delivered as it stands, its sections standing for W-008's parts: Asks, decided claims (what is already covered), proposed and inferred claims (what changed), proposed terms (terms introduced). The reasoning role adds one line at the IR's end stating each empty part in W-008's words |

A change to a count in the conditions is an amendment, because it
changes which row holds. A report to RD-1 or RD-3 that is not normative gets a
stranger review only when the owner's review flag is set.

## The footprint

An IR may declare, in its Footprint header, the files or directories
its deliverable is expected to change. When the header is absent or
empty, no comparison is made. An IR whose deliverable is a chat message has no footprint, because
no branch carries a chat message. The deliverable of an IR for a PR
body is the pull request's changes, which its branch carries.
When the IR's Status becomes `reviewed`, and again at delivery, the
reasoning role compares the declaration with the files the branch
changed since its base branch. The counts recorded are those of the last comparison made. When the
branch is merged or deleted before delivery, the last comparison is
the one at `reviewed`. When no branch diff exists at `reviewed`,
because the deliverable sits on the base branch itself or the branch
was merged before, the counts are recorded as `not comparable`. A lint may run the comparison for the reasoning role. A file is changed when the branch's diff adds, modifies, deletes or
renames it. A rename counts as one changed file. A renamed file is declared when
either of its paths is declared. The IR itself and its review record are not counted. A changed
file that no declared file or directory covers is a surprise. A
changed file that a declared entry covers is neither a surprise nor a
miss. A declared file that did not change is a miss. A declared
directory under which no file changed is a miss. The count of
surprises and the count of misses are the mechanical reading of the
prediction-surprise indicator of
[convergence](vocabulary.md#def-convergence). The reasoning role
records both counts in the Status header's parenthesis when the IR is
delivered, beside the unratified-term count.

## When an IR is required at all

A document always starts as an IR. A report to RD-2 always starts as an IR, because its opening
paragraph, which re-establishes the current state (reader catalog,
RD-2), is rendered from the IR. A report to RD-1 or
RD-3 may be written as prose directly, with the style guide's mechanical checks,
when it introduces no term, records no decision, and states no
register fact. A register fact is a statement about the state of a
Register (vocabulary, Artifact types) or of a row in one. A term, a decision or a register fact requires the IR, because each
is content a model would hold.

## Lifecycle

An IR's mutability follows the designation (vocabulary, Designations)
of its prose. The IR of an active document (a plan, a specification)
is edited whenever the document is. The IR is the authority for an active document. A disagreement
between the IR and the document is a defect in the prose, fixed by
rendering again. The IR of a delivered report (a chat message,
a PR body) is a record: its Status becomes `delivered` and it is not
edited after.

Ratification of a `proposed` term adds a row with an anchor to the
project vocabulary. That row becomes the term's definition site
(P-008).
Ratified terms and decided claims are the first entries of a formal
project model, the horizon the [Backlog](backlog.md) records under
"Formal project models".

## History

Adopted at v1.2 of the schema of the
[communication-pipeline](https://github.com/majodali/communication-pipeline)
project (a project in the
[Portfolio register](vocabulary.md#def-portfolio-register)), whose
`docs/ir-schema.md` records the versions v0 to v1.2. The communication-pipeline project's record of the IRs it routed is
the data from which a count may be proposed for amendment. From the adoption of 2026-10-26 the specification is amended here. CK-12 was added at
adoption after a stranger review found identifier uniqueness stated
without a check. The Footprint header was added on 2026-10-26, from
the communication-pipeline project's schema v1.3. The second
stranger round for normative text was added on 2026-10-26, by owner
ruling, in methodology PR #50. The motivating instance
([Article 6](constitution.md#article-6--inclusion-every-rule-earns-its-keep),
inclusion) was the four normative texts of October 2026, methodology
PRs #46 to #49. Each of the four texts was reviewed once. Each of
the four was judged not readable before its fixes. None of the four
was measured after its fixes. The record is
[evaluation case 004](https://github.com/majodali/communication-pipeline/blob/main/eval/cases/004-normative-text-reviews-2026-10-26.md)
in the communication-pipeline project. On 2026-10-26 the two-round
rule of PR #50 was replaced by rounds until readable, with a limit of
ten and the meta-review trigger. The reason was that the second round on PR #50's own text had
returned not readable. No third round ran before PR #50 merged. Two rulings of 2026-10-25 are recorded in the communication-pipeline
project's
[branch-point.md](https://github.com/majodali/communication-pipeline/blob/main/docs/branch-point.md).
The first: a report to RD-1 or RD-3 needs an IR only for a term, a
decision or a register fact. The second: a report to RD-1 or RD-3 gets a stranger review only on
the owner's flag.
