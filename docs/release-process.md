# The amendment & release process

How a change to the methodology travels from proposal to per-project
adoption. This is a Methodology-level (Level 2) document under
[Article 8](constitution.md#article-8--amendments-versions-and-migration):
the Constitution defines that amendments, versions, and migration exist
and who decides; this document defines the pipeline mechanics, and is
itself amendable through the process it describes. Normative keywords
per BCP 14 (constitution preamble).

Cites: [Semantic Versioning](https://semver.org/) (version semantics);
[Keep a Changelog](https://keepachangelog.com/) (the
[Release register](releases.md)'s shape).

## Lifecycle

`proposed → adjudicated → accepted (candidate) → released → adopted
(per project)`, with `rejected` as the exit at adjudication.

### 1 — Proposed

A proposal is a PR against `main` (Article 8). It MUST contain, in one
diff:

- the change itself;
- a link to its **evidencing instance** — the project and artifact that
  needed it (Articles 6 and 8);
- its entry in the [Release register](releases.md)'s *Unreleased*
  section
  ([M-004](rules/mirrors.md#m-004--amendment-prs-carry-their-release-register-entry)),
  carrying: amendment title and PR link · suggested by (evidencing
  instance) · **impact assessment** — every Portfolio project affected,
  each marked *accommodated* / *deviation expected* / *not affected* ·
  **migration note** — what an adopting project must do (`none` is a
  valid value and MUST be stated explicitly, never left blank).

A proposal missing any of these is not adjudicable; reviewers return it
to the proposer rather than judging it.

### 2 — Adjudicated

Adjudication happens at a scheduled **review round** or at an **interim
adjudication** (Article 8; vocabulary-defined). The per-proposal duties
are identical either way:

- the traceability review (Article 9,
  [M-003](rules/mirrors.md#m-003--amendment-prs-receive-traceability-review)):
  follow the evidencing-instance link and verify the change against the
  current standard and all open proposals;
- the accommodation question first: *"how do we make this amendment
  work for all impacted projects?"* — a deviation is the fallback,
  never the default (Article 8);
- verify the Release-register entry is complete and honest.

An interim adjudication covers only its named proposals and none of the
review round's corpus-level duties (census, semantic audit,
anti-languish flagging — Article 9). Scheduled review rounds
re-examine the interim decisions taken since the last round.

### 3 — Accepted: the release candidate

Acceptance is the human owner's merge of the proposal PR; rejection is
closure unmerged, and the register entry dies with the PR. **`main`
between tags is the release candidate**: the accumulation of accepted,
unreleased amendments, described exactly by the Unreleased section.
There are no release-candidate tags — a deliberate omission while the
portfolio is solo-owned. Nothing MAY pin or adopt unreleased `main`:
compliance targets reference releases only.

### 4 — Released

The owner cuts a release at a moment of their choosing:

1. A **release PR** retitles the Unreleased section to `vX.Y.Z — date`
   (leaving a fresh empty Unreleased section above it). The retitled
   section *is* the release's migration notes — nothing further is
   written at release time.
2. After merging it, the owner creates the annotated tag `vX.Y.Z` —
   the release ceremony (tags are owner-created, on `main`, after
   review; never pre-merge, never by an agent — the methodology's
   [process records](classification.md)).

### 5 — Adopted: per project, at its own pace

A release binds no pinned project until it migrates (Article 8). Each
project raises a **migration PR** that updates its Classification pin
and, following the release's migration notes, adopts each changed rule
or records a deviation with rationale. Version lag stays visible rather
than implicit — `mtool status` reports it per project, and the census
refreshes Portfolio summaries — and lag MUST remain temporary, not a
home (Article 8). During early adoption, frequent small releases and
prompt migrations are the expected rhythm (informative).

## Version semantics

- **Minor** (`x.Y.0`) — any release containing normative change: one
  amendment or a batch.
- **Patch** (`x.y.Z`) — editorial changes only. An **editorial change**
  (vocabulary-defined) has zero normative effect — a typo, broken
  link, formatting fix, or wording clarification that changes no
  obligation. Editorial changes MAY merge without the amendment
  process, at the owner's discretion, and are recorded as one-line
  notes in Unreleased (no impact assessment or migration note). They
  normally ship with the next release of any size; a patch release
  exists for when an editorial fix must become adoptable on its own.
  Whether a change is editorial is the owner's call; when in doubt it
  is an amendment.
- **Major** (`X.0.0`) — constitutional restructuring or a change that
  breaks the migration model itself; expected to be rare.
