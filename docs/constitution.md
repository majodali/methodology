# The Methodology Constitution

*The Constitution is Level 1 of exactly three levels. It changes rarely, by
human decision only. Everything below it is amendable through the process it
defines.*

Split at bootstrap from *The Methodology Constitution & Vocabulary — Draft
v0.7*, together with [vocabulary.md](vocabulary.md) and the rule corpus under
[rules/](rules/README.md). The draft's changelog is preserved at the end of
this document as the pre-1.0 history.

Deliberately incomplete and completely true: every structure here was needed
by decisions already made in working sessions; nothing is included on spec.

Normative keywords MUST, MUST NOT, SHOULD, SHOULD NOT, and MAY are
used per RFC 2119 / RFC 8174 (source: [IETF BCP 14](https://www.rfc-editor.org/info/bcp14)).
The Constitution holds its own normative statements to this convention.

## Article 1 — Purpose

The methodology is a well-defined corpus: a standard vocabulary and a body of
rules written in that vocabulary, governing the process and documentation
aspects of majodali projects. Its purposes, in order: (1) let any project be
audited at any time; (2) inform process definitions down to fine detail;
(3) make project corpora navigable and trustworthy for humans and agents
alike.

## Article 2 — Levels and termination

There are exactly three levels: the **Constitution** (governs the
methodology), the **Methodology** (governs projects), and **Project
documentation** (governs work). There is no fourth level. Questions about the
Constitution are resolved by the human owner, not by further meta-documents.

## Article 3 — Authority

Documentation is authoritative; tooling is derivative. The plugin, hooks,
skills, generators, and any other machinery are **built artifacts whose
specification is the methodology's documents**. Where machinery and document
disagree, the document is right and the machinery has a bug. No artifact
under `.claude/` at any level is ever authoritative (the documentation-
primacy practice, [A0](practices.md), applied to the
methodology itself).

## Article 4 — Applicability, then precedence

Rule selection is a two-stage procedure. Both stages MUST be mechanically
decidable from a project's **Classification document together with the
designations it explicitly references** — currently only Workflow stage
designations carried by Backlog entries (see *Workflow*,
`docs/vocabulary.md`). No other project content may enter the decision.
Expanding this basis — referencing any new class of designation or
content — is a **constitutional change** (Article 2), never a vocabulary
amendment; "currently" marks a deliberate gate, not a snapshot.

**Stage 1 — Applicability.** Every rule carries applicability conditions
drawn exclusively from the declared Classification fields — **C-tier**,
**S-level**, **type**, **target** — or from derived conditions defined in
the vocabulary as functions of those fields and of the designations the
Classification references. A rule is *in play* for a project iff the
project's declared state satisfies its conditions. A project **without a
Classification document is C0 by definition**, with every optional field
at the omission default the Classification definition assigns
(`docs/vocabulary.md` — the sole authoritative location for defaults);
declaring anything else requires a Classification. There are no *project-level* exemptions outside this
mechanism — a C0 project is governed by exactly the rules tagged `[C0+]`,
not by a carve-out (see Article 7). Per-material exemption exists in
exactly one form: the sandbox designations of Article 7.

**Declaration accuracy.** Classification declarations — including the
implicit C0 default of an absent Classification — MUST reflect the
project's actual state; misdeclaration is non-compliance, and the audit
perimeter is never self-selected. **Omitting an optional field is itself
a declaration of that field's omission default, subject to the same
accuracy MUST** — a *deployable* project in live operation that declares
no Workflow is declaring `deployed = false` falsely, and a C1 web tool
that omits
type is declaring `exploration` falsely. Accuracy extends to the
designations the decidability basis reads: where a Workflow is declared,
Backlog entries MUST carry current stage designations, and letting them
lapse is misdeclaration. A project whose actual state has outgrown its
declaration MUST be **re-classified** (*Re-classification*,
`docs/vocabulary.md`; when the C-tier rises this is *Promotion*).

**Stage 2 — Precedence.** Among in-play rules that conflict, the first
applicable entry in this order wins:

1. A **project deviation**, recorded in the project's Classification,
   citing the rule it overrides and the rationale.
2. A **project custom definition** (Article 7), within its declared scope.
3. The **more specific rule**, determined in order over **effective
   constraining conditions** — stated or defaulted (Article 5), then
   normalized: a condition constrains iff it excludes at least one
   possible value of its field; vacuous tags (`[C0+]`, `[S0+]`, any
   full-range tag) are dropped before counting, and restating a default
   is never a specificity advantage — notation never beats semantics:
   (a) the rule whose
   satisfied conditions name more of the project's declared fields and
   referenced designations; (b) if equal, the rule whose condition on a
   shared field covers the narrower range (`[C3]` beats `[C2+]`) — and
   when each rule is narrower on a *different* shared field, the rule
   narrower on the higher-weighted field per (c) wins; (c) if
   still equal, the rule whose distinguishing conditions rank higher in
   the weight order: S-level, then C-tier, then type, then target, then
   derived conditions (each derived condition's vocabulary definition MUST
   state its position when finer ranking among derived conditions is
   needed).
4. A conflict that survives step 3 is a **corpus defect**: it MUST be
   recorded as a methodology issue and resolved by amendment; until then
   the human owner's ruling stands and is recorded with the issue.

Explanatory text sits outside this order entirely: it is non-normative and
cannot conflict with rules. If explanatory text appears to contradict a
rule, the rule wins and the text has a bug.

Overrides are always explicit: a deviation or custom definition that
overrides a rule MUST link the rule it overrides. Silent divergence is
non-compliance even when the divergence would have been approved.

## Article 5 — Rule form

Every rule has: a stable **ID** (rule-corpus format,
[docs/rules/README.md](rules/README.md)); a
**statement** using BCP 14 keywords; **applicability conditions** per
Article 4 (default when unstated: `[C1+]`, all S-levels, all types, all
targets); a link to its **motivating instance** (Article 6); and, if
imported or adapted from a third-party source, a **source citation**.
Rules MAY link a rationale note. Terms used normatively MUST be defined in
the vocabulary (`docs/vocabulary.md`).

## Article 6 — Inclusion: every rule earns its keep

A rule or vocabulary term enters the methodology only when (a) a live
project needed it, and (b) its inclusion credibly saves more time across
the portfolio than it costs. Every rule records its motivating instance as
a link. Completeness is explicitly a non-goal. Any rule that no project
has **exercised** (vocabulary-defined: it observably constrained or
shaped work, not merely was in play) within its **review horizon**
(vocabulary-defined; default two review rounds, measured from the rule's
first adoption) MUST be flagged for amendment or removal by the
methodology's own semantic audit (Article 9) — the anti-languish principle
([D6](practices.md)), applied to the methodology
itself.

## Article 7 — The C0 baseline, custom definitions, and the sandbox

**C0 baseline.** A project without a Classification is C0 with the default
fields of Article 4 stage 1; a project MAY declare a minimal
Classification (see the Classification definition's mandatory/optional
fields) to override any default. Rules tagged `[C0+]` form the
exploration baseline, currently: a README stating the question being
explored ([W-007](rules/working-agreement.md#w-007--every-project-has-a-readme-that-says-what-it-is));
the test-modification rules where tests exist
([W-002](rules/working-agreement.md#w-002--existing-tests-are-signals-not-obstacles)); and the
secret-hygiene rules
([S-001/S-002](rules/security.md) — public
exploration repos need them most). All other rules default to
`[C1+]` (Article 5) and are therefore not in play at C0.

**Custom definitions.** The vocabulary is extensible per project:

- A project MAY define custom document, content, or artifact types. Each
  custom definition MUST live in the **Custom definitions section of the
  project's Classification** (the current standard home; relocating it
  would be an amendment), and every instance of the custom type MUST link
  its definition.
- Custom definitions are audited like standard ones. Audits SHOULD flag
  convergent custom definitions across projects as standardization
  candidates (promotion by amendment).

**Sandbox.** A project MAY hold material under a sandbox location or an
`in-progress` / `not-compliant` designation for temporary use. Sandbox
material is exempt from **content rules** but not **existence rules**
(vocabulary-defined): it MUST carry the designation visibly, and audits
treat sandbox **age** as a finding. Temporary is a state, not a home.
Sandbox designation is the Constitution's only per-material divergence
mechanism; it is bounded, visible, and aged, and it is out of scope for
Article 8's two project-level forms.

## Article 8 — Amendments, versions, and migration

- Anyone — human or agent — MAY propose an amendment. Agents are
  **encouraged** to propose amendments arising from lessons learned or
  observed inefficiencies. A proposal is a PR to the methodology repo
  containing the change and a link to the evidencing instance. Agents
  MUST NOT self-apply proposed practice mid-project. Amendment PRs MUST
  receive the traceability-link review of Article 9 regardless of the
  methodology's own declared tier — they are the highest-stakes changes
  in the system.
- Proposals are adjudicated at **review rounds**, or at **interim
  adjudications** (vocabulary-defined) that the human owner MAY convene
  at any time for named proposals; every scheduled review round
  re-examines the interim decisions taken since the last round.
  Review rounds occur on a cadence set by the human owner and recorded in
  the methodology repo; the interval MUST be bounded (initial calibration:
  at least quarterly) so that review-horizon flagging and adjudication
  timing are decidable. Reviewers at each round check projects against the
  current standard *and* all open proposals, so each proposal accumulates
  evidence before adjudication. Acceptance is the human owner's decision,
  informed by an impact assessment across projects. The review MUST first
  pursue the question *"how do we make this amendment work for all
  impacted projects?"* — a formulation accommodating every project is
  preferred; a deviation is the fallback when accommodation would damage
  the amendment's value, never the default.
- The methodology is **versioned** on a single line — versions are never
  branched. Versioning exists solely to let each project **migrate at its
  own pace**: a project's Classification pins a version, which is its
  **compliance target** (vocabulary-defined), and amendments are never
  retroactive for pinned projects — a version bump ships migration notes
  (accumulated per amendment in the **Release register**,
  `docs/releases.md`), and a pinned compliance target remains until the
  project migrates.
  **The one exception is the unpinned C0 project**, whose compliance
  target is the latest version and moves with it: amendments to the
  `[C0+]` baseline apply there without a migration step, acceptable
  because the baseline is minimal. Because deviations recorded against a
  moving target can silently stale, recording a deviation at C0 SHOULD be
  accompanied by pinning. Residence on an old version is expected to be
  temporary, not a home. The mechanics of proposal, adjudication,
  acceptance, release candidacy, release, and adoption are defined in
  the **release process** (`docs/release-process.md`), a
  Methodology-level document amendable through this Article.
- Amendments are proposed against the **latest version only**. A project
  on an older version that has amendments to propose SHOULD first migrate
  to the latest — recording deviations where needed — and propose from
  there.
- **Project-level divergence from in-play rules has exactly two forms and
  no third**: version lag (pinned to an older version, pending migration)
  and recorded deviations (recorded against the project's compliance
  target, per Article 4 stage 2.1 — so a lagging project's deviations are
  well-defined too). At migration a project adopts each changed rule or
  records a deviation with rationale. Per-material sandbox divergence is
  governed by Article 7 and is out of scope here. Both project-level forms
  are to be minimized, in good time, never hidden: every audit MUST call
  out the project's version lag and all current deviations (Article 9).

## Article 9 — Audits

- Every C1+ project undergoes audits of two kinds. **Form audits** —
  structure, designations, link integrity, sandbox age, custom-definition
  hygiene — run via machine on **every day on which the project has
  changed**: per-file content checks are scoped to the change deltas,
  while repo-wide invariants — existence rules, link integrity, and
  declaration-consistency — are evaluated over the full tree on every
  run (calibration resolved 2026-08-20: full-tree invariant evaluation
  closes the delta blind spot of deletions breaking inbound links in
  unchanged files; evidencing instance in the Release register). **Semantic audits** —
  verifying that traceability links actually support what citing content
  claims, and that documents are substantively current, not merely
  well-shaped — MAY be requested at any time; at C2 and C3 they are
  additionally auto-triggered when cumulative change since the last
  semantic audit exceeds a threshold of total project size (initial
  calibration: 50% at C2, 25% at C3; the trigger approach itself is
  exploratory and open to amendment). Semantic audits include human
  adjudication.
- Every audit of either kind MUST call out the project's version lag and
  all current deviations (Article 8).
- **The methodology repo is itself a project under this Constitution**,
  with its own Classification carrying its tier — the Constitution does
  not fix it — and the reserved type **`methodology-corpus`**, which
  exactly one project MAY hold (field values are amendment-controlled,
  so uniqueness is enforceable; this is the tag by which rules denote
  this repo). It is subject to Articles 9–10 like any other project, and
  it maintains the **Portfolio register** (`docs/vocabulary.md`): the
  enumeration of all majodali projects, including implicit-C0 ones. **The
  register MUST contain every project** — this duty binds the
  methodology repo, not the projects themselves (an unregistered
  implicit-C0 repo has no Classification to bind), and its M- mirror
  tags `[type: methodology-corpus]`. **A semantic audit of the
  methodology runs at every review round**, whatever its declared tier;
  it sweeps the Portfolio register, and includes a **census pass** that
  (a) reconciles the register against observable repositories,
  refreshing stale classification summaries, and (b)
  spot-checks declarations — including implicit-C0 defaults — against
  observable project state. The census is the detector for Article 4's
  declaration-accuracy MUST: project-level audits are gated by declared
  tier, so under-declaration is caught here, from outside any single
  project. This audit is also the executor of Article 6's anti-languish
  flagging, and additionally examines corpus-level properties no single
  project's audit can see: rule exercise across the portfolio, open
  corpus defects (Article 4), and convergent custom definitions across
  projects (Article 7 standardization candidates).
- A passed audit means **"no detected violations"** against the project's
  compliance target. It is never a certified state; "compliant" appears in
  this corpus only inside the defined term *compliance target*.
- Human PR review at C2+ MUST include following traceability links from
  changed content (performed against the branch's rendered tree; source
  diffs do not resolve links). The agent review pass is expected to
  resolve and verify links mechanically.

## Article 10 — Naming, moves, and traceability

- Document identity rests on **stable naming hierarchies**, which are
  themselves expressions of project taxonomy and decisions. Naming is not
  arbitrary; it is also not fully pre-determinable.
- Documents MAY be renamed or moved. Tooling MUST update inbound links
  within the repo automatically, and MUST warn when moving or renaming a
  heavily linked document — not because it is difficult, but because heavy
  linkage makes the move a de facto decision review.
- A document referenced from **outside its repo** is public API: moving it
  MUST leave a tombstone/redirect stub or an explicit deprecation note,
  because external links cannot be rewritten.
- Traceability links (requirement → decision → plan → implementation →
  verification) MUST be present; other relationship links MAY be added
  where they earn their keep. Dangling links are audit findings.

## Article 11 — Transitional provisions

Until the tooling an audit duty presupposes exists, that duty MAY be
discharged manually and best-effort; each such gap MUST be recorded in the
methodology repo's Risk register with the tooling it awaits. Transitional
status ends per gap when the tooling lands, and this Article is reviewed
for deletion once the Risk register holds no transitional entries.

---

## Draft history (pre-1.0)

The changelog of *The Methodology Constitution & Vocabulary — Draft*,
which held this Constitution (its Part I), the [vocabulary](vocabulary.md)
(Part II), and the [rule-corpus organization](rules/README.md) (Part III)
before the bootstrap split. Preserved verbatim.

*Changes in v0.7: applies all findings of the fifth Fable 5 review — the
reserved singleton type `methodology-corpus` added so tags can denote the
methodology repo (M- mirrors now expressible; Portfolio-register
maintenance rehomed as its duty); first adoption redefined over in-play
rather than inclusion, with never-in-play rules flagged when their clock
hasn't started; the unpinned-C0 moving compliance target carved out of
Article 8's universals with deviation-at-C0 pinning guidance; the
accuracy example qualified to deployable projects; specificity counts
effective conditions, stated or defaulted; the mirror paragraph rehomed
under its own heading; the register summary marked informative cache with
census drift-refresh; the Auditor trigger list completed.*

*Changes in v0.6: applies all findings of the fourth Fable 5 review — a
Portfolio register created as the enumeration the corpus-level audit
sweeps, with a census pass checking declarations against observable state
(the detector for declaration accuracy); specificity counts only
constraining conditions (vacuous tags normalized away); "exercise" defined
with the review-horizon clock starting at first adoption; C0 compliance
target defaulted to latest; omission of an optional field made itself a
declaration subject to the accuracy MUST; `deployed` redefined to entail
`deployable`; Re-classification added with Promotion as its C-tier case;
omission defaults made authoritative in the vocabulary alone;
constitutional direct duties to be mirrored as M- rules; changelog order
and stale parenthetical fixed.*

*Changes in v0.5: applies all findings of the third Fable 5 review —
declaration accuracy made a constitutional MUST (misdeclaration is
non-compliance, including lapsed stage designations and the implicit C0
default); the methodology's semantic audit bound to every review round
(executing Article 6) with its tier moved out of the Constitution into its
own Classification and amendment PRs given mandatory traceability review;
Classification fields marked mandatory/optional with omission defaults;
mixed-narrowness tie-break and live derived-condition ranking added; O-
floor lowered to `[C1+][deployed]`; `docs-corpus` type added with field
enums extendable by amendment only; decidability-basis expansion made an
explicitly constitutional change; C0 baseline gains secret hygiene; prose
moved out of scope cells; stale echoes fixed.*

*Changes in v0.4: applies all findings of the second Fable 5 review —
decidability basis honestly restated (Classification plus the designations
it references); Classification absence defined as the C0 default; sandbox
and `not-compliant` scoped as per-material divergence, restoring both
absolutes; deviations defined against the compliance target; specificity
given range-narrowness and derived-condition weights; review rounds given
a bounded cadence; the methodology made a project under its own
Constitution with corpus-level audit duties; Embedded register content
type added; Auditor role updated; REQUIRED dropped; widening exception
clarified; S-section floor moved to `[S0+]`; Workflow naming frictions
resolved.*

*Changes in v0.3: amendment/version/deviation model settled per owner
decision — versioning exists solely for migrate-at-own-pace, deviations are
the sole divergence mechanism on the current version, every audit calls out
all deviations and version lag, amendments are proposed from the latest
version only; audit cadence defined (daily delta-scoped form audits;
on-request semantic audits with delta-ratio auto-triggers at C2/C3);
`provisional` folded into `in-progress`; custom definitions homed in the
Classification; the `deployed` boolean replaced by per-project Workflow
state.*

*Changes in v0.2: applies all findings of the 2026-07-21 Fable 5 review —
applicability separated from precedence and made decidable from declared
Classification fields; C0 handled by tagging, not exemption; amendment
acceptance vs. version pinning de-duplicated (accept-or-deviate moves to
migration time); CLAUDE.md and README given artifact types; "compliance
target" defined; internal citations added; keyword casing corrected;
Event register renamed; review horizon, existence/content rules, and the
tier scales defined.*
