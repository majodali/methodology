# The Methodology Vocabulary

*Each term will carry: definition, allowed relationships, lifecycle
(designations it may hold), and the rules that govern it. Listed here are
the categories and initial members working sessions have already needed;
definitions are written term-by-term as rules require them
([Constitution Article 6](constitution.md#article-6--inclusion-every-rule-earns-its-keep)).*

Split at bootstrap from *The Methodology Constitution & Vocabulary — Draft
v0.7* (its Part II); the draft's changelog is preserved as pre-1.0 history
in [constitution.md](constitution.md#draft-history-pre-10).

## Classification scales and derived conditions

- **C-tier** — criticality: `C0` exploration · `C1` personal tool ·
  `C2` serious project, pre-users · `C3` production with real users
  (definitions: [proposal §1.1](practices.md)).
- **S-level** — sensitivity: `S0` public code only · `S1` infrastructure
  secrets · `S2` personal data/PII ([proposal §1.2](practices.md)).
- **Type** — `web-app` · `backend-service` · `component/library` ·
  `language/tool platform` · `exploration` · `ops` · `docs-corpus` (a
  documentation or standards corpus) · `template` (a project whose
  shipped content instantiates *derived* projects — its distinctive
  burden is that the scaffold it ships must keep derivatives
  compliant, [Q-001](rules/quality.md#q-001--template-scaffolds-stay-compliant))
  · `methodology-corpus` (**reserved
  singleton**: the methodology repo itself; exactly one project MAY hold
  it, per [Article 9](constitution.md#article-9--audits) — the tag by
  which rules denote that repo). Type and
  C-tier are
  orthogonal: type `exploration` names a project's nature and may persist
  at C1+ (a maintained research harness); C0 is a criticality tier any
  type may hold. The informal gloss of C0 as "exploration" is
  non-normative.
- **Target** — `none/local` · `static site` · `serverless-aws` ·
  `package registry` · `home infrastructure`.
- **Derived conditions** (functions of declared Classification fields and
  of designations the Classification references, usable in applicability
  tags): `deployable` := target ≠ `none/local`; `deployed` :=
  `deployable` **∧** at least one Backlog entry is at a stage the
  project's **Workflow** (defined below) designates *live* — so
  `deployed` entails `deployable` by definition, and with no Workflow
  declared `deployed` is false (omission-as-declaration,
  [Article 4](constitution.md#article-4--applicability-then-precedence),
  makes falsely relying on that non-compliant). Precedence weight among
  derived conditions (Article 4 stage 2.3(c)), most specific first — an
  order the containment now genuinely establishes: `deployed`, then
  `deployable`; each new condition is inserted into this order at
  definition time.

## Defined terms

- **Compliance target** — the methodology version a project's
  Classification pins, or, for an unpinned C0 project, the latest
  version (which moves with each bump — the one place amendments apply
  without a migration step,
  [Article 8](constitution.md#article-8--amendments-versions-and-migration));
  the standard all audits of that
  project run against (Articles 8–9).
- **Review horizon** — the number of review rounds within which a rule
  must have been exercised by some project to escape anti-languish
  flagging; default two, measured from the rule's **first adoption** —
  the first review round at which the rule is **in play** for some
  project (its compliance target includes the rule *and* the project
  satisfies its applicability conditions) — so neither slow migration
  cycles nor the always-latest projects start clocks spuriously. A rule
  whose clock has not started within the review horizon of its creation
  is itself flagged as **never-in-play** — the ultimate languisher
  ([Article 6](constitution.md#article-6--inclusion-every-rule-earns-its-keep)).
- **Exercise** — a rule is exercised when it observably constrained or
  shaped work: evidence includes an artifact whose form or existence the
  rule required, a deviation recorded against it, an audit finding or
  review comment citing it, or a tooling enforcement event. Being in
  play is not exercise.
- **Project family** — a named group of projects forming one product,
  estate, or discipline, declared through the Classification's
  optional **Family** field: family name, role (`lead` | `member`),
  and, for members, the lead's location. Exactly one member is the
  **lead**. The lead is the family's documentation home — shared
  registers, decisions, and construct definitions live with the lead
  (or the member that publishes them), and other members reference
  rather than duplicate them (*family cohesion*); changes to
  family-shared constructs route through the defining member's change
  process, and family-defined document types are adopted by citation
  (Article 7). Family membership never merges Classifications: every
  member declares, migrates, and is audited alone — S-levels and
  tiers stay orthogonal. **The Family field is outside the Article 4
  decidability basis**: no rule applicability condition may read it,
  and admitting it would be a constitutional change (Article 4).
  Promotion of any member SHOULD review the family (the
  [D6](practices.md) anti-languish review, generalized). The census
  reconciles family declarations for symmetry (a claimed membership
  the lead's family does not reciprocate is drift), and the Portfolio
  register groups by family.
- **Portfolio register** — the Register in the methodology repo
  enumerating all majodali projects (name, location, classification
  summary). The summary is an **informative cache** — each project's own
  Classification remains authoritative — and the census pass refreshes
  stale summaries. The corpus-level audit's sweep set and the census
  pass's baseline ([Article 9](constitution.md#article-9--audits)).
  Completeness is a duty of the methodology
  repo (`[type: methodology-corpus]`), not of the enumerated projects.
  Current instance: [registers/portfolio.md](registers/portfolio.md).
- **Interim adjudication** — an adjudication of named amendment
  proposals that the human owner MAY convene at any time between review
  rounds ([Article 8](constitution.md#article-8--amendments-versions-and-migration)).
  It carries every per-proposal duty — the traceability review, the
  impact assessment and accommodation question, the Release-register
  entry check — and none of the review round's corpus-level audit
  duties ([Article 9](constitution.md#article-9--audits)); every
  scheduled review round re-examines the interim decisions taken since
  the last round. Defined by the
  [release process](release-process.md).
- **Release** — a version of the methodology made adoptable by the
  owner's annotated tag `vX.Y.Z` on `main`; its content is the set of
  accepted amendments recorded in the Release register's section for
  that version. Compliance targets reference releases only — unreleased
  `main` is never a compliance target
  ([release process](release-process.md)).
- **Release register** — the Register (methodology repo only,
  [releases.md](releases.md)) recording, per amendment: provenance
  (suggested by / evidencing instance), impact assessment, and
  migration note — Unreleased section for the current release
  candidate, then one section per release. The durable record the
  amendment lifecycle writes through
  ([M-004](rules/mirrors.md#m-004--amendment-prs-carry-their-release-register-entry));
  shape cites [Keep a Changelog](https://keepachangelog.com/).
- **Audit delivery** — the appending of a new Audit-log Entry to an
  audited project, due exactly when an audit run's **finding
  fingerprint** — the sorted set of `(rule ID, severity, file)` over
  violations and warnings — differs from the project's newest
  same-kind entry, or no such entry exists. Always by PR, never a
  direct push; the first delivery creates the project's Audit log.
  Defined by the [audit process](audit-process.md).
- **Editorial change** — a change with zero normative effect (typo,
  broken link, formatting, wording clarification changing no
  obligation). It MAY merge without the amendment process at the
  owner's discretion and is recorded as a one-line Unreleased note;
  patch releases contain editorial changes only
  ([release process](release-process.md)). When in doubt, it is an
  amendment.
- **Existence rules / content rules** — existence rules govern that
  material is present, located, designated, and linked as required;
  content rules govern its internal form and substance. Sandbox material
  is subject to the former only
  ([Article 7](constitution.md#article-7--the-c0-baseline-custom-definitions-and-the-sandbox)).
- **Workflow** — a per-project ordered set of stages through which work
  items pass (e.g. dev → test → release → production), declared in the
  Classification, with the stages that constitute *live* operation
  explicitly designated. The Workflow is the stage set; the **Backlog**
  holds the items, each entry carrying its current stage as a
  designation — so workflow state (which features are at which stage) is
  readable from the Backlog, and derived conditions like `deployed` are
  decidable from Classification + Backlog designations
  ([Article 4](constitution.md#article-4--applicability-then-precedence)). The
  specific stage set is defined per project; the methodology standardizes
  only that one exists, where it is declared, and how stages are
  referenced. Stage names SHOULD NOT collide with vocabulary-defined
  derived conditions.

## Artifact types

- **Document** — a markdown file of a defined type. Canonical home is
  `docs/`; two root-level Document types exist outside it:
  - **Readme** (`README.md`) — orientation; at C0, the sole required
    Document.
  - **Agent bootstrap** (`CLAUDE.md`) — non-authoritative by A0; its only
    normative content is the Binding block.

  Subtypes under `docs/`:
  - **Classification** (`docs/classification.md`) — the binding
    declaration. Mandatory fields: **C-tier**, and at C1+ the **pinned
    methodology version** (compliance target). Optional fields, each with
    a defined omission default (this definition is the **sole
    authoritative location** for omission defaults;
    [Article 4](constitution.md#article-4--applicability-then-precedence)
    references
    it): S-level (`S0`), type (`exploration`), target (`none/local`),
    Workflow definition (absent ⇒ `deployed` is false), Deviation
    register and Custom definitions section (absent ⇒ empty),
    **Family** (absent ⇒ none — the project stands alone; see *Project
    family*), and — at
    C0 only, where the pin is optional — pinned version (absent ⇒ the
    **latest** version: C0 projects track the current `[C0+]` baseline).
    A tier-line-only Classification is therefore legal at C0; C1+ adds
    only the version pin. Classification **field value sets are extended
    by amendment only, never per-project** — Article 7's custom
    definitions cover types of project material, not field values.
  - **Register** — append-oriented Document of uniformly-shaped entries:
    *Backlog*, *Decision register*, *Risk register*, *Radar*, *Hypothesis
    register*, *Event register* (house style: "register"; ES/CQRS sources
    often say "registry" — [AsyncAPI](https://www.asyncapi.com/) et al.),
    the *Audit log* (`docs/audits.md` — one Entry per audit execution,
    in the format the [audit process](audit-process.md) defines; the
    machine-readable
    source for *time of last semantic audit*, which the Article 9
    delta-ratio auto-trigger reads; entries arrive by *Audit delivery*
    on state transitions; motivated by
    [methodology-tools chunk 1](https://github.com/majodali/methodology-tools/pull/1)),
    and — in the methodology repo only — the *Portfolio register*.
    Register-shaped sections *within* a Document are **Embedded
    registers**, a Content type — the Deviation register and Custom
    definitions section within the Classification are the current
    instances.
  - **Plan** — outcome-named, statused, in `docs/plans/`.
  - **Design note** — reasoning for a designed area; target of register
    pointers.
  - **Specification** — behavior stated to be implemented against;
    includes *literate specification* (prose with embedded executable
    examples).
  - **Runbook** — operational procedure (ops profile).
  - **Custom document type** — per-project
    ([Article 7](constitution.md#article-7--the-c0-baseline-custom-definitions-and-the-sandbox));
    instances link the definition.
- **Non-document artifacts** — source, tests, workflows, built artifacts
  (including the methodology plugin), hosted views. Each appears in a
  project only as an instance of a defined type (standard or custom).

## Content types (sections within Documents)

- **Entry** — one uniformly-shaped item in a Register or Embedded
  register (e.g. *decision entry*: ID, one-line summary, status, pointer
  to reasoning).
- **Embedded register** — a register-shaped section within a Document,
  holding Entries under the same rules as a Register; current instances:
  the *Deviation register* and *Custom definitions section* of the
  Classification.
- **Requirement** — a statement of needed behavior/quality; traceability
  source.
- **Rationale** — reasoning attached to a decision/plan/rule.
- **Status line** — machine-readable designation carried by Plans and
  other lifecycled content.
- **Binding block** — the Agent bootstrap section referencing the
  Classification with strictness language.
- **Custom content type** — as per custom documents.

## Designations (lifecycle states)

`draft` · `active` · `superseded (by X, because Y)` · `closed` · `accepted`
· `deprecated` · `in-progress` (absorbing the former `provisional`) ·
`not-compliant` · **Workflow stages** (per-project names, carried by
Backlog entries)
— which types may hold which designations is defined per type; transitions
are rules.

## Relationship types

`traces-to` · `implements` · `verifies` · `informs` · `supersedes` ·
`defines / instance-of` · `deviates-from` · `motivated-by` (rules → their
instances) · `cites` (third-party source).

## Process terms

**Review round** · **Interim adjudication** (defined above) ·
**Audit** (form / semantic,
[Article 9](constitution.md#article-9--audits)) · **Amendment** ·
**Release** (defined above) ·
**Migration** ([Article 8](constitution.md#article-8--amendments-versions-and-migration))
· **Re-classification** (updating any declared
Classification field to match actual state,
[Article 4](constitution.md#article-4--applicability-then-precedence)) ·
**Promotion**
(the C-tier-raising case of Re-classification) · **Chunk gate**
· **Close-out** (plan completion) · **Standardization** (custom →
standard).

## Roles

**Human owner** · **Agent** (session, working) · **Reviewer** (human or
agent; adjudication reserved to humans) · **Auditor** (docs-auditor agent
for form audits on changed days + human semantic pass — on-request,
auto-triggered, or at every review round for the methodology repo, per
[Article 9](constitution.md#article-9--audits)).

## Practices

The named practices of the main proposal (A0–F5) become vocabulary
members, each defined by the rules that constitute it. Third-party imports
(BCP 14, MADR statuses, RFD lifecycle, Diátaxis modes, C4 levels,
Conventional Commits, Well-Architected/ASVS checklists, ES/CQRS
event-register practices) enter as vocabulary + rules with `cites`
relationships — never as tooling mandates.
