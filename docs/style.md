# Documentation style

The house style for project documentation. This is a Methodology-level
(Level 2) document, amendable through the
[release process](release-process.md). The rules that bind projects to
it are the P- section of the [rule corpus](rules/prose.md); this
document holds the decisions those rules cite.

Motivated by the documentation review of 2026-08-30. The review found
the same defects in every governed project: long chained sentences
(mean 30–37 words), rhetoric inside normative text, bold used for
emphasis, identifiers cited without names, and registers filled with
narrative.

## Base guides

Two external guides are adopted by citation. Restating them here is an
error; this document records only house decisions.

- [Diátaxis](https://diataxis.fr/) — document architecture. Governed
  documents are almost all *reference* documents in the Diátaxis
  sense. Structure them for lookup. Put explanation in linked
  documents, not inline.
- [Google Developer Documentation Style Guide](https://developers.google.com/style)
  — prose mechanics: sentence construction, word choice, headings,
  lists, tables, link text.

Where this document is silent, the base guides decide. Where all are
silent, write plainly and raise the gap at a review round.

## House decisions

### Purpose: reference, not reading

Write every document for the reader who arrives mid-document from a
link or a search. Front-load each section's claim. Make each section
answer its own header without requiring the text above it. A document
that must be read in full to be used is misconstructed.

### Sentences

One idea per sentence. Target 25 words or fewer. Do not extend a
sentence with chained em-dashes or semicolons; split it. Delete words
that add tone but not content. Rhetorical devices — dramatic
accumulation, aphorism, suspense — do not belong in governed
documents.

### Bold

Bold marks structure only. Its two legal uses:

1. Field labels in fielded entries (for example **Statement**,
   **Migration note**).
2. A term at its definition site.

Bold is never emphasis. If a sentence needs emphasis, rewrite the
sentence.

### Reader statement

A document under `docs/` opens with its reader: who it is for and what
they are assumed to know, with a link to where that knowledge is
defined (P-007 — documents state their reader). Name the reader from
the catalog below by identifier, or describe the reader in one
sentence when no entry fits. A text that assumes the conversation
that produced it is a report, governed by W-008 (reports map their
deliverables), not a document.

### Readers

The reader catalog. Each entry names what the reader is assumed to
know, what the text owes them, and the readability test a reviewer
answers for that reader. RD-1 to RD-3 are W-008's report audiences;
RD-4 and RD-5 read documents. An entry is added only when a real text
had a reader none of these describes, and that text is cited.

| Id | Reader | Assumed to know | Needs from the text | Readability test |
|---|---|---|---|---|
| RD-1 | the human owner, in the conversation that produced the text | the conversation; the methodology; the portfolio; the project's documents | the asks first; what is new against what was settled | After the first screen, can the owner list every ask? Does any sentence carry two claims the owner could decide separately? |
| RD-2 | the human owner, returning after a gap or in another session | the methodology; the portfolio; the project's documents, not the conversation | the current state in one paragraph citing the last recorded state; what changed; the asks | Without the transcript, can the owner say what was decided and what is asked? |
| RD-3 | a delegating agent that dispatched the work | the task it dispatched; the project's documents; the methodology at the project's pin | status; a map of the deliverable; the asks | From the status and asks alone, can the agent decide its next dispatch? |
| RD-4 | a fresh agent session, including an auditor or reviewer | the methodology at the project's pin; what the project's documents state, and nothing recorded nowhere | terms defined or cited before use; the problem before the solution; one definition site per term; status that is true | Can the session state the document's problem, its terms and its decision, without the conversation? |
| RD-5 | a person outside the project and the methodology | the general domain | plain language; standard names for patterns; a gloss wherever precision needs a term; no bare identifier | Could a reader with no repository access act on the text? |

### Terms are defined once

A term with a project-specific meaning has one definition site: a
vocabulary row or a defining heading, carrying the anchor
`<a id="def-<slug>"></a>` (P-008 — terms are defined once and linked
at first use). Link the site at the term's first use in the unit (the
document for a report, the section for a reference document) and
write the term bare after. For RD-5 replace the link with an inline
gloss. A term with no site is defined in one sentence at first use
and listed under *terms introduced* for the owner to ratify or strike
(W-008). A ratified term gets its vocabulary row; a struck term is
removed from the deliverable.

### Citations carry names

An identifier alone is not a reference. On first use in a document,
give an identifier its name: "W-006 (branches are single-use)",
"D68 (methodology adoption)". Link it where a link target exists.
Identifiers from another repository always carry their name, in every
document. Section numbers follow the same rule: "§6 (launch
playbook)", never "§6" alone.

### Headers state contents

A header is a noun phrase or a claim that predicts its section's
content. A reader scanning only headers must be able to locate any
fact in the document. Do not use teaser headers, jokes, or bare
identifiers as headers; an identifier in a header carries its name,
as in prose.

### Registers hold rows

A register entry is a uniform fielded row with bounded length: what,
when, status, pointer. Reasoning lives in a linked decision, design,
or plan document — never in the register. The
[Audit log](audits.md) entry format is the model. Each register
declares its row shape in its own header.

### Rule bodies are labeled

A rule body separates its parts with labeled fields: **Statement**
(the norm), **Rationale** (why, optional), **Exceptions** (bounded
carve-outs, if any). Format details:
[rule corpus organization](rules/README.md).

### Structure first

