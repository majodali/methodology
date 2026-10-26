# Intermediate representation

Status: active. Specification (methodology level) adopted from the
communication-pipeline pilot's schema v1.2 (chunks 1 to 3, October
2026). Required by
[W-009](rules/working-agreement.md#w-009--the-methodology-corpus-writes-its-deliverables-ir-first)
(the methodology corpus writes its deliverables IR first); available
to any project that adopts W-009 by declaration.

Reader: RD-4 (a fresh agent session, [reader catalog](style.md#readers))
in the reasoning, paraphraser or reviewer role, or the human owner
reading an IR instead of the prose rendered from it. Assumed to know:
[W-008](rules/working-agreement.md#w-008--reports-map-their-deliverables)
(reports map their deliverables), [P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use)
(terms are defined once), and the [style guide](style.md).

## Purpose

An intermediate representation (IR) is the structured form the
reasoning role writes before any prose exists. It holds the terms,
claims, relations, evidence and asks of one communication. Every
element carries an identifier and a provenance status. Prose is
rendered from the IR by the paraphraser role when the
the rendering thresholds below say so. Otherwise the IR is delivered
as it stands.

The IR removes three failure modes of prose written directly:
several claims compressed into one sentence; referents left unnamed;
terms borrowed from context and used as if defined
(case 001 of the pipeline's evaluation corpus).

## Document form

An IR is a markdown file named `<subject>.ir.md`. It sits beside the
prose it produces, or under `docs/records/` when the prose is a chat
message or a PR body. It opens with four header fields and then holds
five sections in a fixed order: Terms, Claims, Relations, Evidence,
Asks. The Claims section may use any sub-headings.

| Header field | Value |
|---|---|
| Reader | one entry from the [reader catalog](style.md#readers), by identifier |
| Purpose | `report` or `document`, then one sentence saying what the communication is for |
| Status | `draft` · `reviewed` · `rendered` · `delivered` |
| Source | the conversation, document or event that occasioned it |

A `report` is read by someone who shares the conversation: RD-1 (the
human owner in conversation), RD-2 (the human owner returning) or RD-3
(a delegating agent). A `document` is read by someone who does not,
RD-4 (a fresh agent session) or RD-5 (an external reader), or will live
under `docs/`.

## Element kinds

Every element has an identifier and a body. Terms, claims and clusters
also carry a provenance status. Relations, evidence and asks do not
(v1.1, below). Identifiers are a kind letter and a number, unique
within the document. A split claim takes a new number, never a suffix:
`C29`, not `C1a`.

| Kind | Letter | Body | Rule |
|---|---|---|---|
| Term | `T` | the word or phrase; its meaning in this communication; `defined-at:` a link to its definition site when one exists | A term is defined once per IR. Every project-specific term used in a claim appears here. A term with a definition site links it and does not restate it; the rendering links that site at first use. A term without one is proposed, rendered as an inline definition, and listed for ratification ([P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use) (terms are defined once)). |
| Claim | `C` | one statement | A claim makes one statement and names every referent inside itself (the referent rule below). A claim may carry `evidence: E<n>` and, for a report to a human-owner reader, `part: covered` or `part: changed`. Without a part, a decided claim renders under *What is already covered* and a proposed claim under *What changed*. |
| Cluster | `G` | `cluster: C<a>, C<b>, …` with an optional topic claim first | The paraphraser renders a cluster as one paragraph, in the order given. A claim belongs to at most one cluster. |
| Relation | `R` | `C<a> <verb> C<b> because <reason>` | Verbs: `supports`, `depends-on`, `contradicts`, `refines`. The reason is one sentence or a claim identifier. Cross-claim references are relations, never pronouns in a claim. |
| Evidence | `E` | a pointer (file and line, commit, message date, URL) and what it shows | Evidence is cited by a claim's `evidence:` field, never free-standing. |
| Ask | `A` | a decision or action requested of the reader; `Depends:` the claims or asks it rests on | Every IR for RD-1 (the human owner in conversation) or RD-2 (the human owner returning) has an Asks section, holding asks or the single line `A0. No asks.` |

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
unratified terms per IR is recorded (the owner's unratified-vocabulary
indicator, "Convergence and Divergence", 2026-10-22).

## Mechanical checks

A lint or reviewer reports each of these as a finding. Identifiers are
`CK-nn`.

| Check | Finding when |
|---|---|
| CK-01 | a claim contains a pronoun or determiner phrase from the referent rule with no noun-phrase antecedent earlier in that claim. "This specification restates" names its referent and passes; "This is fine" does not |
| CK-02 | a claim exceeds 40 words |
| CK-03 | a claim joins two clauses that could each stand as a claim, by `and`, `but`, `so`, a semicolon or an em-dash. A semicolon or a final `, and` that follows a colon separates list items and is not a join |
| CK-04 | a project-specific term appears in a claim and is neither a `T` element nor linked to a definition site |
| CK-05 | a term, claim or cluster has no provenance status, or a status without its required fields |
| CK-06 | a relation, cluster, `evidence:` or `Depends:` names an identifier that does not resolve |
| CK-07 | the Reader header is not a catalog identifier, or the Purpose header lacks `report` or `document` |
| CK-08 | an IR for RD-1 or RD-2 (either human-owner reader) has no Asks section |
| CK-09 | a claim appears in two clusters |
| CK-10 | the five sections are absent or out of order |
| CK-11 | a term's `defined-at:` target does not resolve |

What counts as a project-specific term for CK-04: any bolded term, any
capitalized multi-word phrase that is not a proper name, and any word
in the project vocabulary.

## Rendering rule

The paraphraser renders one claim as one sentence, or one cluster as
one paragraph in the cluster's order. It introduces no new claim and
drops no claim. It may add connective prose: sentences that assert
nothing a model would hold and exist to join claims for the reader.
Relations and evidence are not rendered as sentences. A term with a
definition site is linked at its first use in the unit [P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use) (terms are defined once) names, and bare after. A term the IR
introduces is defined in a sentence of its own before its first use
and listed under *Terms introduced*. For RD-5 a link becomes an inline
gloss. For the human-owner readers, a claim renders under the part its
`part:` field names. Without one, decided renders under *What is
already covered* and proposed under *What changed*. Normative text (a
rule, a specification) is rendered by the reasoning role, not the
paraphraser, and the stranger still reads it (the rendering thresholds below). It follows the
[style guide](style.md) for the IR's reader. It states an
empty Asks section as "No asks." The round-trip check
re-extracts claims from the prose and diffs them against the IR: the
paraphraser appends a render map naming where each claim landed, and
a lint reports claims absent from the map.

## Lifecycle

An IR's mutability follows its prose's designation. The IR of an
active document (a plan, a specification) is edited whenever the
document is, and a disagreement between the two is a defect in the
prose. The IR of a delivered report (a chat message, a PR body) is a
record: its Status becomes `delivered` and it is not edited after.

Ratification of a `proposed` term adds a row with an anchor to the
project [vocabulary](vocabulary.md), which becomes the term's
definition site. The [P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use) (terms are defined once) has the
steps. Ratified terms and decided claims are the first entries of a
project's conceptual model, the formal-model horizon the
[Backlog](backlog.md) records.

## Rendering thresholds

Whether prose is rendered from an IR is decided from the IR alone:
its reader, its purpose, its claim count, its proposed-term count,
the count of asks with a `Depends:` field, and the length of its
longest claim. The lints run in every case. The first row whose
condition holds decides.

| Condition | What follows |
|---|---|
| the owner asked for a review of this output | render, then a stranger review |
| purpose is `document` and the header carries `Normative: yes` | the author renders; a stranger reviews IR and prose |
| purpose is `document` | render, then a stranger review |
| reader is RD-4 or RD-5 | render, then a stranger review |
| proposed terms > 0 | render, with the ratification ask |
| reader is RD-2 | render |
| reader is RD-1 and (claims > 6 or dependent asks > 0 or longest claim > 30 words) | render |
| reader is RD-3 and (claims > 12 or dependent asks > 0) | render |
| reader is RD-1 or RD-3 | lint only; the IR is delivered as it stands |

The thresholds are provisional; the pipeline's evaluation corpus
tunes them, and a change here is an editorial change while it changes
no obligation. The stranger review of a report to RD-1 or RD-3 runs
only when the owner asks for it (owner ruling, 2026-10-25).

## When an IR is required at all

A report to RD-1 (the human owner, in conversation) or RD-3 (a
delegating agent) may be written as prose directly, with the style
guide's mechanical checks, when it introduces no term, records no
decision, and makes no claim about the state of a register. Any of
those three requires the IR, because each is content a model would
hold: a term, a decision, or a register fact (owner ruling,
2026-10-25). Documents always start as an IR.

## History

Adopted at v1.2 of the pipeline's schema. The pipeline's
`docs/ir-schema.md` records the changes from v0 to v1.2; from this
adoption the specification is amended here.
