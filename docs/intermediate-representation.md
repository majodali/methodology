# Intermediate representation

Status: active. A Methodology-level specification, adopted 2026-10-26
from the [communication-pipeline](https://github.com/majodali/communication-pipeline)
project (a Portfolio project) at its schema v1.2. Required by
[W-009](rules/working-agreement.md#w-009--the-methodology-corpus-writes-its-deliverables-ir-first)
(the methodology corpus writes its deliverables IR first). Any project
that adopts W-009 by declaration uses it.

Reader: RD-4 (a fresh agent session, [reader catalog](style.md#readers))
in the reasoning, paraphraser or stranger role. The human owner reads
it as RD-4 does when reading an IR instead of the prose rendered from
it. Assumed to know:
[W-008](rules/working-agreement.md#w-008--reports-map-their-deliverables)
(reports map their deliverables),
[P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use)
(terms are defined once and linked at first use), and the
[style guide](style.md), including its Readers table.

## Purpose

An [intermediate representation](vocabulary.md#def-intermediate-representation)
(IR) is the structured form the reasoning role writes before any
prose exists. It holds the terms, claims, relations, evidence and
asks of one communication. Every element carries an identifier. Every
term, claim and cluster also carries a provenance status. Prose is
rendered from the IR by the paraphraser role when the rendering
conditions below select rendering. Otherwise the IR is delivered as
it stands.

The IR removes three failure modes of prose written directly: several
claims compressed into one sentence; referents left unnamed; terms
borrowed from the conversation and used as if defined.

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
| Status | `draft` · `reviewed` · `rendered` · `delivered` |
| Source | the conversation, document or event that occasioned it |
| Normative | optional: `yes` when the prose is normative text, that is a rule, a specification, or any text whose words bind |
| Footprint | optional: the files or directories the work is expected to touch, separated by semicolons; a directory ends in `/` |

A `report` is read by someone who shares the conversation: RD-1 (the
human owner in conversation), RD-2 (the human owner returning) or RD-3
(a delegating agent). A `document` is read by someone who does not
share the conversation: RD-4 (a fresh agent session) or RD-5 (an
external reader). A text that will live under `docs/` is a
`document`.

## Element kinds

Every element has an identifier and a body. Terms, claims and clusters
also carry a provenance status. Relations, evidence and asks do not.
Identifiers are a kind letter and a number, unique within the
document (CK-12). A split claim takes a new number, never a suffix:
`C29`, not `C1a`.

| Kind | Letter | Body | Rule |
|---|---|---|---|
| Term | `T` | the word or phrase; its meaning in this communication; `defined-at:` a link to its definition site when one exists | A term is defined once per IR. Every project-specific term used in a claim appears here. A term with a definition site links it and does not restate it. A term without one is proposed, rendered as an inline definition, and listed for ratification (P-008). |
| Claim | `C` | one statement | A claim makes one statement and names every referent inside itself (the referent rule below). A claim may carry `evidence: E<n>` and, for a report to a human-owner reader, `part: covered` or `part: changed`. Without a part, a decided claim renders under *What is already covered* and a proposed claim under *What changed*. |
| Cluster | `G` | `cluster: C<a>, C<b>, …` with an optional topic claim first | The paraphraser renders a cluster as one paragraph, in the order given. A claim belongs to at most one cluster. |
| Relation | `R` | `C<a> <verb> C<b> because <reason>` | Verbs: `supports`, `depends-on`, `contradicts`, `refines`. The reason is one sentence or a claim identifier. Cross-claim references are relations, never pronouns in a claim. |
| Evidence | `E` | a pointer (file and line, commit, message date, URL) and what it shows | Evidence is cited by a claim's `evidence:` field, never free-standing. |
| Ask | `A` | a decision or action requested of the reader; `Depends:` the claims or asks it rests on | Every IR for RD-1 or RD-2 (either human-owner reader) has an Asks section, holding asks or the single line `A0. No asks.` |

### The referent rule

A referent is anything a claim refers to: a document, a project, a
rule, a person, a role, an earlier claim's subject. A claim names each
referent inside itself. A pronoun or determiner phrase (`it`, `this`,
`that`, `these`, `those`, `the other`, `the above`, `the former`, `the
latter`, `the same`) is legal only when its antecedent is a noun phrase
earlier in that claim. A claim that needs an earlier claim refers
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

A term with status `proposed` is an unratified term. The count of
unratified terms per IR is recorded: it is the mechanical reading of
the unratified-vocabulary indicator of
[convergence](vocabulary.md#def-convergence).

## Mechanical checks

A lint or a stranger reports each of these as a finding.
methodology-tools runs them as `mtool ir check`.

| Check | Name | Finding when |
|---|---|---|
| CK-01 | referent rule | a claim contains a pronoun or determiner phrase from the referent rule with no noun-phrase antecedent earlier in that claim. "This specification restates" names its referent and passes; "This is fine" does not |
| CK-02 | claim length | a claim exceeds 40 words |
| CK-03 | compound claim | a claim joins two clauses that could each stand as a claim, by `and`, `but`, `so`, a semicolon or an em-dash. A semicolon or a final `, and` that follows a colon separates list items and is not a join |
| CK-04 | undefined term | a project-specific term appears in a claim and is neither a `T` element nor linked to a definition site |
| CK-05 | provenance | a term, claim or cluster has no provenance status, or a status without its required fields |
| CK-06 | dangling reference | a relation, cluster, `evidence:` or `Depends:` names an identifier that does not resolve |
| CK-07 | header | the Reader header is not a catalog identifier, or the Purpose header lacks `report` or `document` |
| CK-08 | asks section | an IR for RD-1 or RD-2 has no Asks section |
| CK-09 | cluster membership | a claim appears in two clusters |
| CK-10 | section order | the five sections are absent or out of order |
| CK-11 | definition site | a term's `defined-at:` target does not resolve |
| CK-12 | identifier uniqueness | two elements carry the same identifier |

What counts as a project-specific term for CK-04: any bolded term, any
capitalized multi-word phrase that is not a proper name, and any word
in the project vocabulary.

## Rendering rule

The paraphraser renders one claim as one sentence, or one cluster as
one paragraph in the cluster's order. The paraphraser introduces no
new claim and drops no claim. The paraphraser may add connective prose: a sentence
that asserts nothing the IR holds and exists to join claims for the
reader. Relations and evidence are not rendered as sentences. A term
with a definition site is linked at its first use in the unit P-008 (terms are defined
once and linked at first use) defines, and bare after. A term the IR introduces is defined in a
sentence of its own before its first use and listed under *Terms
introduced*. For RD-5 a link becomes an inline gloss. For the
human-owner readers, a claim renders under the part its `part:` field
names. Without one, decided renders under *What is already covered*
and proposed under *What changed*. The rendering follows the style
guide's rows for the IR's reader. The rendering states an empty Asks
section as "No asks."

Normative text is rendered by the reasoning role, the agent that
wrote the IR, not by the paraphraser, because a paraphrase could
change its force. A stranger reads it, the reasoning role fixes the
findings, and a stranger reads the fixed text again. The second
round's verdict is the text's readability (owner ruling, 2026-10-26,
after four normative texts reviewed once were all unreadable before
fixes and unmeasured after).

The paraphraser appends a render map: one comment line of the form
`<!-- render map: C1→¶1 C2→¶1 … -->` listing where each claim
landed. A round-trip check reads the map and reports claims absent
from it, identifiers in it that the IR does not hold, and the ratio
of prose sentences to claims.

## Rendering conditions

Whether prose is rendered from an IR, and whether a stranger reviews
it, is decided from the IR and one further input: whether the owner
asked for a review of this output. The inputs from the IR are its
reader, its purpose, its claim count, its proposed-term count, the
count of asks with a `Depends:` field, and the length of its longest
claim. The mechanical checks run in every case. The first row whose
condition holds decides.

| Condition | What follows |
|---|---|
| the owner asked for a review of this output | the paraphraser renders, then a stranger reviews |
| purpose is `document` and the header carries `Normative: yes` | the reasoning role renders; a stranger reviews IR and prose; after the fixes a stranger reviews again |
| purpose is `document` | the paraphraser renders, then a stranger reviews |
| reader is RD-4 or RD-5 | the paraphraser renders, then a stranger reviews |
| proposed terms > 0 | the paraphraser renders, with the ratification ask |
| reader is RD-2 | the paraphraser renders |
| reader is RD-1 and (claims > 6 or dependent asks > 0 or longest claim > 30 words) | the paraphraser renders |
| reader is RD-3 and (claims > 12 or dependent asks > 0) | the paraphraser renders |
| reader is RD-1 or RD-3 | the checks only; the IR is delivered as it stands |

The counts in the conditions are provisional. The communication-
pipeline project's dispatch log is the data that tunes them, and a
change to a count is an editorial change while it changes no
obligation. The stranger review of a report to RD-1 or RD-3 runs only
when the owner asks for it (owner ruling of 2026-10-25, recorded in
that project's
[branch-point.md](https://github.com/majodali/communication-pipeline/blob/main/docs/branch-point.md)).

## The footprint

An IR may declare, in its Footprint header, the files or directories
its work is expected to touch. After the work, the declaration is
compared with the files the branch changed. A changed file that was
not declared is a surprise. A declared file that did not change is a
miss. The two counts are the mechanical reading of the
prediction-surprise indicator of
[convergence](vocabulary.md#def-convergence), recorded per IR with
the unratified-term count.

## When an IR is required at all

A document always starts as an IR. A report to RD-1 or RD-3 may be
written as prose directly, with the style guide's mechanical checks,
when it introduces no term, records no decision, and states no
register fact. A register fact is a statement about the state of a
Register (vocabulary, Artifact types) or of a row in one. A term, a
decision or a register fact requires the IR, because each is content
a model would hold (the owner ruling of 2026-10-25 cited above).

## Lifecycle

An IR's mutability follows the designation (vocabulary, Designations)
of its prose. The IR of an active document (a plan, a specification)
is edited whenever the document is. A disagreement between the two is
a defect in the prose. The IR of a delivered report (a chat message,
a PR body) is a record: its Status becomes `delivered` and it is not
edited after.

Ratification of a `proposed` term adds a row with an anchor to the
project vocabulary, which becomes the term's definition site (P-008).
Ratified terms and decided claims are the first entries of a
project's conceptual model, the formal project models the
[Backlog](backlog.md) lists as the owner's horizon.

## History

Adopted at v1.2 of the communication-pipeline project's schema, whose
`docs/ir-schema.md` records the versions v0 to v1.2. From this
adoption the specification is amended here. CK-12 was added at
adoption after a stranger review found identifier uniqueness stated
without a check. The Footprint header and the second stranger round
for normative text were added on 2026-10-26 from that project's
schema v1.3 and the owner's ruling at its chunk 4 gate.
