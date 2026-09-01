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
from per-chunk to per-sequence, and is not removed.

An agent running a sequence MUST stop, summarize, and wait when any of
these occurs:

- a check fails — the project's gate, whatever it is;
- the scope changes — the work diverges from the agreed chunk list;
- a chunk turns out to need a decision that is the human's to make.

A chunk needing a decision is a stop, not a judgment call. The landing
duties for each chunk are unchanged; only the wait between them is
removed.

**Rationale**: where "larger arcs" begins is deliberately undefined —
gating is owner judgment, not a measurable threshold; a definition
waits for a real dispute to evidence it (review round 1 adjudication,
2026-08-30). The sequence mode is likewise offered, never owed: a human
who wants the per-chunk gate keeps it by not pre-ratifying, and work
whose shape is uncertain should not be pre-ratified at all.

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
report addressed to the human owner (the principal audience) MUST
separate restatement from novelty and close with the asks: name the
parts encoding decisions already made in the conversation, name the
new parts with a pointer into the deliverable and what to review
there, and end with an explicit list of decisions and actions
requested of the reader — or state that there are none. It MUST also
lead with the outcome or the decision needed, not with the process
that produced it, and order its sections by what the reader must
decide, not by the order the writer discovered them. A report
addressed to a delegating agent (the agent audience) MUST state its
status, map its deliverable, and close with the asks or state there
are none, and MAY omit the restatement-versus-novelty split. Any
substantive report SHOULD follow the audience-appropriate structure
where it fits, with no empty ceremony. The P- rules bind reports as
their purpose admits.

**Rationale**: A summary that requires reading its document defeats
its purpose. The report is the reader's index into the deliverable;
the asks are why the report exists. Structure and order are separate
duties: a report can hold every required part and still open with its
verification process and bury the finding in its last paragraph,
which is the failure the ordering sentence above closes. Scoping by
artifact excluded the reports that most need the discipline — a
decision, a finding, a refusal, none of which necessarily attaches a
document. Scoping by "chat" assumed a human reader when most reports
in a delegated loop are agent-addressed. The
restatement-versus-novelty split exists to save a human reader's time
against a document they have not read; an agent-addressed report's
reader is the one who dispatched the work and already holds its
context, so the split costs that reader nothing it needed and this
rule no longer asks for it there.
