# P — Prose & presentation

Opened by amendment (v1.4.0 candidate) after the documentation review
of 2026-08-30, which found the same writing defects across every
governed project. The rules cite the [style guide](../style.md); the
style guide holds the decisions, the rules hold the duties. See the
[rule corpus organization](README.md).

Every rule here carries the C0 baseline via the widening exception
(owner ruling, 2026-08-30): the rules mint no coverage duties — each
binds only documentation that exists, so tier does not change the
burden. A C0 project owes no documents; the documents it writes anyway
follow the same style.

### P-001 — Documents are structured for reference
Applies: [C0+]
Keywords: MUST, SHOULD
Motivated-by: the 2026-08-30 documentation review — every governed project's docs required full reading to locate single facts
Cites: [style guide](../style.md); [Diátaxis](https://diataxis.fr/) (reference mode)

**Statement**: A governed document MUST be usable by a reader who
arrives at any section from a link or search: each section answers its
own header without the text above it, and each section front-loads its
claim. Explanation SHOULD live in linked documents, not inline.

**Rationale**: The corpus is read by lookup — during audits, rule
selection, and cross-repo citation — far more often than in full.

### P-002 — One idea per sentence
Applies: [C0+]
Keywords: SHOULD, MUST NOT
Motivated-by: the 2026-08-30 review metrics — mean sentence length 30–37 words in every project, ~30% of sentences over 35 words, em-dash chaining as the mechanism (62 in the constitution's 404 lines)
Cites: [style guide](../style.md); [Google style guide](https://developers.google.com/style/sentence-structure)

**Statement**: A sentence SHOULD carry one idea in at most about 25
words. Prose MUST NOT extend sentences by chained em-dashes or
semicolons, and MUST NOT use rhetorical devices — dramatic
accumulation, aphorism, suspense — in normative or register text.

**Rationale**: Long chained sentences hide which clause is the norm.
Audits check the SHOULD statistically and warn, not fail.

### P-003 — Bold marks structure, never emphasis
Applies: [C0+]
Keywords: MUST
Motivated-by: the 2026-08-30 review — bold used interchangeably for field labels, term definitions, and emphasis ("**Gate review pending.**", "**live = live**"), destroying its scanning value
Cites: [style guide](../style.md)

**Statement**: Bold MUST appear only as a field label in a fielded
entry or on a term at its definition site. Emphasis is never a legal
use.

### P-004 — Citations carry names
Applies: [C0+]
Keywords: MUST
Motivated-by: the 2026-08-30 review — "the D6 split's siblings" in this repo's Release register cites another project's decision number, unresolvable from where it stands; "(§6)", "chunk 4", and bare rule IDs throughout the portfolio
Cites: [style guide](../style.md)

**Statement**: An identifier MUST carry its name on first use in a
document — "W-006 (branches are single-use)", "§6 (launch playbook)" —
and MUST be linked where a target exists. An identifier from another
repository MUST carry its name at every use.

**Rationale**: An identifier alone demands the reader hold the
referenced document's map in memory; the name makes the reference
self-sufficient (P-001 — documents are structured for reference).

### P-005 — Headers state their contents
Applies: [C0+]
Keywords: SHOULD
Motivated-by: the 2026-08-30 review — identifier-only headers ("C1.5b: `*_attach` collapse") and teaser headers requiring the section body to decode
Cites: [style guide](../style.md)

**Statement**: A header SHOULD be a noun phrase or claim that predicts
its section's content, so a reader scanning only headers can locate
any fact. An identifier in a header carries its name, as in prose
(P-004 — citations carry names).

### P-006 — Registers hold uniform rows
Applies: [C0+]
Keywords: MUST
Motivated-by: the 2026-08-30 review — Backlog entries of 100–250 words with nested parentheticals across the portfolio, burying the register's scan function; the Audit-log entry format as the existing counter-model
Cites: [style guide](../style.md); [audit process](../audit-process.md) (entry format)

**Statement**: A register MUST declare its row shape in its header,
and its entries MUST follow that shape with bounded length: what,
when, status, pointer. Reasoning MUST live in a linked document, not
in the entry.

**Rationale**: A register is read by scanning. The methodology's own
registers (Audit log, Release register) already demonstrate the fielded
shape; this rule extends it to all registers, Backlogs included.

### P-007 — Documents state their reader
Applies: [C0+]
Keywords: MUST
Motivated-by: allegro's documentation-standards proposal, 2026-10-16 — a census of fifty documents in which "clear" had no test because no document named its reader; the communication-pipeline pilot, chunks 1 to 3, whose reader catalog gave its paraphraser and reviewer the reader to render and judge for
Cites: [style guide](../style.md) (Reader statement; Readers); [W-008](working-agreement.md#w-008--reports-map-their-deliverables) (reports map their deliverables); [Reader catalog](../vocabulary.md#def-reader-catalog)
Protects: sound abstraction — a document written for a named reader can be judged against that reader

**Statement**: A document under `docs/` MUST open with a
[reader statement](../vocabulary.md#def-reader-statement): a
`Reader:` line or a *Reader* section before the first section
heading, saying who the document is for and what that reader is
assumed to know, with a link to where that knowledge is defined. The
reader MUST be named from the [reader catalog](../style.md#readers)
by identifier, or described in one sentence when no catalog entry
fits. A text addressed to RD-1, RD-2 or RD-3 (the human owner or a
delegating agent) is a report under W-008, not a document, and is
scoped by W-008 instead.

**Rationale**: Every other prose duty is relative to a reader. Without
a named reader, "readable" has no test. With one, the catalog's
readability test is the test. The catalog is small on purpose. An
entry is added only when a real text had a reader none of the entries
describes. That text is cited in the entry. Existing documents gain
their reader statement at their next edit (style guide, section
Migration).

### P-008 — Terms are defined once and linked at first use
Applies: [C0+]
Keywords: MUST
Motivated-by: allegro's documentation-standards proposal, 2026-10-16 — six abstractions defined in five documents, with the relations between them only in the maintainer's head, resolved by a two-page vocabulary; the communication-pipeline pilot's [term lifecycle](https://github.com/majodali/communication-pipeline/blob/main/docs/term-lifecycle.md) (owner rulings of 2026-10-25 on handling by definition site) — 146 first-use links written by a linker across 26 documents
Cites: [style guide](../style.md) (Terms are defined once); [P-004](#p-004--citations-carry-names) (citations carry names); [W-008](working-agreement.md#w-008--reports-map-their-deliverables) (terms introduced); [Definition site](../vocabulary.md#def-definition-site)
Protects: sound abstraction — one definition per term; provenance — an unratified term is surfaced, never silently adopted

**Statement**: A term with a project-specific meaning MUST have one
[definition site](../vocabulary.md#def-definition-site): a vocabulary
row, or the heading of the document or section that defines it,
carrying an anchor of the form `<a id="def-<slug>"></a>`. A document
that uses the term MUST be its definition site or link the site at
the term's first use in the unit. The unit is the whole text for a
report (a text addressed to RD-1, RD-2 or RD-3) and the section for a
document under `docs/` (RD-4, RD-5). After that first use the term is
written bare. For RD-5, the external reader of the
[reader catalog](../style.md#readers), the link is replaced by an
inline gloss. A term with no definition site MUST be defined in one
sentence at its first use and listed under *terms introduced*
(W-008). Ratification by the human owner adds the term's vocabulary
row, which becomes its definition site. A struck term is removed from
the deliverable. A term used in more than one sense across a
project's documents MUST be listed in the vocabulary with the sense
to prefer in each use.

**Rationale**: A term defined in two places drifts into two meanings.
A term defined nowhere is a concept only its author holds. One site
per term keeps the abstraction sound. Linking the site at first use
lets a reader who arrives mid-document reach the definition in one
step. Handling follows the definition site, not frequency: a term
used often is one that reached a vocabulary early. A report is read
once and linearly, so its unit is the whole text. A document is read
by lookup, so its unit is the section (P-001, documents are
structured for reference).
