# Backlog

The single source of progress truth for this repo
([K-003](rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth));
entries update in the same commit as the work they describe
([W-003](rules/working-agreement.md#w-003--documentation-moves-in-the-same-commit-as-the-work)).

## Completed

- [x] **Corpus import** — split *Constitution & Vocabulary draft v0.7*
  into [constitution.md](constitution.md) (with Article 11, the approved
  adoption edit), [vocabulary.md](vocabulary.md), and
  [rules/](rules/README.md) (K-001–K-009, W-001–W-007, M-001–M-003,
  S-001–S-002, one file per section); imported proposal v0.2 as
  [practices.md](practices.md); rewrote all draft-relative links
  repo-relative and verified every relative link and anchor resolves
  (ad-hoc script — transitional, Risk R2); kept the draft changelogs as
  pre-1.0 history.
- [x] **Methodology Classification and Portfolio register** (draft open
  item 6) — first Classification ever written:
  [classification.md](classification.md), `methodology-corpus` / C1 / S0
  / none-local, pinned 1.0.0; Binding block in `CLAUDE.md`;
  [Portfolio register](registers/portfolio.md) seeded from a full
  account census (19 repositories, all implicit C0 except this repo).
  **Census confirmation by the owner is pending at the chunk-1 gate.**
- [x] **Skeletons** — copyable starting files under
  [skeletons/](../skeletons/) per [practices §6](practices.md), scoped
  to the kickoff list: minimal `CLAUDE.md` (Binding block + pointers,
  K-002), `docs/classification.md`, `docs/backlog.md`,
  `docs/decisions.md`, `docs/open-risks.md`, `docs/plans/TEMPLATE.md`
  (encoding the K-007 status-line contract), `pull_request_template.md`
  (D2), `ci-verify.yml` (D3). Radar/hypothesis skeletons from §6's
  sketch deliberately not created (K-005: no empty ceremony ahead of
  need; kickoff list governs).
- [x] **Census confirmed and methodology-tools cross-registered** —
  owner confirmed the census at the chunk-1 gate (2026-08-18), ruling
  the three unobservable practices-§1.1 examples disregarded;
  [methodology-tools](https://github.com/majodali/methodology-tools)
  bootstrapped under v1.0.0 (component/library, C1, S0, package
  registry; founding plan imported, status draft) and its
  [Portfolio entry](registers/portfolio.md) updated from implicit C0 to
  its declared summary (M-001).

- [x] **Bootstrap merged** — PR #1 merged to `main` (2026-08-18) and
  `main` made the default branch. Cross-repo links from
  methodology-tools now resolve.

- [x] **v1.0.0 released** — owner created the annotated tag `v1.0.0`
  on `main` (2026-08-18) and deleted the merged single-use bootstrap
  branch (W-006). Owner rulings adopted as standing process: version
  tags are created by the owner after PR review (the release ceremony),
  and `main` accepts pushes from the owner only — recorded in the
  [Classification's process records](classification.md).

- [x] **Amendment & release process** (amendment; the merge is
  acceptance) — Article 8 amended: interim adjudication minted and the
  release mechanics homed in [release-process.md](release-process.md)
  (Level 2, amendable); [Release register](releases.md) created
  (Keep-a-Changelog shape), seeded with the v1.0.0 section and
  Unreleased entries for this amendment and the audit-log amendment;
  vocabulary: *Interim adjudication*, *Release*, *Release register*,
  *Editorial change*;
  [M-004](rules/mirrors.md#m-004--amendment-prs-carry-their-release-register-entry)
  added. Suggested by the adjudication questions around
  [PR #3](https://github.com/majodali/methodology/pull/3).
- [x] **Audit-log register** (amendment,
  [PR #3](https://github.com/majodali/methodology/pull/3), accepted
  2026-08-20) — [audits.md](audits.md) created, seeded with the
  bootstrap link-check entry; *Audit log* added to the vocabulary's
  Register subtypes. Motivating instance:
  [methodology-tools chunk 1](https://github.com/majodali/methodology-tools/pull/1),
  whose `mtool status` delta-ratio needs a machine-readable
  last-semantic-audit time.
- [x] **v1.1.0 cut** — release PR retitled Unreleased to
  [*v1.1.0 — 2026-08-20*](releases.md): the amendment & release
  process (PR #4) and the audit-log register (PR #3), both accepted at
  the first interim adjudications; the owner creates the annotated tag
  `v1.1.0` after merging (release ceremony). Migration notes: none for
  either amendment — migrations are pin bumps only.

- [x] **Migrated to 1.1.0** — v1.1.0 tagged by the owner 2026-08-20;
  migration PR bumped the [Classification](classification.md) pin and
  the `CLAUDE.md` Binding block, and refreshed this repo's
  [Portfolio row](registers/portfolio.md) (v1.1.0 migration notes:
  none, so the pin bump is the whole migration — release process
  step 5). methodology-tools migrates by its own PR.

- [x] **Risk R2 closed** — link-integrity tooling landed
  (`mtool links check`,
  [methodology-tools chunk 2](https://github.com/majodali/methodology-tools/pull/4));
  first tool-driven run over this tree logged in the
  [Audit log](audits.md) (144 relative links, no findings), the ad-hoc
  bootstrap script retired. Transitional entries R1, R3, R4 remain
  open, so Article 11 stands (its deletion review waits for an empty
  transitional set).

- [x] **Risk R1 closed** — form-audit tooling landed
  (`mtool audit form` + `mtool hooks install`,
  [methodology-tools chunk 3](https://github.com/majodali/methodology-tools/pull/5)).
  This repo's first tool-driven form audit logged in the
  [Audit log](audits.md) (no findings); the first portfolio-wide run
  audited allegro, in-real-life, the template, and both ops repos at
  their declared levels — allegro's findings match its own
  adoption-transition notes, in-real-life has one W-007 gap (no
  README), the implicit-C0 repos audit clean. Portfolio rows for
  allegro and in-real-life refreshed from their observed declarations.
  R3 and R4 remain open, so Article 11 stands.

- [x] **Audit delivery process** (amendment; the merge is acceptance)
  — [audit-process.md](audit-process.md) created (Level 2): audit
  results become machine-comparable finding fingerprints
  (rule/severity/file over violations + warnings; info and message
  text excluded; corpus version recorded, not compared), compared
  against the project's own Audit log, delivered by PR exactly on
  transitions (first delivery creates the register); portfolio sweeps
  recorded centrally in this repo's [Audit log](audits.md). Article 9
  pointer added; vocabulary: *Audit delivery*; Audit-log entry format
  extended; transitional [Risk R5](open-risks.md) opened (manual
  delivery until `mtool` compare-and-deliver, chunk 4).
  Owner-designed 2026-08-21; evidencing instance: the chunk-3 gate
  findings that never reached their projects.

- [x] **v1.2.0 cut** — release PR retitled Unreleased to
  [*v1.2.0 — 2026-08-21*](releases.md): the form-audit delta-scope
  calibration (PR #9) and the audit delivery process (PR #12); the
  owner creates the annotated tag `v1.2.0` after merging (release
  ceremony). Migration notes: none for either amendment — migrations
  are pin bumps only.

- [x] **Migrated to 1.2.0** — v1.2.0 tagged by the owner 2026-08-21;
  pin, Binding block, and Portfolio row bumped (migration notes: none,
  so the pin bump is the whole migration — release process step 5).
  methodology-tools migrates by its own PR.

- [x] **Risks R3 and R5 closed** — census and audit-delivery tooling
  landed
  ([methodology-tools chunk 4](https://github.com/majodali/methodology-tools/pull/7)):
  `mtool census` reconciled all 19 observed repos against the
  [Portfolio register](registers/portfolio.md) on its first run
  (completeness verified; allegro's stale pin refreshed per its drift
  proposal; 12 implicit-C0 spot-check candidates queued for the review
  round), and `mtool audit deliver` mechanizes the
  [audit process](audit-process.md) fingerprint comparison. R4 (links
  move, chunk 5) is the sole remaining transitional entry — Article
  11's deletion review arms when it closes.

- [x] **Links-move external-reference limitation** (amendment; the
  merge is acceptance) — Article 10's tombstone bullet records that,
  until the census maintains an external-reference index, whether a
  document is externally referenced is operator-supplied knowledge
  (`mtool links move` surfaces the duty, `--tombstone` discharges it);
  transitional [Risk R6](open-risks.md) opened. The founding tools
  plan's second promised amendment
  ([methodology-tools chunk 5](https://github.com/majodali/methodology-tools/pull/8)).

- [x] **Risk R4 closed** — move/rename tooling landed
  (`mtool links move`,
  [methodology-tools chunk 5](https://github.com/majodali/methodology-tools/pull/8));
  the founding tools plan is closed (all five chunks delivered), and
  every bootstrap transitional entry (R1–R5) is now closed. R6 (the
  links-move limitation) is the sole remaining transitional entry, so
  Article 11 stands until the census external-reference index lands.

- [x] **Project families** (amendment; the merge is acceptance) —
  multi-repo grouping designed and minted: the optional **Family**
  Classification field (lead | member; omission default none; outside
  the Article 4 decidability basis) and the *Project family* term —
  family cohesion via the lead as documentation home, family-shared
  constructs adopted by citation, per-member Classifications never
  merged, census symmetry checking, Portfolio Families section. This
  repo declares lead of the `methodology` family (members:
  methodology-tools, project-orchestrator, serverless-web-app-template
  — declarations land per repo). Ratified 2026-08-24; resolves the
  multi-repo Backlog item.

- [x] **Template type and Q-001** (amendment; the merge is
  acceptance) — the `template` type minted (a project whose shipped
  content instantiates derived projects) and the Q- section opened
  with [Q-001](rules/quality.md#q-001--template-scaffolds-stay-compliant):
  a template's scaffold MUST instantiate to a form-clean project at
  the tier the template declares for derivatives — mechanically
  checkable via the classify/audit loop. The template joins the
  `methodology` family (owner ruling 2026-08-24); its own type
  adoption happens in its repo. Resolves the template-burden Backlog
  item.

- [x] **Custom definitions by citation** (amendment; the merge is
  acceptance) — Article 7 names the citation form: a Custom
  definitions section MAY define a type by reference to another
  project's published definition (family lead or process project),
  which stays authoritative; convergent citations remain
  standardization candidates. Named instance: project-orchestrator's
  managed-project enrollment (*Plan register* / *Cost log* adopted by
  citing its process spec). Resolves the orchestrator-relationship
  question: norms (methodology) / enforcement (methodology-tools) /
  execution (project-orchestrator), all in the `methodology` family.

- [x] **v1.3.0 cut** — release PR retitled Unreleased to
  [*v1.3.0 — 2026-08-25*](releases.md): the links-move
  external-reference limitation (PR #16), project families (PR #19),
  template type and Q-001 (PR #20), and custom definitions by citation
  (PR #21); the owner creates the annotated tag `v1.3.0` after merging
  (release ceremony). Migration notes: none for all four — migrations
  are pin bumps only.

- [x] **Migrated to 1.3.0** — v1.3.0 tagged by the owner 2026-08-25;
  pin, Binding block, and Portfolio row bumped (migration notes: none
  for all four amendments, so the pin bump is the whole migration —
  release process step 5). Family-declaration PRs go out per repo in
  the same round: methodology-tools, project-orchestrator, and
  serverless-web-app-template each bump their pin and declare
  `Family: methodology (member)`; in-real-life declares lead with
  ops/org as members; the template's `type: template` adoption is
  proposed in its own PR. Portfolio rows refresh as each merges
  (M-001).

- [x] **Portfolio refreshed after the v1.3.0 adoption round** — all
  seven follow-up PRs merged 2026-08-25 (methodology #23,
  methodology-tools #9, project-orchestrator #1,
  serverless-web-app-template #2, in-real-life #66, in-real-life-ops
  #18, in-real-life-org #13); the
  [Portfolio register](registers/portfolio.md) rows refreshed from the
  observed declarations (M-001/M-002): both family compositions fully
  declared, the template's first Classification replaces its
  implicit-C0 row (`template` type, Q-001 in play), pins now 1.3.0
  across both families (allegro observed at 1.2.0 — its own migration
  timing). Verified by `mtool census` over the eight merged checkouts:
  no summary drift; enumeration unverified this run (no API access —
  known limitation) and the 12 implicit-C0 spot-check candidates stand.
  Census-side family-symmetry checking is queued in methodology-tools.

- [x] **Prose & presentation rules** (amendment; the merge is
  acceptance) — [style guide](style.md) created and the P- section
  opened ([P-001](rules/prose.md)–P-006): reference-first structure,
  one idea per sentence, bold as structure only, citations with
  names, content-stating headers, registers as uniform rows; rule
  bodies gain labeled Statement/Rationale/Exceptions fields. Base
  guides adopted by citation: Diátaxis, Google developer style.
  Suggested by the owner 2026-08-30; evidence from the same day's
  documentation review across all eight governed checkouts.

- [x] **Reports and supersession rules** (amendment; the merge is
  acceptance) — W-008 (reports map their deliverables): delivery
  reports separate restatement from novelty and close with explicit
  asks; K-010 (superseded content is never silently readable) and
  K-011 (found contradictions are marked, not routed around):
  decisions propagate in the same deliverable or leave greppable
  supersession markers, bounded by review rounds. The
  [style guide](style.md) gains the report contract, the marker
  format, and the named information-lifecycle concept.
  Owner-designed 2026-08-30, same conversation as the P- rules.

- [x] **Review-round cadence resolved** (amendment; the merge is
  acceptance) — Article 8's calendar floor ("at least quarterly")
  replaced by two cycle-based floors: consecutive rounds at most N
  minor releases apart, and parked items adjudicated within N minor
  releases of parking; a dormant corpus with an empty review queue
  owes no round. N = 3 recorded in the
  [process records](classification.md). Owner-designed 2026-08-30
  under the no-calendar-time principle; resolves draft open item 3.

- [x] **First review round held** — convened and closed 2026-08-30;
  record: [plans/review-round-1.md](plans/review-round-1.md)
  (status: closed). All nine items adjudicated, every proposal
  accepted: eleven interim adjudications confirmed; three seed
  tensions resolved by editorial Rationale notes (K-003, W-001,
  M-003); Workflow-declaration-format amendment ratified (queued
  below); semantic-audit thresholds parked to round 2 (bounded by the
  parked-item floor); spot-checks clean (workbench, graph-analysis,
  chloe-portfolio — the last previously unregistered, now a
  Portfolio row per M-001); Risk R6 stays open; editorial passes
  begin after the v1.4.0 cut. Semantic-audit and sweep entries in
  the [Audit log](audits.md) seed the delta-ratio baseline. This
  entry supersedes the plan (K-007).

- [x] **Workflow declaration format** (amendment; the merge is
  acceptance) — the vocabulary's *Workflow* term now defines the
  required minimum declaration format: `stages: a → b → c;
  live = <stage>; backlog default: checked ⇒ <s1>, unchecked ⇒ <s2>`,
  with explicit `stage:` markers for deviating entries. Ratified at
  review round 1 from the anatomy the three live declarations
  (allegro, in-real-life, in-real-life-ops) converged on; `deployed`
  becomes derivable from a parseable declaration; pre-format
  declarations reword editorially at their own pace, carrying an
  info finding meanwhile. Tool-side parsing is methodology-tools
  work, queued there. Resolves draft open item 4.

- [x] **v1.4.0 cut** — release PR retitled Unreleased to
  [*v1.4.0 — 2026-08-30*](releases.md): prose & presentation rules
  (PR #25), reports and supersession (PR #26), review-round cadence
  in release cycles (PR #27, constitutional), and the Workflow
  declaration format (PR #30); review round 1 held before the cut per
  the new floors. The owner creates the annotated tag `v1.4.0` after
  merging (release ceremony). Migration notes: none mandatory for all
  four — migrations are pin bumps; editorial passes and Workflow
  rewording are scheduled work on each project's own pace. The Audit
  log's sweep entry now names the raised delivery PRs (allegro #41,
  in-real-life #69).

- [x] **Migrated to 1.4.0** — v1.4.0 tagged by the owner 2026-08-30;
  pin, Binding block, and Portfolio row bumped (migration notes: none
  mandatory, so the pin bump is the whole migration — release process
  step 5). Family members migrate by their own PRs in the same round.

- [x] **Portfolio refreshed after the 1.4.0 migration round** — all
  seven migration PRs merged 2026-08-30; member rows moved to pinned
  1.4.0. project-orchestrator-service registered on owner instruction
  (M-001): C1 / S1 / backend-service / serverless-aws, pinned 1.4.0,
  `methodology` family member since its own 2026-08-27 bootstrap —
  the family's default-join ruling working unprompted. Its audit is
  clean after a scanner-precision fix in methodology-tools (S-001
  key pattern now requires a base64 body; two false positives were
  the motivating instance). allegro's stranded v1.4.0 migration was
  found on a dead branch, landed by cherry-pick (allegro PR #43), and
  its row reads 1.4.0. Census over nine checkouts: no drift.

- [x] **Delegated-work vocabulary** (amendment; the merge is
  acceptance) — *Delegation* (delegating agent / delegated agent) and
  *Report audience* (principal / agent) added to the vocabulary's
  defined terms. First amendment drafted by another project
  (project-orchestrator node P1-N015) and hand-carried here; the two
  terms serve its sibling proposals for W-008 and K-011.

- [x] **Report rule scoped by audience** (amendment; the merge is
  acceptance) — W-008 and the [style guide](style.md)'s report
  contract now scope by *report audience* rather than by "chat" and
  "delivers a written artifact": principal-addressed reports keep the
  restatement/novelty/asks shape and gain two ordering duties;
  agent-addressed reports owe status, deliverable map, and asks.
  Drafted by project-orchestrator and hand-carried; its dispatch loop
  is the evidencing instance.

- [x] **Contradiction-marking duty in nested sessions** (amendment;
  the merge is acceptance) — K-011 now names the finder as the owner
  of the marking duty at any depth of delegation, and gives a role
  forbidden to edit files a discharge: report a located finding (file,
  location, contradicted decision) in its own deliverable. Drafted by
  project-orchestrator and hand-carried; its role-contracts decision 2
  is the evidencing instance.

- [x] **K-010's converse for active documents** (amendment; the merge
  is acceptance) — unmarked content in a document designated `active`
  asserts current intent, so a passage found to contradict a recorded
  decision there is false rather than stale and MUST be corrected in
  the finding deliverable, not left under a supersession marker alone.
  Drafted by project-orchestrator and hand-carried; its founding
  plan's corrected pin claim is the evidencing instance.

- [x] **Pre-ratified chunk sequences** (amendment; the merge is
  acceptance) — W-001 gains an alternative to the per-chunk gate: a
  human MAY approve a chunk sequence once, before the first chunk, and
  the agent lands the chunks without stopping between them. Four stop
  conditions bound the mode — a failed check, a scope change, a chunk
  needing the human's decision, and any chunk summary carrying asks —
  and the mode is offered, never owed. Only the human pre-ratifies.
  Drafted by allegro and hand-carried; its parallel-lane experiment
  and deviation D-1 are the evidencing instance.

- [x] **Report contract cached in the Agent bootstrap** (amendment;
  the merge is acceptance) — W-008 gains a **Required bootstrap
  text** field: a verbatim block every Agent bootstrap MUST carry,
  covering the three report parts in order, the state-an-empty-part
  duty, and the sentence-level style duties (short direct sentences,
  no rhetorical padding, named citations). The block is a cache;
  W-008, the P- rules and the [style guide](style.md) stay the
  authority, and audits compare each bootstrap's copy against it.
  This repo's `CLAUDE.md` and
  [skeletons/CLAUDE.md](../skeletons/CLAUDE.md) carry it in the same
  commit. Owner-observed instance: report conformance decaying across
  high-traffic sessions, 2026-09-01.

## Upcoming
- [ ] **Editorial passes for existing documents** — restyle per the
  [style guide](style.md), highest-traffic reference documents first
  (constitution, vocabulary, rules, classifications); each pass is an
  editorial change, no per-document amendment.
- [ ] **Style checks in `mtool audit`** — mechanical subset of the P-
  rules as warnings: sentence-length statistics, unnamed identifiers
  and section references, register row length; plus the W-008
  bootstrap-cache drift check (compare each project's copied block
  against the rule's own). Tools-repo work.
- [ ] **Formal project models (post-Allegro)** — owner horizon,
  recorded 2026-08-30: requirements, specifications, reasoning
  chains, assumptions, and dependencies as formal model nodes;
  documentation read by query and transform. Bears on how much prose
  remains and expands what audits can check. The style guide's
  structure-first decision keeps documents liftable; no construction
  ahead of need.
- [ ] **Meta-template for template projects** — a process and/or
  template for building template projects, anticipated as the family
  of templates grows (owner-raised, 2026-08-24).
- [ ] **D-/Q-/O- rule extraction pass** — extract the delivery,
  quality, and operations disciplines from
  [practices.md](practices.md) so form audits can see the gap
  analysis's delivery findings (no CI, no PR template, …); each rule
  needs its live motivating instance (Article 6). Deferred out of
  tools chunk 3 by owner ruling, 2026-08-20.
- [ ] ~~**Form-audit delta scope**~~ **calibration resolved**
  (amendment; this entry merges with its PR): per-file content checks
  delta-scoped, repo-wide invariants full-tree on every audit —
  Article 9's open parenthetical replaced, the deletion blind spot
  closed by construction. Evidencing instance: `mtool audit form`
  (draft open item 1 done).
- [ ] **Semantic-audit auto-trigger calibration** — delta-ratio
  thresholds (initial: 50% at C2, 25% at C3) and whether delta-ratio is
  the right trigger shape at all (draft open item 2; Article 9).
  Parked to review round 2 at round 1 (unfalsifiable until first
  semantic audits exist; round 1 seeded the first baseline). The
  parked-item floor bounds this: adjudication within three minor
  releases of 2026-08-30.