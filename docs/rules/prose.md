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
