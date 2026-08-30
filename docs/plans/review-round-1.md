# Review round 1 — packet and record

Status: active

Outcome under development: the first scheduled review round
([Article 8 (amendments)](../constitution.md#article-8--amendments-versions-and-migration)),
due under the cycle-based floors (three minor releases, no round
held). This document is the round's packet and becomes its record:
each agenda item carries the evidence and an Adjudication field the
owner fills. The round closes when every item is adjudicated; the
Backlog entry then supersedes this plan (K-007 — plans are
outcome-named, statused, and ruthlessly current).

Evidence date: 2026-08-30, at corpus commit f8dfa03 (v1.4.0
candidate: PRs #25, #26, #27). Assembled by the Auditor with
`mtool audit semantic`, a portfolio form-audit sweep, `mtool census`,
and `mtool audit deliver` over the eight governed checkouts.

## Portfolio state at assembly

Form audits at each project's declared level, corpus at the v1.4.0
candidate:

| Project | Result |
|---|---|
| methodology | clean (24 rules in play) |
| methodology-tools | clean (20) |
| project-orchestrator | clean (20) |
| serverless-web-app-template | clean (21; Q-001 in play) |
| in-real-life | pass + 1 info (Workflow format — item 5) |
| in-real-life-ops | pass + 1 info (same) |
| in-real-life-org | clean (26) |
| allegro | 1 warning (1.2.0 lag — its own migration timing) + 1 info (same) |

Census: register and checkouts reconcile with no drift; account
enumeration unverified (no API access from the audit environment);
the twelve implicit-C0 rows remain spot-check candidates (item 6).

## Agenda

### 1 — Interim adjudications since v1.0.0 (Article 8 re-examination)

Article 8 requires every scheduled round to re-examine the interim
decisions taken since the last round. All eleven accepted amendments
were interim-adjudicated; none has a recorded reversal candidate. The
duty here is confirmation, not re-litigation.

- v1.1.0: amendment & release process (#4); audit-log register (#3).
- v1.2.0: form-audit delta-scope calibration (#9); audit delivery
  process (#12).
- v1.3.0: links-move limitation (#16); project families (#19);
  template type and Q-001 (#20); custom definitions by citation (#21).
- v1.4.0 candidate: prose & presentation rules (#25); reports and
  supersession (#26); review-round cadence in release cycles (#27).

**Evidence**: all eleven are exercised — three releases adopted
portfolio-wide, families declared, the template classified, the P-
and lifecycle rules already binding this packet's own prose.

**Adjudication**: _pending owner_.

### 2 — Seed tension: K-003's stage-designation clause (mirror or duplication?)

[K-003 (the Backlog is the single source of progress truth)](../rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth)
requires stage designations on Backlog entries where a Workflow is
declared; [Article 4 (applicability)](../constitution.md#article-4--applicability-then-precedence)'s
declaration-accuracy duty already binds those designations.

**Evidence**: no defect observed in three Workflow-declaring projects;
the overlap has cost nothing yet.

**Proposal**: keep K-003's clause as a deliberate mirror; add one
sentence to K-003's Rationale naming Article 4 as the source it
mirrors. Editorial change.

**Adjudication**: _pending owner_.

### 3 — Seed tension: W-001's "larger arcs" threshold is undefined

[W-001 (two delivery modes, human-gated)](../rules/working-agreement.md#w-001--two-delivery-modes-human-gated)
distinguishes chunk-gated arcs from single deliverables without
defining where an arc begins.

**Evidence**: no dispute has arisen in any governed session; owners
have gated by judgment.

**Proposal**: leave undefined; record in W-001's Rationale that the
threshold is deliberate owner judgment, not a gap. Editorial change.
Mint a definition only when a real dispute evidences the need
(Article 6 — rules need motivating instances).

**Adjudication**: _pending owner_.

### 4 — Seed tension: M-003's subject is the process, not a repo

[M-003 (amendment PRs receive traceability review)](../rules/mirrors.md#m-003--amendment-prs-receive-traceability-review)
tags `[type: methodology-corpus]` to bind a process duty to the repo
hosting it.

**Evidence**: the tag works; every amendment PR this cycle received
its review. A process-scoped applicability notion would be new
Article 4 machinery with one consumer.

**Proposal**: keep the repo-scoped tag; note the modeling choice in
M-003's Rationale. Editorial change. Revisit only if a second
process-scoped rule appears — or when the formal project model
(Backlog) gives processes first-class identity.

**Adjudication**: _pending owner_.

### 5 — Calibration: Workflow declaration format (draft open item 4)

The Classification's Workflow field has no defined format, so
`deployed` cannot be derived mechanically and every audit of a
Workflow-declaring project carries the same info finding.

**Evidence**: three live formats have converged on the same anatomy —
allegro, in-real-life, and in-real-life-ops each declare ordered
stages, one designated live stage, and a Backlog default rule
(checked ⇒ stage X, unchecked ⇒ stage Y, explicit `stage:` markers
for exceptions).

**Proposal**: standardize that anatomy as the required minimum —
`stages: a → b → c; live = <stage>; backlog default: checked ⇒ <s1>,
unchecked ⇒ <s2>` — as a v1.4.0 amendment; the three projects already
comply in substance and reword at their own pace (editorial in each).
`deployed` derives from "the live stage exists and is reachable per
the declaration". This is the round's one substantive amendment
proposal.

**Adjudication**: _pending owner_.

### 6 — Calibration: semantic-audit auto-trigger (draft open item 2)

Initial thresholds (delta-ratio 50% at C2, 25% at C3) have never
fired: no C2 project has recorded a semantic audit, so delta-ratio
reports "no semantic audit recorded yet" everywhere.

**Evidence**: zero firings; the trigger's input (a recorded semantic
baseline) does not yet exist in any C2 project.

**Proposal**: leave thresholds unchanged; they are unfalsifiable
until first semantic audits exist. Park to the next round (the
parked-item floor now bounds this: adjudication within three minor
releases). Seed the baseline by recording this round's semantic audit
of the methodology repo in its Audit log.

**Adjudication**: _pending owner_.

### 7 — Spot-checks: twelve implicit-C0 repositories

The census lists twelve registered implicit-C0 repositories with no
checkout to verify their C0-baseline compliance (W-007 README,
S-001/S-002 secret hygiene).

**Evidence**: none observable — the audit environment has no access
to these repositories.

**Proposal**: sample three by owner's pick (suggested: mc-tools,
workbench, and the most recently pushed of the rest), added to a
session's repo scope for baseline checks; the remaining nine stay
registered as candidates. Archived `open-context-v1` is exempt from
sampling (dormant, historical).

**Adjudication**: _pending owner (sample choice, or defer)_.

### 8 — Transitional risk R6 and Article 11

[Risk R6](../open-risks.md) (links-move external-reference
limitation) is the sole open transitional entry; Article 11's
deletion review arms only when the transitional set is empty.

**Evidence**: the census external-reference index that would close R6
is queued tools work; the operator-supplied duty is documented and
exercised.

**Proposal**: keep R6 open; Article 11 stands. No action.

**Adjudication**: _pending owner_.

### 9 — Editorial-pass schedule (P- rules migration)

The style guide requires per-document editorial passes for existing
documents, highest-traffic first.

**Proposal**: order — constitution, vocabulary, rules corpus,
release/audit processes, this repo's registers, then per-project
classifications on their own schedules. One pass per PR, each an
editorial change. Begin after the v1.4.0 cut so passes restyle
stable text.

**Adjudication**: _pending owner_.

## Round follow-ups (armed by this packet, regardless of adjudications)

- Audit deliveries due on transitions found by this sweep: allegro
  (new fingerprint: the 1.3.0-lag warning) and in-real-life (clean
  transition from its W-007 baseline). Delivery PRs after the round.
- Record this round's semantic audit of the methodology repo in the
  [Audit log](../audits.md) at round close (Article 9 binds the
  methodology to a semantic audit every round; also seeds item 6's
  baseline).
- v1.4.0 cut after adjudications land (the round precedes the cut,
  per the cadence floors).
