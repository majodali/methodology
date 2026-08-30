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

A chat report is governed prose. The P- rules apply to it as its
purpose admits — named citations above all: a report about a document
never cites that document by bare section number.

A report that delivers a written artifact has three duties
(W-008 — reports map their deliverables):

1. **Restatement**: name the parts of the artifact that encode
   decisions already made in the conversation, and which decisions.
2. **Novelty**: name the parts that are new, each with a named pointer
   into the artifact and one sentence on what to review there.
3. **Asks**: end with an explicit list of the decisions and actions
   requested of the reader, or state that there are none.

Any substantive report follows the same structure where it fits. Do
not add empty sections to satisfy the shape (K-005's no-empty-ceremony
principle applies to reports too).

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

## Migration

The P- rules bind new and edited prose from adoption onward. Existing
documents migrate by per-document editorial passes (editorial change,
[vocabulary](vocabulary.md#defined-terms)), highest-traffic
reference documents first. No document requires its own amendment to
be restyled.
