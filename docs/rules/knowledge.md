# K — Knowledge & memory

Seed extraction v0.1 — see the [rule corpus organization and import
notes](README.md).

### K-001 — Project documentation is the sole authority
Applies: [C1+]
Keywords: MUST, MUST NOT
Motivated-by: [proposal A0](../practices.md); adopted after the founding sessions established that agent-operational files had absorbed authoritative content in [allegro](https://github.com/majodali/allegro)
Cites: —

Project documentation under `docs/` MUST be the single authoritative
record of the project. Content under `.claude/` and the Agent bootstrap
(`CLAUDE.md`) MUST NOT be authoritative: they may cache or point to
project documentation, never substitute for it, and no human is assumed
to read them. Work above C0 MUST be plannable, reviewable, and resumable
from project documentation alone; anything load-bearing found outside
`docs/` is in the wrong place and MUST be moved there.

### K-002 — The Agent bootstrap is a pointer, not a record
Applies: [C1+]
Keywords: MUST, MUST NOT, SHOULD
Motivated-by: [proposal A1](../practices.md); the contrast between [in-real-life's](https://github.com/majodali/in-real-life) 144-line index and allegro's 618-line monolith
Cites: —

The Agent bootstrap MUST contain the Binding block referencing the
project's Classification, and MUST NOT contain project knowledge absent
from `docs/`. It SHOULD stay under ~200 lines: what the project is, how
to build/run/test, architecture at a glance, conventions, and pointers.
A reader who ignores it entirely MUST miss nothing authoritative
([K-001](#k-001--project-documentation-is-the-sole-authority)).

### K-003 — The Backlog is the single source of progress truth
Applies: [C1+]
Keywords: MUST
Motivated-by: [proposal A2](../practices.md); convergent independent practice in [allegro BACKLOG.md](https://github.com/majodali/allegro) and [in-real-life docs/backlog.md](https://github.com/majodali/in-real-life)
Cites: —

Every project MUST keep a Backlog: one dependency-ordered Register of
completed and upcoming work. Checked entries MUST be rewritten to
describe what actually shipped, so the completed section doubles as the
implementation map. Where the project declares a Workflow, entries MUST
carry current stage designations (Article 4 declaration accuracy). The
Backlog is the referent for "what is done and what is next"; no other
document may claim that role.

**Rationale**: the stage-designation clause deliberately mirrors
Article 4's declaration-accuracy duty — a mirror, not a duplication
(review round 1 adjudication, 2026-08-30).

### K-004 — Decisions live in a numbered register
Applies: [C2+]
Keywords: MUST
Motivated-by: [proposal A3](../practices.md); [in-real-life docs/decisions.md](https://github.com/majodali/in-real-life) (D1–D59 at extraction time)
Cites: [MADR](https://adr.github.io/madr/) (status and supersession fields)

C2+ projects MUST keep a Decision register: numbered entries, one line
each, carrying a status (`accepted` · `superseded by D<n>, because …` ·
`deprecated`) and a link to the design note holding the reasoning.
Decisions are revisable; revision happens by superseding entry, never by
silent edit.

### K-005 — Companion registers when pressure appears, never before
Applies: [C2+]
Keywords: SHOULD, MUST NOT
Motivated-by: [proposal A4](../practices.md); [in-real-life](https://github.com/majodali/in-real-life) open-risks/radar/hypotheses trio
Cites: —

C2+ projects SHOULD adopt Risk, Radar, and Hypothesis registers when the
corresponding pressure appears — known gaps, tracked-but-undesigned
workstreams, embedded analyses that are really testable bets. Empty
ceremony MUST NOT be created ahead of need. Hypothesis entries SHOULD
carry an explicit validation trigger: what observed signal, at what
threshold, revisits them.

### K-006 — One design note per designed area
Applies: [C2+]
Keywords: MUST
Motivated-by: [proposal A5](../practices.md); in-real-life `docs/*.md` design notes; allegro design memos (relocated per [K-001](#k-001--project-documentation-is-the-sole-authority))
Cites: —

Each designed area MUST have a design note in `docs/` holding the
reasoning that register entries point to. Traceability links (Article
10) run requirement → decision → plan → implementation → verification
through these notes.

### K-007 — Plans are outcome-named, statused, and ruthlessly current
Applies: [C2+]
Keywords: MUST
Motivated-by: [proposal A7](../practices.md); the owner's plan-hygiene ruling in the founding sessions; allegro `.claude/plans/` (relocating to `docs/plans/` per [K-001](#k-001--project-documentation-is-the-sole-authority))
Cites: [Oxide RFDs](https://rfd.shared.oxide.computer/) (statused design documents)

Plan documents MUST live in `docs/plans/`, named strictly for the
feature or outcome under development, each carrying a Status line with
only these transitions: `draft → active → (superseded by X, because Y |
closed → Backlog entry)`. As details or ordering change, the plan MUST
be updated; obsolete content MUST be deleted or marked obsolete with the
driving factor or decision and a pointer to what superseded it. A
completed plan MUST be closed out explicitly. Anything unmarked in a
plan is a live claim of current intent — readers and reviewing agents
may rely on that invariant.

### K-008 — Non-developer documentation
Applies: [C2+]
Keywords: SHOULD
Motivated-by: [proposal A8](../practices.md); allegro's lapsed literate specification pages; the owner's stakeholder-readability requirement in the founding sessions
Cites: [Diátaxis](https://diataxis.fr/) (documentation modes); [Gauge](https://gauge.org/) (markdown specification-by-example)

C2+ projects SHOULD maintain non-developer documentation in one or both
forms: (a) literate specification-by-example — prose with embedded
executable behavioral examples, so the spec is simultaneously readable
and verified; (b) hosted views of the project's registers with
supporting explanation. Anyone following the project should have a
current, honest window into it without reading commits.

### K-009 — Current hosted register views at C3
Applies: [C3]
Keywords: MUST
Motivated-by: [proposal A8](../practices.md); the pre-launch readability gap identified for [in-real-life](https://github.com/majodali/in-real-life)
Cites: [Diátaxis](https://diataxis.fr/) (reference mode)

C3 projects MUST publish hosted views of at least the Decision and Risk
registers, kept current, presented as latest snapshots only unless
historical detail demonstrably earns its keep.

### K-010 — Superseded content is never silently readable
Applies: [C0+]
Keywords: MUST
Motivated-by: owner-raised 2026-08-30 — decisions whose pre-decision content survived unmarked, misleading later sessions into contradictory application and persistence of the superseded state in new work
Cites: [style guide](../style.md) (Supersession markers); [W-003](working-agreement.md#w-003--documentation-moves-in-the-same-commit-as-the-work) (the same-commit principle this rule extends)

**Statement**: A deliverable that records a decision superseding
existing content MUST either rework all affected content in the same
deliverable, or record the known affected locations in the decision's
entry and place a supersession marker (style-guide format) at each. A
marker still standing at the next review round is an audit finding.
Registers kept as history are exempt entry-by-entry when their header
labels them historical.

**Rationale**: A backlog entry warns in the backlog; the reader is in
the document. The methodology's own version pin shows the working
shape — lag is legal only when declared at the point of reading.

### K-011 — Found contradictions are marked, not routed around
Applies: [C0+]
Keywords: MUST
Motivated-by: owner-raised 2026-08-30 — the affected-locations list in a decision entry is what the decision author could see; later sessions keep finding contradictions the author missed, and routing around them silently preserves the pre-decision state
Cites: [K-010](#k-010--superseded-content-is-never-silently-readable); [style guide](../style.md) (Supersession markers)

**Statement**: A session that finds content contradicting a recorded
decision MUST, within its own deliverable, fix the content or mark it
with a supersession marker and add the location to the decision's
entry. Working around unmarked stale content without marking it is
non-compliance.

**Rationale**: K-010 (superseded content is never silently readable)
binds what the decision author knew; this rule binds what later
readers discover. Together they close the gap that lets a superseded
state persist in new work.
