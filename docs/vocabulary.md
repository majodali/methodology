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

- <a id="def-c-tier"></a>**C-tier** — criticality: `C0` exploration · `C1` personal tool ·
  `C2` serious project, pre-users · `C3` production with real users
  (definitions: [proposal §1.1](practices.md)).
- <a id="def-s-level"></a>**S-level** — sensitivity: `S0` public code only · `S1` infrastructure
  secrets · `S2` personal data/PII ([proposal §1.2](practices.md)).
- <a id="def-type"></a>**Type** — `web-app` · `backend-service` · `component/library` ·
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
- <a id="def-target"></a>**Target** — `none/local` · `static site` · `serverless-aws` ·
  `package registry` · `home infrastructure`.
- <a id="def-derived-conditions"></a>**Derived conditions** (functions of declared Classification fields and
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

- <a id="def-compliance-target"></a>**Compliance target** — the methodology version a project's
  Classification pins, or, for an unpinned C0 project, the latest
  version (which moves with each bump — the one place amendments apply
  without a migration step,
  [Article 8](constitution.md#article-8--amendments-versions-and-migration));
  the standard all audits of that
  project run against (Articles 8–9).
- <a id="def-review-horizon"></a>**Review horizon** — the number of review rounds within which a rule
  must have been exercised by some project to escape anti-languish
  flagging; default two, measured from the rule's **first adoption** —
  the first review round at which the rule is **in play** for some
  project (its compliance target includes the rule *and* the project
  satisfies its applicability conditions) — so neither slow migration
  cycles nor the always-latest projects start clocks spuriously. A rule
  whose clock has not started within the review horizon of its creation
  is itself flagged as **never-in-play** — the ultimate languisher
  ([Article 6](constitution.md#article-6--inclusion-every-rule-earns-its-keep)).
- <a id="def-exercise"></a>**Exercise** — a rule is exercised when it observably constrained or
  shaped work: evidence includes an artifact whose form or existence the
  rule required, a deviation recorded against it, an audit finding or
  review comment citing it, or a tooling enforcement event. Being in
  play is not exercise.
- <a id="def-project-family"></a>**Project family** — a named group of projects forming one product,
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
- <a id="def-portfolio-register"></a>**Portfolio register** — the Register in the methodology repo
  enumerating all majodali projects (name, location, classification
  summary). The summary is an **informative cache** — each project's own
  Classification remains authoritative — and the census pass refreshes
  stale summaries. The corpus-level audit's sweep set and the census
  pass's baseline ([Article 9](constitution.md#article-9--audits)).
  Completeness is a duty of the methodology
  repo (`[type: methodology-corpus]`), not of the enumerated projects.
  Current instance: [registers/portfolio.md](registers/portfolio.md).
- <a id="def-interim-adjudication"></a>**Interim adjudication** — an adjudication of named amendment
  proposals that the human owner MAY convene at any time between review
  rounds ([Article 8](constitution.md#article-8--amendments-versions-and-migration)).
  It carries every per-proposal duty — the traceability review, the
  impact assessment and accommodation question, the Release-register
  entry check — and none of the review round's corpus-level audit
  duties ([Article 9](constitution.md#article-9--audits)); every
  scheduled review round re-examines the interim decisions taken since
  the last round. Defined by the
  [release process](release-process.md).
- <a id="def-release"></a>**Release** — a version of the methodology made adoptable by the
  owner's annotated tag `vX.Y.Z` on `main`; its content is the set of
  accepted amendments recorded in the Release register's section for
  that version. Compliance targets reference releases only — unreleased
  `main` is never a compliance target
  ([release process](release-process.md)).
- <a id="def-release-register"></a>**Release register** — the Register (methodology repo only,
  [releases.md](releases.md)) recording, per amendment: provenance
  (suggested by / evidencing instance), impact assessment, and
  migration note — Unreleased section for the current release
  candidate, then one section per release. The durable record the
  amendment lifecycle writes through
  ([M-004](rules/mirrors.md#m-004--amendment-prs-carry-their-release-register-entry));
  shape cites [Keep a Changelog](https://keepachangelog.com/).
- <a id="def-audit-delivery"></a>**Audit delivery** — the appending of a new Audit-log Entry to an
  audited project, due exactly when an audit run's **finding
  fingerprint** — the sorted set of `(rule ID, severity, file)` over
  violations and warnings — differs from the project's newest
  same-kind entry, or no such entry exists. Always by PR, never a
  direct push; the first delivery creates the project's Audit log.
  Defined by the [audit process](audit-process.md).
- <a id="def-editorial-change"></a>**Editorial change** — a change with zero normative effect (typo,
  broken link, formatting, wording clarification changing no
  obligation). It MAY merge without the amendment process at the
  owner's discretion and is recorded as a one-line Unreleased note;
  patch releases contain editorial changes only
  ([release process](release-process.md)). When in doubt, it is an
  amendment.
- <a id="def-existence-rules-content-rules"></a>**Existence rules / content rules** — existence rules govern that
  material is present, located, designated, and linked as required;
  content rules govern its internal form and substance. Sandbox material
  is subject to the former only
  ([Article 7](constitution.md#article-7--the-c0-baseline-custom-definitions-and-the-sandbox)).
- <a id="def-workflow"></a>**Workflow** — a per-project ordered set of stages through which work
  items pass (e.g. dev → test → release → production), declared in the
  Classification, with the stages that constitute *live* operation
  explicitly designated. The Workflow is the stage set; the **Backlog**
  holds the items, each entry carrying its current stage as a
  designation — so workflow state (which features are at which stage) is
  readable from the Backlog, and derived conditions like `deployed` are
  decidable from Classification + Backlog designations
  ([Article 4](constitution.md#article-4--applicability-then-precedence)). The
  specific stage set is defined per project; the methodology
  standardizes the declaration's required minimum format (review
  round 1 adjudication, 2026-08-30):

  `stages: <a> → <b> → <c>; live = <stage>; backlog default: checked ⇒ <s1>, unchecked ⇒ <s2>`

  — three parts: the ordered stage list, the designated live stage or
  stages, and the Backlog default rule. A Backlog entry deviating from
  the default carries an explicit `stage:` marker. The declaration MAY
  dress the parts in prose, but each MUST be present and unambiguous:
  `deployed` is derived by reading them. Declarations predating this
  format already carry the three parts in substance and reword
  editorially at their own pace; until reworded to the parseable
  form, audits note the declaration as tool-unreadable (an info
  finding, not a violation). Stage names SHOULD NOT collide with
  vocabulary-defined derived conditions.
- <a id="def-delegation"></a>**Delegation** — the relationship formed when an Agent session (the
  **delegating agent**) dispatches bounded work to another Agent
  session (the **delegated agent**) and awaits its report. The
  delegated agent reports to the delegating agent, not directly to
  the human owner, unless the delegating agent is itself the human
  owner's own direct session. Delegation nests: a delegated agent MAY
  itself act as a delegating agent to sessions it dispatches in turn.
- <a id="def-convergence"></a>**Convergence** — a project is convergent while the cost for its
  owners to understand, change and verify it grows more slowly than
  the project (owner, "Convergence and Divergence", 2026-10-22, a
  writeup not yet in this corpus).
- <a id="def-invariant"></a>**Invariant** — one of three properties a convergent project keeps
  as it grows. A rule MAY name the invariants it protects in its
  `Protects:` header, each with one clause saying how
  ([Article 5](constitution.md#article-5--rule-form), rule form). The
  three definitions below are wordings proposed 2026-10-26 from the
  owner's writeup, pending the owner's confirmation:
  - <a id="def-provenance"></a>**Provenance** — every claim a governed
    document makes can be traced to the decision, evidence or source
    that produced it.
  - <a id="def-sound-abstraction"></a>**Sound abstraction** — every
    term and structure a governed document uses has one definition and
    is used as defined.
  - <a id="def-proportional-verification"></a>**Proportional
    verification** — the effort spent checking a change grows with the
    change's footprint, the files and claims it touches, and not with
    the size of the project.
- <a id="def-reader-catalog"></a>**Reader catalog** — the set of defined readers a text may be
  written for: RD-1 to RD-5, one row each in the [style guide's
  Readers table](style.md#readers). Each row states what the reader is
  assumed to know and its **readability test**, the question a
  reviewer answers to judge a text readable for that reader. A
  document names its reader from the catalog
  ([P-007](rules/prose.md#p-007--documents-state-their-reader)).
- <a id="def-reader-statement"></a>**Reader statement** — the opening of a document that names who it
  is for and what that reader is assumed to know, with a link to where
  that knowledge is defined
  ([P-007](rules/prose.md#p-007--documents-state-their-reader)).
- <a id="def-definition-site"></a>**Definition site** — the one place a term is defined: a vocabulary
  row or the heading of the document that defines it, carrying an
  anchor `<a id="def-<slug>"></a>` that every other use links to
  ([P-008](rules/prose.md#p-008--terms-are-defined-once-and-linked-at-first-use)).
- <a id="def-terms-introduced"></a>**Terms introduced** — the fourth part of a report to the human
  owner
  ([W-008](rules/working-agreement.md#w-008--reports-map-their-deliverables)).
  It lists each term the report or its deliverable uses with a meaning
  no vocabulary defines, with one sentence of meaning each. Ratified
  2026-10-26.
- <a id="def-migration-round"></a>**Migration round** — the set of per-project migration PRs that
  follows one methodology release. Ratified 2026-10-26; first used in
  the Portfolio refresh of 2026-10-25
  ([PR #44](https://github.com/majodali/methodology/pull/44)).
- <a id="def-intermediate-representation"></a>**Intermediate representation (IR)** — the structured form a
  reasoning role writes before prose: the terms, claims, relations,
  evidence and asks of one communication. Every element carries an
  identifier. Every term, claim and cluster also carries a
  **provenance status** (decided, proposed or inferred). Specified in
  [intermediate-representation.md](intermediate-representation.md);
  required by
  [W-009](rules/working-agreement.md#w-009--the-methodology-corpus-writes-its-deliverables-ir-first).
  The roles around it:
  - <a id="def-reasoning-role"></a>**Reasoning role** — the agent role
    that does the thinking and writes its output as an IR.
  - <a id="def-paraphraser"></a>**Paraphraser** — the agent role that
    renders an IR into prose for one catalog reader, adding no claim and
    dropping none.
  - <a id="def-stranger"></a>**Stranger** — a reviewer with no access to
    the conversation that produced the text and no content
    contributions to the project. The stranger judges a text against
    its reader's readability test.
  The terms of the specification, ratified 2026-10-27:
  - <a id="def-provenance-status"></a>**Provenance status** — the tag
    ending each term, claim and cluster of an IR: decided, proposed or
    inferred.
  - <a id="def-referent"></a>**Referent** — anything a claim refers
    to: a document, a project, a rule, a person, a role, or an earlier
    claim's subject. A claim names each referent inside itself.
  - <a id="def-cluster"></a>**Cluster** — an ordered list of claim
    identifiers the paraphraser renders as one paragraph.
  - <a id="def-render-map"></a>**Render map** — one comment line in
    rendered prose listing the paragraph each claim landed in.
  - <a id="def-review-record"></a>**Review record** — the file
    `<subject>.review.md` beside an IR, holding each round's findings,
    dispositions and verdict.
  - <a id="def-round"></a>**Round** — one stranger review of an IR and
    its prose, returning findings and a verdict.
  - <a id="def-count"></a>**Count** — one review's sequence of rounds,
    ending at a readable verdict or at the limit.
  - <a id="def-limit"></a>**Limit** — ten rounds in one count.
  - <a id="def-meta-review"></a>**Meta-review** — a review, by a
    session with no part in the rounds, of a text's review record and
    the text itself, reporting whether the process needs a change. Due
    when a text's count reaches the limit or its review record shows a
    meta-review signal (the specification's Meta-review section).
  - <a id="def-footprint"></a>**Footprint** — the files or directories
    an IR's deliverable is expected to change, declared in the IR's
    Footprint header and compared with the branch's changes before
    delivery.
  - <a id="def-register-fact"></a>**Register fact** — a statement about
    the state of a [Register](#def-register) or of a row in one.
  - <a id="def-normative-text"></a>**Normative text** — a rule, a
    specification, or any text whose words bind.
  - <a id="def-meta-review-signal"></a>**Meta-review signal** — one of
    four conditions in a review record that make a text a meta-review
    subject, named in the specification's Meta-review section.
- <a id="def-planning-execution-model"></a>**Planning/execution model** — the plan model of a project plus
  the verification evidence of each node: what the web view renders
  and the source of progress truth (owner, 2026-10-28,
  [vision](vision.ir.md)).
- <a id="def-stream"></a>**Stream** — a unit of approved autonomous work bounded by scope,
  budget and accepted risks rather than by chunk gates (owner,
  2026-10-28, [vision](vision.ir.md)).
- <a id="def-specification-by-example"></a>**Specification-by-example** — a specification given as examples
  that double as tests (owner, 2026-10-28, [vision](vision.ir.md)).
- <a id="def-web-view"></a>**Web view** — the project-orchestrator-service's interface for a
  project's planning/execution model, called the plan view in service
  chunk 2 (owner, 2026-10-28, [vision](vision.ir.md)).
- <a id="def-report-audience"></a>**Report audience** — the reader a report is addressed to under
  [W-008](rules/working-agreement.md#w-008--reports-map-their-deliverables)
  (reports map their deliverables): the human owner directly (the
  **principal audience**), or a delegating agent awaiting a delegated
  agent's report before relaying its own report further (the **agent
  audience**). The audience determines which of W-008's duties a
  report carries.

## Artifact types

- <a id="def-document"></a>**Document** — a markdown file of a defined type. Canonical home is
  `docs/`; two root-level Document types exist outside it:
  - <a id="def-readme"></a>**Readme** (`README.md`) — orientation; at C0, the sole required
    Document.
  - <a id="def-agent-bootstrap"></a>**Agent bootstrap** (`CLAUDE.md`) — non-authoritative by A0; its only
    normative content is the Binding block.

  Subtypes under `docs/`:
  - <a id="def-classification"></a>**Classification** (`docs/classification.md`) — the binding
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
  - <a id="def-register"></a>**Register** — append-oriented Document of uniformly-shaped entries:
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
  - <a id="def-plan"></a>**Plan** — outcome-named, statused, in `docs/plans/`.
  - <a id="def-design-note"></a>**Design note** — reasoning for a designed area; target of register
    pointers.
  - <a id="def-specification"></a>**Specification** — behavior stated to be implemented against;
    includes *literate specification* (prose with embedded executable
    examples).
  - <a id="def-runbook"></a>**Runbook** — operational procedure (ops profile).
  - <a id="def-custom-document-type"></a>**Custom document type** — per-project
    ([Article 7](constitution.md#article-7--the-c0-baseline-custom-definitions-and-the-sandbox));
    instances link the definition.
- <a id="def-non-document-artifacts"></a>**Non-document artifacts** — source, tests, workflows, built artifacts
  (including the methodology plugin), hosted views. Each appears in a
  project only as an instance of a defined type (standard or custom).

## Content types (sections within Documents)

- <a id="def-entry"></a>**Entry** — one uniformly-shaped item in a Register or Embedded
  register (e.g. *decision entry*: ID, one-line summary, status, pointer
  to reasoning).
- <a id="def-embedded-register"></a>**Embedded register** — a register-shaped section within a Document,
  holding Entries under the same rules as a Register; current instances:
  the *Deviation register* and *Custom definitions section* of the
  Classification.
- <a id="def-requirement"></a>**Requirement** — a statement of needed behavior/quality; traceability
  source.
- <a id="def-rationale"></a>**Rationale** — reasoning attached to a decision/plan/rule.
- <a id="def-status-line"></a>**Status line** — machine-readable designation carried by Plans and
  other lifecycled content.
- <a id="def-binding-block"></a>**Binding block** — the Agent bootstrap section referencing the
  Classification with strictness language.
- <a id="def-custom-content-type"></a>**Custom content type** — as per custom documents.

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

<a id="def-review-round"></a>**Review round** · **Interim adjudication** (defined above) ·
<a id="def-audit"></a>**Audit** (form / semantic,
[Article 9](constitution.md#article-9--audits)) · <a id="def-amendment"></a>**Amendment** ·
**Release** (defined above) ·
<a id="def-migration"></a>**Migration** ([Article 8](constitution.md#article-8--amendments-versions-and-migration))
· <a id="def-re-classification"></a>**Re-classification** (updating any declared
Classification field to match actual state,
[Article 4](constitution.md#article-4--applicability-then-precedence)) ·
<a id="def-promotion"></a>**Promotion**
(the C-tier-raising case of Re-classification) · <a id="def-chunk-gate"></a>**Chunk gate**
· <a id="def-close-out"></a>**Close-out** (plan completion) · <a id="def-standardization"></a>**Standardization** (custom →
standard).

## Roles

<a id="def-human-owner"></a>**Human owner** · <a id="def-agent"></a>**Agent** (session, working) · <a id="def-reviewer"></a>**Reviewer** (human or
agent; adjudication reserved to humans) · <a id="def-auditor"></a>**Auditor** (docs-auditor agent
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