Prefer structure the tooling can read — fields, rows, named links —
over prose that only a person can read. Write so a parser could lift
the document into nodes and edges: claims as sentences, reasoning
under labels, references by name. Prose carries what structure cannot.
This keeps documents ready for the owner's formal project-model
horizon (recorded 2026-08-30 in the [Backlog](backlog.md)), where
reading and referencing become query and transform operations.

### Reports and summaries

A report is governed prose regardless of who reads it. The P- rules
apply to it as its purpose admits — named citations above all: a
report about a document never cites that document by bare section
number.

A report's duties scope by its report audience
(W-008 — reports map their deliverables):

A report addressed to the human owner (the principal audience) leads
with the outcome or the decision needed, not the process that produced
it, and carries four parts in this order:

1. **Asks**: the decisions and actions requested of the reader.
2. **What is already covered**: the parts of the deliverable that
   encode decisions the conversation already settled, and which
   decisions.
3. **What changed**: the parts that are new, each with a named pointer
   into the deliverable and one sentence on what to review there.
4. **Terms introduced**: each term the report or its deliverable uses
   with a meaning that neither the [methodology vocabulary](vocabulary.md)
   nor the project's own vocabulary defines, with one sentence giving
   its meaning. The asks request its ratification or striking. On
   ratification the agent adds a row for the term to the project's
   vocabulary. A struck term is removed from the deliverable.

A report addressed to a delegating agent (the agent audience) carries
its status, a map of what it delivers, and the asks. It lists its
terms introduced when it has any, so the delegating agent can carry
them into its own report. It may omit parts 2 and 3 — the reader
dispatched the work and already holds its context.

An empty part is stated, not dropped, in the part's own words: "No
asks", "We already covered everything in the document", "The content
is all new", "No terms introduced". W-008 carries
the short form of these duties as verbatim text every Agent bootstrap
must hold, so the guidance stays in force late in a session; this
section remains the authority for it. A stated-empty
part is one line, not a section: the declaration is the point, and
padding it into a heading with boilerplate is the empty ceremony
K-005 (companion registers when pressure appears, never before)
forbids.

### Supersession markers

When a decision supersedes content that cannot be reworked in the same
deliverable, each known-stale location gets a marker, placed where the
reader reads:

> Superseded by D-041 (single-seam design) on 2026-08-30; this section
> describes the pre-decision state and awaits rework.

The marker is a blockquote beginning "Superseded by", citing the
decision by identifier and name (P-004 — citations carry names), and
saying what the reader should do with the stale text. The fixed prefix
keeps markers greppable for tooling and editorial passes. A register
kept as history is exempt entry-by-entry; its header says so once.

### The information lifecycle

Information moves through phases: discussed (chat) → decided (a
ruling or register entry) → encoded (documents, code) → summarized
(reports, register rows) → superseded (marked) → historical (labeled).
Each transition has an owner rule: W-003 (documentation moves in the
same commit) for decided → encoded, W-008 (reports map their
deliverables) for encoded → summarized, K-010 and K-011 (supersession)
for encoded → superseded, the audit and release processes for their
own registers. Bounds on lifecycle duties are expressed in a project's
internal cycles and milestones — review rounds, releases, gates —
never in calendar time (owner principle, 2026-08-30). The lifecycle is
named here so rules share language; it is not a framework. Its full
formalization belongs to the formal project-model horizon recorded in
the [Backlog](backlog.md).

## The editing pass

A change that adds or rewrites more than a few sentences of prose gets
one editing pass against this document before the PR is opened. The
pass is the author's duty, in the same session that wrote the prose.

### Mechanical checks

The mechanical part of the pass is a lint, so it fails instead of
relying on memory. Each check approximates its rule and reports a
warning; the judgment part of the rule stays with the author and the
reviewer. methodology-tools runs them as `mtool style`.

| Rule | Check |
|---|---|
| P-001 | three or more numerals in one sentence; a document whose first section needs the text above it (judgment) |
| P-002 | a sentence over 25 words (warn) or over 35 (flag); two independent clauses joined by `and`, `but`, `so`, a semicolon or an em-dash; a sentence-initial `This`, `That`, `These`, `Those`, `It` with no noun following; `the other`, `the above`, `the former`, `the latter`; fragments of the form `That is X.` and `X is not Y. It is Z.` |
| P-003 | a bold span longer than four words, or bold not followed by `:` and not at a term's definition site |
| P-004 | an identifier (`[A-Z]{1,3}-?\d+`, `§\d+`) whose first occurrence is not followed by a parenthesized name or a link; for RD-5, every occurrence |
| P-005 | a header that is only an identifier, ends in `?`, or contains an em-dash |
| P-006 | an entry over 60 words in a register whose header declares a row shape |
| P-007 | no `Reader:` line or *Reader* section within the first twenty lines of a document under `docs/` |
| P-008 | a vocabulary term whose first use in the unit is not linked; a link to a `#def-` anchor that does not resolve; a bolded or capitalized phrase absent from both vocabularies |
| W-008 | a report to RD-1 or RD-2 without the four headings in order; a report to RD-3 without status, map and asks |
| K-010 | a blockquote beginning `Superseded by` whose citation does not resolve |

## Migration

The P- rules bind new and edited prose from adoption onward. Existing
documents migrate by per-document editorial passes (editorial change,
[vocabulary](vocabulary.md#defined-terms)), highest-traffic
reference documents first. No document requires its own amendment to
be restyled.
