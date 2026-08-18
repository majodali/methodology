# Practice definitions (imported: Standard Development Methodology — Proposal v0.2)

Imported verbatim at bootstrap. This document holds the practice
definitions (A0–F5) that rules in [docs/rules/](rules/README.md) cite as
motivating instances, and it is the source for the remaining extraction
passes (C-, D-, O-, Q- and further S- rules — see the
[extraction notes](rules/README.md#extraction-notes-for-the-first-review-round)).
Where a practice here and an extracted rule differ, the rule corpus is the
norm; this document is its evidenced source material. Pre-import
references to "this repo" and repo layout describe the proposal's intent
at writing time and are preserved as history.

---

A unified methodology for all majodali projects, synthesized from the practices that
have actually evolved in `serverless-web-app-template`, `allegro`, `in-real-life`,
and (by inference) `in-real-life-ops`. Intended to live as its own repo (e.g.
`majodali/methodology`) that every agent session is directed to read.

Design stance: the methodology is a **catalog of practices plus a classification
model that selects among them** — not a single mandatory process. Each project
declares its classification in its `CLAUDE.md` and adopts the corresponding
profile, with documented deviations.

---

## 1. Classification model

Every project declares four variables. These are orthogonal; each independently
turns practices on or off.

### 1.1 Criticality (C-tier)

| Tier | Meaning | Current examples |
|---|---|---|
| **C0 — Exploration** | Throwaway or research code; learning is the deliverable | parser experiments, spikes |
| **C1 — Personal tool** | You depend on it; nobody else does | home-infrastructure, comms-hub, minecraft-mcp |
| **C2 — Serious project, pre-users** | Long-lived, ambitious, but failure harms only the work itself | allegro, in-real-life today |
| **C3 — Production with real users** | Other people's data, trust, or time is at stake | in-real-life at launch |

### 1.2 Sensitivity (S-level)

| Level | Meaning | Consequence |
|---|---|---|
| **S0 — Public code only** | No secrets, no personal data | Public repo fine; minimal controls |
| **S1 — Infrastructure secrets** | AWS accounts, deploy credentials, domains | OIDC-only auth, no long-lived keys in repos, config in a private ops repo or repo variables |
| **S2 — Personal data / PII** | Real people's information | Privacy-by-design practices mandatory (see §2.E): PII registry, crypto-shredding or equivalent, export/delete rights, public/private repo split |

### 1.3 Project type

`web-app` · `backend-service` · `component/library` · `language/tool platform` ·
`exploration` · `ops` — see §4 for what each profile changes.

### 1.4 Deployment target

`none/local` · `static site` · `serverless AWS` · `package registry` ·
`home infrastructure` — determines which delivery practices (§2.D) apply and
which reference implementation to copy (the template repo is the reference for
serverless AWS).

**Rule of thumb for escalation:** criticality drives *verification and delivery*
rigor; sensitivity drives *security and privacy* rigor; type and target select
*which* concrete mechanisms implement them. A C2/S0 language platform and a
C2/S2 web app need equally serious verification but completely different
security postures.

---

## 2. Practice catalog

Organized into six disciplines. Each practice is tagged with the minimum tier at
which it becomes **required** (it's always *permitted* earlier).

### A. Knowledge & memory

The strongest convergent finding across your repos: **durable project knowledge
lives in the repo, structured for agent consumption, updated in the same commit
as the work it describes.** The divergence is in shape, and IRL's shape is the
better one.

- **A0. Documentation primacy (C1+).** Project documentation under `docs/` is
  the single authoritative record. Everything under `.claude/` — memory files,
  plans, settings — and `CLAUDE.md` itself are agent-operational conveniences:
  assume **no human ever reads them**. Above C0, all work must be plannable,
  reviewable, and resumable from project documentation alone; if something in
  `.claude/` turns out to be load-bearing for the project, it is in the wrong
  place and moves to `docs/`. `.claude/` may *cache or point to* project docs,
  never substitute for them.
- **A1. Thin `CLAUDE.md` as index (C1+).** `CLAUDE.md` covers: what the project
  is, how to build/run/test, architecture at a glance, conventions, and
  *pointers* to the registers below. Target under ~200 lines. It is a bootstrap
  for agent sessions, never an authoritative record (A0) — a human should be
  able to ignore it entirely and miss nothing. IRL (144 lines) is
  the model; Allegro's 618-line monolith is the anti-pattern — it duplicates
  what BACKLOG.md and design docs should hold, and every completed phase makes
  it heavier (its "completed items" section alone is the bulk of the file).
- **A2. Backlog as the single source of truth for progress (C1+).** One
  dependency-ordered register of done/next. Completed items are rewritten to
  describe *what actually shipped* (the checked entries double as the
  implementation map — IRL's articulation of this is the canonical wording).
  Updated **in the same commit** as the work; new scope discovered mid-slice is
  added rather than done silently. Allegro's "update BACKLOG.md before every
  commit" and IRL's same-commit rule are the same norm — standardize the wording
  and the location (`docs/backlog.md`).
- **A3. Decision register (C2+).** IRL's `decisions.md` pattern: numbered
  decisions (D1…), one line each, pointer to the note holding the reasoning,
  explicit "decisions are revisable" framing. Allegro has the *content* of this
  scattered across `.claude/memory/design_*.md` files but no register — an
  agent can't survey "what's already been decided" without reading everything.
- **A4. Companion registers (C2+ as needed).** From IRL: `open-risks.md` (known
  gaps with status), `radar.md` (tracked-but-undesigned workstreams),
  `hypotheses.md` (embedded analyses as testable, reversible hypotheses).
  Adopt each when the corresponding pressure appears; don't create empty files.
- **A5. Design notes per area (C2+).** One markdown note per designed area,
  holding the reasoning the registers point to. Both Allegro
  (`.claude/memory/design_*`) and IRL (`docs/*.md`) do this; standardize on
  `docs/` so the notes are first-class and public-repo-visible, reserving
  `.claude/` for agent-operational material.
- **A6. Agent memory directory (C1+, strictly non-authoritative).** Allegro's
  `.claude/memory/` split with a `MEMORY.md` index is the most developed
  instance, but under A0 its role narrows: it holds only agent-operational
  material — session norms, working-style feedback, pointers into `docs/`.
  Design memos (`design_*`) migrate to `docs/` (A5); project-state files
  migrate to the backlog and registers. The generalizable process norms (see
  §3) move up into the methodology repo itself so they don't need re-teaching
  per project.
- **A7. Plan documents (C2+) — in `docs/plans/`, kept ruthlessly current.**
  One doc per planned feature arc, written *before* implementation, chunked
  for approval — the artifact side of the working agreement (B1). Per A0 these
  are project documents, not `.claude/` artifacts: they live in `docs/plans/`
  and are named **strictly for the feature or outcome under development**
  (e.g. `effect-types.md`, `mutual-recursion-termination.md`). Because plan
  details and implementation order change frequently, plan hygiene is a
  discipline of its own: every plan is updated as reality diverges from it,
  and obsolete plan content is either **deleted** or **marked obsolete with
  the factor or decision that drove the change and a pointer to what
  superseded it**. A completed plan is closed out explicitly (superseded by
  the backlog's checked entries per A2), never left half-true. A reader must
  be able to trust that anything unmarked in a plan is still the current
  intent.
- **A8. Non-developer documentation (recommended C2+, expected C3 or whenever
  there are stakeholders).** When a project moves fast, project docs alone can
  outpace what the maintainer — let alone other stakeholders — can absorb. Two
  practices address this, both valuable, neither always required:
  **(a) Literate specification-by-example** — self-hosted BDD/spec pages in
  literate style, with explanations embedded among executable behavioral
  tests, so the spec is simultaneously readable prose and verified truth
  (Allegro carried this for a while; worth reviving as a named practice).
  **(b) Hosted register views** — web representations of the decision, risk,
  hypothesis, and radar registers with supporting explanations, published as
  **latest snapshots only** unless historical detail earns its keep. Both
  serve the same principle: anyone following the project should have a
  current, honest window into it without reading commits.

### B. Agent working agreement

Allegro is the only repo where this is codified, but the norms are clearly
portfolio-wide preferences. These belong in the methodology repo as universal
(C0+ unless noted) so every agent inherits them.

- **B1. Two delivery modes.** *Current work — stay close*: deliver a tight
  increment, summarize, stop; don't chain steps without confirmation ("great
  work" without "next" means discuss, not continue). *Upcoming work — plan
  first*: for larger features, write a plan doc (A7) and let the human decide
  chunk boundaries; don't start chunk 1 without explicit go-ahead; after each
  chunk, summarize and wait.
- **B2. Test modification rules.** Add new tests and assertions freely; **never
  remove or change an existing test condition without discussing first** — a
  failing test is a signal (possibly of a prior misunderstanding), and silently
  "fixing" it discards the signal. This includes expected-output comments and
  structural setup. Investigate root cause before touching the test file.
- **B3. Docs in the same commit.** `CLAUDE.md`, backlog, and any affected
  registers/notes update as part of the commit that changes what they describe
  — never after.
- **B4. Corpus-driven review-and-redo (design-heavy projects).** Every feature
  is provisional until reviewed against a corpus of real use; ship the version
  that maximizes learning, build escape hatches, resist premature "final form"
  commitments. Allegro states this for language features; IRL's "decisions are
  revisable" and hypothesis register are the same stance. Promote to a
  portfolio principle.
- **B5. Fix root causes; no unowned known-issues.** Don't accept "known issues"
  unless truly known, isolated, and with a planned remediation (tracked in
  open-risks).
- **B6. Naming conventions.** Plan documents and branches are named **strictly
  for the feature or outcome under development** — descriptive, boring, and
  greppable (`docs/plans/effect-types.md`, branch `functional-test-backfill`).
  The evocative two-word-plus-author plan labels and any similar themed naming
  found in existing repos were inventions of past agent sessions, not standard
  practice — retire the convention; existing docs can keep their filenames but
  new ones follow the outcome rule. **Branches are single-use**: one branch
  per deliverable, deleted after merge, never reused for the next piece of
  work. General naming meta-rules stand: no stuttering names; flat numbering
  over primes; themed names used sparingly, locked once chosen, and never
  extended by an agent unprompted.

### C. Quality & verification

A ladder — each rung assumes the previous:

- **C1. Typecheck/lint clean (C1+).** The minimum gate; the template's
  `npm run typecheck` across workspaces is the pattern.
- **C2. Unit tests, co-located (C1+ for anything with logic; C0 optional).**
  IRL's `*.test.mjs` beside sources; Allegro's 970+-test suite. Runner-native,
  no heavy frameworks.
- **C3. Synthesis/build verification (deployable projects, C1+).** `cdk synth`
  in CI proves infrastructure code is coherent without touching AWS — template
  pattern.
- **C4. Functional tests against a deployed test environment (C2+ for anything
  with a backend).** IRL's pattern: CI deploys `IrlStackTest` on merge, then
  runs the functional suite against the live stack, serialized via concurrency
  groups. This is the single most valuable practice to generalize — it's what
  makes "it works" mean something for serverless systems that can't be
  meaningfully run locally.
- **C5. Post-deploy diagnostics / self-tests (C2+ for deployed apps).** The
  template's admin-only diagnostics page: every feature ships with a live
  self-test step, using non-mutating negative paths so a self-test can never
  damage state. Complements C4: functional tests verify the *test* stack;
  diagnostics verify the *deployed* stack, on demand, forever.
- **C6. Scenario walkthroughs (C2+ for design-heavy systems).** IRL's practice
  of running concrete scenarios through the *design as written*, adversarially,
  before code — with findings triaged into decisions. Cheap, catches whole
  classes of error tests can't.
- **C7. Build safety in — fail closed (C2+).** Allegro's stance: a failed
  proof, undeclared effect, or non-exhaustive match *halts compilation*; IRL's
  transactional projections and idempotency are the same instinct. As a
  portfolio principle: invalid states should be unrepresentable or loudly
  fatal, never silently degraded.
- **C8. Deterministic seams for external dependencies (C2+ when applicable).**
  IRL's LLM seam — injected provider, real API in production, canned
  deterministic stub in test/workshop — generalizes to any expensive or
  nondeterministic dependency. A named practice so agents reach for it.

### D. Delivery & environments

- **D1. Branch/merge policy by tier.** C0–C1: direct commits to `main` are
  fine. C2: PRs with CI verification gating `main` (template pattern);
  solo-review is acceptable, the PR exists for the CI gate and the record.
  C3: PRs mandatory, branch protection on, deploys only from `main`.
- **D2. PR template with verification checklist (C2+).** The template's version
  (summary / changes / which tests cover this / notes) — adapted per project to
  reference its own test ladder.
- **D3. CI on every PR (C2+).** Typecheck + build + synth + unit tests. No AWS
  credentials in the PR path.
- **D4. Deploy on merge, OIDC only (C2+ deployed projects).** GitHub Actions
  assuming an AWS role via OIDC; no long-lived keys anywhere. Path-filtered
  triggers, non-cancelling concurrency groups, `workflow_dispatch` escape
  hatch — all template patterns.
- **D5. Environment progression (C2+ backends).** At minimum a test
  environment that CI deploys and tests against (C4) plus production. IRL's
  **workshop mode** — one codebase, a runtime flag, simulated time, gate
  bypass — is the sophisticated version for products that need demo/rehearsal
  environments; adopt where the product warrants it.
- **D6. Operations ownership — the split decision.** Every deployed project
  must have a *named home* for its operational surface; whether that home is a
  separate repo is a deliberate decision, made against these criteria.
  **Split out an ops repo when** at least one holds: (a) *visibility
  mismatch* — the app repo is public but env config, account context, or
  deploy invocation must stay private (the original irl-ops trigger);
  (b) *access mismatch* — future collaborators should touch app code but not
  production controls; (c) *shared surface* — multiple app repos deploy
  through one operational estate; (d) *cadence mismatch* — incident notes,
  env changes, and runbook edits would otherwise churn the app repo's
  history. **Don't split when** none apply: a solo, private, single-app
  project keeps an `ops/` directory (or `docs/ops.md`) in the app repo —
  premature splitting is how ops repos languish. **What a split ops repo
  owns:** per-environment config and CDK *context* (the stack constructs
  themselves stay with the app they describe), production deploy workflows or
  runbooks, secrets strategy, rollback and incident procedures, monitoring
  and alarm definitions, and its own backlog. **What it never owns:**
  application code, design decisions, or anything a developer needs to build
  and test — the app repo must remain self-sufficient through its test
  environment. **The anti-languish rule:** a split ops repo is legitimate only
  if the production deploy path *actually runs through it*. If deploys are
  happening while the ops repo sits untouched, the split has failed in
  practice — either reroute the path through it (make it the only way to
  reach prod) or fold it back into the app repo. Review this at every C-tier
  promotion.
- **D7. Config via toggles with safe defaults (templates/libraries).** The
  template's `ENABLE_WEBSOCKET` / `HOSTING_MODE` approach: everything off/default
  until opted in; each toggle documented with its effect.
- **D8. Rollback story (C3).** Before real users: how do you roll back a bad
  deploy of code, of infrastructure, of data-shape changes? Currently
  undocumented everywhere (see gaps).

### E. Security & privacy

- **E1. No secrets in repos, ever (all tiers).** OIDC for CI; Secrets Manager
  (IRL's LLM key pattern) or ops-repo-held config for runtime.
- **E2. Least-privilege deploy roles (S1+).** Separate roles per
  environment (IRL's test-role vs prod-role split).
- **E3. Privacy by design (S2).** The IRL cluster, generalized: data
  minimization as a product stance; a **PII registry** enumerating where
  personal data lives; **crypto-shredding** (per-aggregate keys, destroyed on
  delete) or an equivalent hard-delete mechanism; export and delete as
  first-class routes exempt from other gates; opaque references instead of IDs
  in responses; no personal data in logs.
- **E4. Auth patterns by tier.** C1 tools: the template's admin-seeded
  bcrypt+JWT is fine. C3 with real users: managed identity (Cognito, as IRL
  chose).

### F. Operations & observability

- **F1. Structured logs (C2+ backends).** One JSON line per
  command/request with status, duration, error type — IRL's command-runner
  pattern.
- **F2. Tracing (C3 backends).** IRL's lightweight X-Ray subsegment emission
  (no SDK dependency) as the reference.
- **F3. Health endpoint + diagnostics (C2+ deployed).** Template patterns.
- **F4. Monitoring/alerting (C3).** Currently absent portfolio-wide; a
  pre-launch requirement for IRL. DLQs on async processing (IRL's projector)
  are the start; add alarms on DLQ depth, error rates, and functional-test
  failures.
- **F5. Runbooks (C3, in the ops repo).** Deploy, rollback, incident,
  data-correction procedures.

---

## 3. What moves *up* into the methodology repo

These are currently taught per-project (or only in Allegro) but are clearly
portfolio-wide, and should be stated once in the methodology so every agent
session inherits them: the working agreement (B1–B6 minus project-specific
naming), the backlog/same-commit rules (A2, B3), the thin-CLAUDE.md structure
with a skeleton template (A1), register templates (decision/risks/radar/
hypotheses skeletons), the verification ladder (§2.C) with the tier at which
each rung activates, the documentation-primacy rule (A0), the plan-document
format and hygiene rules (A7), the ops-split criteria (D6), and the
classification declaration format itself. The declaration lives in `docs/`
(e.g. `docs/classification.md`) and is the **strict definition of the
project's document lifecycles and workflows** — which registers exist, what
their update triggers are, what plan status transitions are legal, and which
tiered practices are active. It is first-class information for humans and
agents alike. `CLAUDE.md` only *references* it, in language that underlines
the strictness of the contract, e.g.:

```
## Methodology — binding
This project follows majodali/methodology v0.x as declared in
docs/classification.md. That file strictly defines this project's
document lifecycles and workflows. Read it before any work; nothing
in this file or under .claude/ overrides it.

Classification: C2 / S2 / web-app / serverless-aws
Deviations: no PR flow yet (solo velocity — revisit at C3);
            legacy plans still under .claude/plans (migrating to docs/plans on touch)
```

The deviations line is important: adoption is per-project by your stated intent,
and an explicit deviations register keeps divergence *chosen* rather than
accidental.

---

## 4. Project-type profiles

**Web app / backend service** (IRL; anything spawned from the template) — full
§2 per tier. The template repo is the reference implementation for the
serverless-AWS target and should track the methodology as it evolves.

**Language / tool platform** (Allegro) — knowledge discipline (§A) and working
agreement (§B) at full strength; verification is C1–C2 plus its own
formal-methods ladder (which is the project's subject matter, not just its
process); delivery is D1–D3 (CI verify) with D4 applying only to its website
loop; §E–F mostly N/A at S0. The corpus review-and-redo (B4) is central.

**Component / library** — C1–C3 verification, D7 toggle discipline, semantic
versioning and a changelog (a practice none of the reviewed repos needs yet but
the methodology should define for when one does).

**Exploration** (C0) — deliberately exempt from almost everything: a README
stating the question being explored, and B2 (test rules) if tests exist.
The methodology should say this explicitly so agents don't impose ceremony on
spikes. Graduation rule: the moment an exploration is something you'd be sad to
lose, it becomes C1 and gets A1+A2.

**Ops repo** — private; holds D6's contents (env config, deploy, rollback,
runbooks, incident notes); its backlog and risks registers cover operational
work.

---

## 5. Gap analysis per project

Legend: ✅ has it · 🟡 partial/divergent · ❌ missing (and matters at its tier) · — not applicable at its tier.

| Practice | template | allegro | in-real-life | irl-ops (inferred) |
|---|---|---|---|---|
| A1 Thin CLAUDE.md | ❌ none at all | 🟡 exists, monolithic (618 lines) | ✅ (144 lines, pointer-style) | ? |
| A2 Backlog source-of-truth | ❌ | ✅ BACKLOG.md | ✅ docs/backlog.md | ? |
| A3 Decision register | — | ❌ (content scattered in memory files) | ✅ D1–D59 | ? |
| A4 Risks / radar / hypotheses | — | ❌ | ✅ all three | ? |
| A6 Agent memory (feedback norms) | ❌ | 🟡 richest instance, but holds authoritative design content (violates A0) | ❌ | ? |
| A7 Plan docs | — | 🟡 exist, but in .claude/ with themed names; hygiene/closure undisciplined | ❌ | ? |
| A8 Non-developer docs (literate specs, hosted registers) | — | 🟡 had literate specs, lapsed | ❌ (registers repo-only) | — |
| C2 Unit tests | ❌ (typecheck + diagnostics only) | ✅ 970+ | ✅ co-located | ? |
| C4 Functional tests vs test env | ❌ (no test env) | — | ✅ CI-deployed IrlStackTest | ? |
| C5 Diagnostics self-tests | ✅ origin of the pattern | — | ❌ (would be valuable post-launch) | — |
| C6 Scenario walkthroughs | — | 🟡 (bench corpus is analogous) | ✅ two adversarial passes | — |
| D1–D3 PR gate + CI | ✅ | ❌ **no CI at all** | 🟡 CI yes; no PR template; deploy fires on push to main | ? |
| D4 OIDC deploy on merge | ✅ | — (website loop is manual) | ✅ (test stack; prod via ops repo) | presumably ✅ |
| D5 Test env / workshop mode | ❌ | — | ✅ both | ? |
| D8 Rollback story | ❌ | — | ❌ | ❌ (pre-launch req) |
| E3 Privacy-by-design cluster | — | — | ✅ (PII registry gaps self-flagged) | ? |
| F1–F2 Logs + tracing | ❌ | — | ✅ | ? |
| F4 Monitoring/alerting | ❌ | — | ❌ (DLQ exists, no alarms) | ❌ |

### Narrative per project

**serverless-web-app-template.** Excellent at what it is — delivery mechanics
and hard-won operational lessons codified in a copyable form. Gaps, viewed as
the reference implementation of this methodology: no `CLAUDE.md` (a project
spawned from it starts with zero agent guidance — the highest-leverage single
fix), no backlog/register skeletons, no unit-test scaffold (the diagnostics
philosophy is great but is post-deploy verification only; there's nothing
between "typecheck passes" and "it's live"), no test environment story (deploys
go straight to the one stack), no rollback documentation. Recommendation: the
template should ship the methodology's C1–C2 skeleton files (CLAUDE.md,
docs/backlog.md, a unit-test example) so derived projects start compliant.

**allegro.** The deepest working-agreement and knowledge culture, and the
weakest delivery mechanics. The glaring gap: **970+ tests and no CI** — nothing
runs them except a local invocation, no branch protection, no PR flow, so a
bad commit to main is caught only by the next session. A minimal
verify workflow (typecheck + `npx tsx src/test.ts`) is a one-hour fix with
outsized value. Second gap: an A0 violation across the board — the CLAUDE.md monolith and the
`.claude/memory/` design memos together hold most of the project's
authoritative knowledge where, by the primacy rule, no human is assumed to
look. Completed-phase narratives move to the backlog's checked entries (A2),
design memos to `docs/` under a decision register, plans to `docs/plans/`
renamed for their outcomes (`phase-h-plan.md` already fits; the themed ones
get outcome names on their next touch) and closed out per A7's hygiene rule.
Third: the literate spec-by-example pages it once had (A8a) lapsed — worth
reviving, since Allegro is exactly the project whose behavior benefits from a
readable, executable spec. Fourth: the website deploy loop (allegrolang.org)
is undocumented in-repo and manual — per D6 it needs a named home (an `ops/`
note suffices; no split warranted). Historical reasons are
legitimate here: Allegro predates the template's CI/CD codification, and its
solo, discussion-driven cadence made PR ceremony feel like overhead — the
methodology should let it keep direct-to-main (D1 at C2 permits solo-review
PRs, but the CI gate is the non-negotiable part, not the PR).

**in-real-life.** The most complete instance overall — design governance,
verification ladder through C4, privacy engineering, environments. Gaps: no
codified agent working agreement (Allegro's B-practices live only in Allegro's
memory files; IRL sessions rediscover the same norms — the methodology repo
solves this for both), no plan-docs practice despite doing plan-scale work, no
PR template, and `deploy-test` fires on push to main with no branch protection
mentioned — fine solo, but worth an explicit deviation note. Post-launch
(C3) requirements already visible: diagnostics self-tests (C5, borrowing back
from the template), rollback procedure, monitoring/alarms, and closing the
self-flagged PII-registry gaps for event-aggregate data. The radar (R1–R7)
already tracks several of these — the methodology mostly needs to bind C3
promotion to their completion.

**in-real-life-ops (not accessible — inferred, and known to have languished).**
The split itself was correct by the D6 criteria — public app repo, private
operational surface is exactly trigger (a) — but a languishing ops repo is the
predicted failure mode D6's anti-languish rule exists for: if deploys are
happening via operator-manual commands from the app repo's instructions
("until the deploy Lambda is in place"), the deploy path doesn't run through
the ops repo, so it accumulates neither content nor habit. The fix is not
more discipline but rerouting: make irl-ops the *only* way to reach prod
(even if that's initially just "the runbook lives here and the deploy script
is invoked from here"), then let its D6 ownership list fill in as launch
approaches — per-env config register, deploy + rollback runbooks,
incident-notes convention, alarm definitions, its own backlog. IRL's C3
promotion should be gated on irl-ops being genuinely load-bearing.

### Convergences worth preserving as-is

Three practices evolved independently in near-identical form and should be
canonized with their existing wording: same-commit backlog/doc updates
(allegro + IRL), "checked backlog entries describe what actually shipped"
(IRL's articulation), and OIDC-no-stored-keys deploys (template + IRL). One
divergence to resolve deliberately: `.claude/memory` design memos (allegro)
vs `docs/` design notes (IRL) — recommend IRL's location, allegro's
memory-index and feedback-file conventions.

---

## 6. Suggested shape of the methodology repo

```
majodali/methodology/
  CLAUDE.md                # bootstrap pointer only (A0/A1) — mirrors docs/
  README.md
  docs/
    methodology.md         # §1–§4 of this document, refined — the authority
    working-agreement.md   # §2.B in full, portable form
    ops-ownership.md       # D6 split criteria + anti-languish rule, expanded
    profiles/
      web-app.md  language-platform.md  library.md  exploration.md  ops.md
    backlog.md  decisions.md  plans/   # the methodology governs itself
  skeletons/               # copyable starting files
    CLAUDE.md  docs/backlog.md  docs/decisions.md  docs/open-risks.md
    docs/radar.md  docs/hypotheses.md  docs/plans/TEMPLATE.md
    pull_request_template.md  ci-verify.yml
```

The plan template (`docs/plans/TEMPLATE.md`) encodes A7's hygiene contract in
its structure: outcome-named file, status line (`active | superseded by X
because Y | closed — see backlog`), and a standing instruction that unmarked
content is a live claim of current intent.

Adoption path: (1) stand up the repo with the working agreement + skeletons;
(2) add allegro CI (the one urgent gap); (3) add classification blocks +
deviation notes to each project's CLAUDE.md; (4) template ships the skeletons;
(5) restructure allegro's CLAUDE.md when convenient; (6) bind IRL's C3
promotion checklist to launch.
