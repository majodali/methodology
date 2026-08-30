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
