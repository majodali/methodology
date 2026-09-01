# W — Working agreement

Seed extraction v0.1 — see the [rule corpus organization and import
notes](README.md).

### W-001 — Two delivery modes, human-gated
Applies: [C1+]
Keywords: MUST, MUST NOT
Motivated-by: [proposal B1](../practices.md); allegro `.claude/memory/feedback_phase_delivery.md`, the practice's origin; the sequence mode from allegro's parallel-lane experiment, 2026-08 to 2026-09
Cites: —

For current work, agents MUST stay close: deliver a tight increment,
summarize, stop. Approval of delivered work MUST NOT be treated as
authorization to continue — "great work" without "next" means discuss.
For larger arcs, agents MUST plan first: write the plan document
([K-007](knowledge.md#k-007--plans-are-outcome-named-statused-and-ruthlessly-current)),
let the human set chunk boundaries, obtain explicit go-ahead before the
first chunk, and gate every chunk on summary and human review or, where
the human has approved a chunk sequence in advance, on the sequence's
stop conditions below.

**The pre-ratified sequence**. A human MAY approve a chunk **sequence**
once, at the start of an arc, instead of gating each chunk. The agent
then lands the chunks in order without stopping between them. The
approval is still explicit and still precedes the first chunk; it moves
from per-chunk to per-sequence, and is not removed. Only the human
owner pre-ratifies: a delegating agent MUST NOT pre-ratify a sequence
it dispatches unless the human has already ratified that sequence.
Delegation carries an approval; it never creates one.

An agent running a sequence MUST stop, summarize, and wait when any of
these occurs:

- a check fails — the project's gate, whatever it is;
- the scope changes — the work diverges from the agreed chunk list;
- a chunk turns out to need a decision that is the human's to make;
- a chunk's landing summary carries asks — anything requested of the
  human, whether a decision or an action.

A chunk needing a decision is a stop, not a judgment call. The landing
duties for each chunk are unchanged — each chunk is still summarized
as it lands ([W-008](#w-008--reports-map-their-deliverables)); only
the wait between chunks that ask nothing is removed. Asks are never
rolled up across chunks, and a pre-ratification MUST NOT purport to
waive the asks stop.

**Rationale**: where "larger arcs" begins is deliberately undefined —
gating is owner judgment, not a measurable threshold; a definition
waits for a real dispute to evidence it (review round 1 adjudication,
2026-08-30). The sequence mode is likewise offered, never owed: a
human who wants the per-chunk gate keeps it by not pre-ratifying, and
work whose shape is uncertain should not be pre-ratified at all.
Reserving pre-ratification to the human keeps the mode from
compounding through a delegation chain, where each agent approving the
next would leave no human decision anywhere in the arc.

Summaries survive the mode because they make the stop conditions
auditable afterwards; a sequence that lands silently cannot be checked
against the conditions that bounded it. Asks always gate for a
stronger reason. Pre-ratifying presumes the questions an arc will
raise, and what depends on their answers, are known when the sequence
is approved. They are not. An ask arriving mid-sequence has undeclared
dependents, so continuing past it builds later chunks on an unanswered
question, trading a bounded wait for unbounded rework. A formal
project model carrying questions and their dependencies as first-class
elements could bound that risk and make rolling up worth revisiting;
prose cannot (owner ruling, 2026-09-01).

### W-002 — Existing tests are signals, not obstacles
Applies: [C0+]
Keywords: MAY, MUST NOT
Motivated-by: [proposal B2](../practices.md); allegro `.claude/memory/feedback_test_modification.md`; discharges the Article 7 placeholder
Cites: —

Agents MAY add tests and assertions freely. Existing test conditions —
including expected-output annotations and structural setup — MUST NOT be
removed, weakened, or altered without prior discussion with the human
owner: a failing test is a signal, possibly of a prior misunderstanding,
and silently "fixing" it discards the signal. Root cause MUST be
investigated before the test file is touched.

### W-003 — Documentation moves in the same commit as the work
Applies: [C1+]
Keywords: MUST
Motivated-by: [proposal A2/B3](../practices.md); convergent same-commit practice in allegro and in-real-life
Cites: —

Every commit that changes project state MUST update the affected
documentation — Backlog, registers, plans, bootstrap — in that same
commit, never after. New scope discovered mid-slice MUST be recorded in
the Backlog rather than silently done.

### W-004 — Everything is provisional until reviewed against reality
Applies: [C2+]
Keywords: SHOULD
Motivated-by: [proposal B4](../practices.md); allegro's corpus-driven review-and-redo; in-real-life's revisable decisions and hypothesis register
Cites: —

Features and designs SHOULD be treated as provisional until reviewed
against real use — a corpus, user research, production behavior. Ship
the version that maximizes learning, build escape hatches, and resist
premature final-form commitments. This rule is the portfolio-level
generalization of allegro's review-and-redo and in-real-life's
hypothesis discipline.

### W-005 — Root causes, or tracked risks — never unowned known issues
Applies: [C1+]
Keywords: MUST NOT
Motivated-by: [proposal B5](../practices.md); allegro `.claude/memory/feedback_review_and_redo.md`
Cites: —

Known issues MUST NOT be accepted unless truly known, isolated, and
carrying a planned remediation tracked in the Risk register (or the
Backlog at C1). Symptomatic fixes without root-cause investigation are a
form of unowned known issue.

### W-006 — Names follow outcomes; branches are single-use
Applies: [C1+]
Keywords: MUST, MUST NOT
Motivated-by: [proposal B6](../practices.md); the owner's naming ruling in the founding sessions, retiring themed plan labels invented by past agent sessions
Cites: —

Plan documents and branches MUST be named strictly for the feature or
outcome under development — descriptive, boring, greppable. Branches
MUST be single-use: one branch per deliverable, deleted after merge,
never reused. Themed or evocative naming schemes MUST NOT be introduced
or extended by agents unprompted; where one exists it is locked as
found.

### W-007 — Every project has a README that says what it is
Applies: [C0+]
Keywords: MUST
Motivated-by: [Constitution Article 7](../constitution.md#article-7--the-c0-baseline-custom-definitions-and-the-sandbox) C0 baseline; the template repo's orientation-first README
Cites: —

Every project MUST have a README. At C0 it MUST state the question being
explored — the one obligation exploration carries besides
[W-002](#w-002--existing-tests-are-signals-not-obstacles) and secret
hygiene. At C1+ it orients: what the project is, for whom, and where the
documentation lives.

### W-008 — Reports map their deliverables
Applies: [C0+]
Keywords: MUST, SHOULD
Motivated-by: owner-raised 2026-08-30 — delivery summaries citing the delivered document by naked section number, and asks buried in prose so the owner parses both summary and document to learn what is requested; extended by project-orchestrator, 2026-09-01 — a delegated loop's reports are mostly agent-addressed and mostly attach no artifact, both outside the rule's original scoping
Cites: [style guide](../style.md) (Reports and summaries); [P-004](prose.md#p-004--citations-carry-names); [Delegation and Report audience](../vocabulary.md#defined-terms) (the audience the Statement below scopes by)

**Statement**: A report's duties scope by its report audience. A
report addressed to the human owner (the principal audience) MUST lead
with the outcome or the decision needed, never with the process that
produced it, and MUST carry three parts in this order: the **asks**
(the decisions and actions requested of the reader), **what is already
covered** (the parts of the deliverable encoding decisions the
conversation already settled), and **what changed** (the parts that
are new, each with a named pointer into the deliverable and what to
review there). An empty part MUST be stated, never omitted — "No
asks", "We already covered everything in the document", "The content
is all new". A report addressed to a delegating agent (the agent
audience) MUST state its status, map its deliverable, and carry the
asks part, and MAY omit the other two. Any substantive report SHOULD
follow the audience-appropriate structure where it fits, without
padding a stated-empty part into a section. The P- rules bind reports
as their purpose admits.

**Required bootstrap text**: A project that has an Agent bootstrap
MUST carry the block below in it, verbatim, under its own heading.
The block is a cache: this rule, the P- rules, and the
[style guide](../style.md) remain the authority
([K-001](knowledge.md#k-001--project-documentation-is-the-sole-authority)
— documentation under `docs/` is the sole authority;
[K-002](knowledge.md#k-002--the-agent-bootstrap-is-a-pointer-not-a-record)
permits the bootstrap to cache what it does not own). Audits compare
the bootstrap's copy against this block and report any difference as
drift. Amend the text here; never edit the copy in place.

```markdown
## Reporting and writing — cached from W-008; do not edit here

Reports to the human owner carry three parts, in this order:

1. **Asks** — the decisions and actions requested of the reader.
2. **What is already covered** — the parts of the deliverable that
   encode decisions the conversation already settled.
3. **What changed** — the parts that are new, each with a named
   pointer into the deliverable and what to review there.

State an empty part; never drop it: "No asks", "We already covered
everything in the document", "The content is all new".

Lead with the outcome or the decision needed, never with the process
that produced it. Write short, direct sentences, one idea each. Cut
clauses that add tone but not content: dramatic accumulation,
aphorism, suspense. Name every identifier you cite.

Authority: majodali/methodology W-008 (reports map their
deliverables), the P- rules, and its style guide. This block is a
cache — amend it upstream, never here.
```

**Rationale**: A summary that requires reading its document defeats
its purpose. The report is the reader's index into the deliverable;
the asks are why the report exists, so they lead. A report can hold
every required part and still open with its verification process and
bury what the reader owes in its last paragraph, which is the failure
the fixed order closes. The bootstrap cache exists because conformance
decays with distance: guidance read once at a session's start competes
with everything the session does afterwards, and the harness re-injects
the bootstrap where it does not re-read the corpus. Caching the rule
where it is re-read keeps it in force late in a session, when the drift
appears (owner observation across high-traffic sessions, 2026-09-01). Stating an empty part is a declaration, not
ceremony: "No asks" tells the reader in three words that they owe
nothing, where silence leaves them searching for what they missed
(the omission-as-declaration principle of Article 4, applied to
reports). Scoping by
artifact excluded the reports that most need the discipline — a
decision, a finding, a refusal, none of which necessarily attaches a
document. Scoping by "chat" assumed a human reader when most reports
in a delegated loop are agent-addressed. The
restatement-versus-novelty split exists to save a human reader's time
against a document they have not read; an agent-addressed report's
reader is the one who dispatched the work and already holds its
context, so the split costs that reader nothing it needed and this
rule no longer asks for it there.
