# Vision for the methodology and the portfolio

Status: reviewed (v1, count 2 readable at round 3 on 2026-10-29 after the chunk-1 corrections; count 1 ended at the limit, meta-review delivered as case 009; meta-review of count 2 pending)

## Reader and purpose

Reader: RD-4, a fresh agent session described in the [reader catalog](style.md#readers).
The reader has the methodology and the project's documents and does not have the conversation that produced them.
Purpose: this document states the vision the portfolio builds toward.
The document gives the direction set, the decisions taken, what the portfolio already provides, the gaps a roadmap closes and the open decisions.

## The direction

Each sentence of this section states the target state the owner decided on 2026-10-28.
Every project in the portfolio that benefits uses the [project-orchestrator](https://github.com/majodali/project-orchestrator), adopted one project at a time.
Each project keeps a comprehensive plan in the project's repository, kept current by agents as the agents perform each task.
An agent queries the [project-orchestrator-service](https://github.com/majodali/project-orchestrator-service) for available tasks and claims a task.
The agent updates the plan when closing the task.
An agent performing a task from a surface with a repository clone changes the project's repository directly.
An agent is [enlisted](https://github.com/majodali/project-orchestrator-service/blob/main/docs/mcp-enlistment.md) from any Claude surface: Claude Code web, desktop or CLI, Claude Duet, the Claude web interface or Claude Mobile.
An agent is also delegated to by another agent.
Projects and agents using the project-orchestrator standardize agent instructions across planning, documentation, communication and engineering practice.
When [Allegro](https://github.com/majodali/allegro) provides modeling, project information and methodology practices are modeled in Allegro.
Modeling in Allegro gives type checking, validation, constraint checking and defined model operations.
An evolving standard set of models covers specification and design, planning, engineering, documentation and communication, and operations, serving every project.
Each project's [planning/execution model](vocabulary.md#def-planning-execution-model) is the primary source of progress and status truth.
The project-orchestrator-service provides a [web view](vocabulary.md#def-web-view) of each project's planning/execution model.
The web view is the primary way a human sees status, drills into subtasks, code and test results, and makes scheduling and delegation decisions.
Projects use a literate style in which planning, specification, documentation and implementation models are tightly integrated.
A new reader gets up to speed by reading the project like a book.
New functionality is defined by the literate style and [specification-by-example](vocabulary.md#def-specification-by-example) as far as possible.
Projects are implemented in larger [streams](vocabulary.md#def-stream) of autonomous work that focus on outcomes and risks rather than a [chunk gate](vocabulary.md#def-chunk-gate) on every chunk.
[Convergence](vocabulary.md#def-convergence) is handled by evolving formal models, evolving agent instructions and adversarial agent review.

## Decisions taken on 2026-10-28

The vision is built by an iterative roadmap.
The owner amends a methodology rule such as [K-003](rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth), the Backlog rule, at the point in the roadmap where a project needs the change.
The [Backlog](rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth)'s remaining jobs, namely the implementation map and the list of what is next, become [renderings](intermediate-representation.md#rendering-rule) of the [planning/execution model](vocabulary.md#def-planning-execution-model).
The Backlog becomes a rendering per project, as each project adopts the project-orchestrator.
On 2026-10-28 the owner named completing service [chunk 1](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md) as the next step.
The Plan register's record of chunk 1 done, dated 2026-09-16, reached main on 2026-10-29 through [pull request 13](https://github.com/majodali/project-orchestrator/pull/13) of the project-orchestrator.
The owner and the [reasoning role](vocabulary.md#def-reasoning-role) review the service's current state after chunk 1.
The owner decides changes to the service's features or roadmap where the vision requires.
The owner adds a project to the service when adoption benefits the project.
No project in the portfolio is known that should not use the service.
Eventually Allegro's approach (its planning DSL and process documents) and the project-orchestrator's approach merge into one model.
The merged model lets Allegro adopt the project-orchestrator.
After the [pilot](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md), the owner decides how and when Allegro's approach and the project-orchestrator's approach merge.
The [plan model](https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-model.md), the [IR](vocabulary.md#def-intermediate-representation) and the role definitions stay documents until Allegro models them.
The owner and the reasoning role construct nothing ahead of need.
The vision document lives in the methodology repository as docs/vision.md.
Before the vision document is rendered, the reasoning role drafts the document's IR for the owner to edit.
The owner names the first adopter by benefit before the pilot starts.
The first adopter's plan is the [pilot](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md).
The roadmap document, not this vision, places the pilot relative to the task-pull loop.

## Decisions taken on 2026-10-29

The owner named [methodology-tools](https://github.com/majodali/methodology-tools) the first adopter on 2026-10-29.
The project-orchestrator adopts the service by construction when service [chunk 5](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md) moves the orchestrator's own orchestration onto the service.
The project-orchestrator's adoption is not the pilot.

## What the portfolio already provides

The [plan model](https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-model.md) defines a project's plan as a tree of nodes with seven stages.
A node is specified on the way down the tree and verified on the way up.
In the plan model a feature is its validation: the set of functional tests that constitute the feature.
The service reads plan state from git.
The service validates the plan-state updates a session commits.
Node P2-N010, plan-state update with an [advisory lease](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md), is done in the [Plan register](https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-register.md).
Role definitions live once in the [orchestrator plugin](https://github.com/majodali/project-orchestrator/blob/main/plugin/README.md).
A script mirrors the role definitions into projects and checks the copies match the plugin.
The methodology supplies the rules.
The project-orchestrator supplies the roles that apply the rules.
[Dispatch](https://github.com/majodali/project-orchestrator/blob/main/docs/process/dispatch.md) has approved scope as the hard boundary.
The owner may attach a task or token budget when granting scope.
The [IR](vocabulary.md#def-intermediate-representation), the [claims check](intermediate-representation.md#stranger-rounds), [same-instance confirmation](intermediate-representation.md#stranger-rounds) and the four [meta-review signals](vocabulary.md#def-meta-review-signal) are the [convergence](vocabulary.md#def-convergence) machinery for prose.
Allegro's book is the portfolio's one literate project, developed only as far as Allegro needed.
Allegro's [planning DSL](https://github.com/majodali/allegro/blob/main/docs/book/vivace/planning-dsl.md) exists as Allegro's first [Vivace](https://github.com/majodali/allegro/blob/main/docs/book/vision.md) domain model.
The planning DSL is demonstrable at [rung 3](https://github.com/majodali/allegro/blob/main/docs/plans/release-track.md) of Allegro's demo ladder.
The planning DSL models a plan as a directed acyclic graph of outcomes.
The service stays a [projection](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md) of git, which remains authoritative.
The service spawns no agents on the server.
The [task-pull loop](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md) is the standing substitute for server-side agent spawning.
Today [K-003](rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth), the Backlog rule, makes the Backlog the single source of progress truth.
The orchestrator's [founding ruling 1](https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-model.md#relationship-to-the-backlog-k-003) keeps the Plan register and the Backlog in sync.
Adversarial review is effective.
Adversarial review has low efficiency until formal models and processes keep the review convergent.

## Gaps the roadmap closes

The [plan model](https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-model.md) and Allegro's [planning DSL](https://github.com/majodali/allegro/blob/main/docs/book/vivace/planning-dsl.md) hold two plan models: a tree with seven stages, a graph of outcomes.
The merged model of Allegro's approach and the project-orchestrator's approach combines the two plan models.
Allegro's planning DSL demo may not match the project-orchestrator's plan model.
The [dispatch](https://github.com/majodali/project-orchestrator/blob/main/docs/process/dispatch.md) loop stops at a [stream](vocabulary.md#def-stream)'s boundary: a gate, an empty actionable set, a blocked task or exhausted scope.
No stop signal exists inside a stream.
Stop signals inside a stream take the [meta-review signals](vocabulary.md#def-meta-review-signal)' shape: mechanical where a count exists, a wording match for a hand check otherwise.
Before a stream starts, the owner approves the stream as scope, budget and accepted risks.
The dispatch loop then runs until a stop signal or the stream's end.
The [reasoning role](vocabulary.md#def-reasoning-role) running a stream keeps a running record of findings and the confidence in each finding's fix.
Today the [convergence](vocabulary.md#def-convergence) machinery applies to prose only.
Plans and specifications therefore have no [stranger](vocabulary.md#def-stranger).
The stranger extends to plans and specifications.
A fresh reviewer restates the plan from the [Plan register](https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-register.md) and each node's [verification criteria](https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-model.md#the-node-lifecycle) before reading the plan's reasoning.
A mismatch between the fresh reviewer's restatement and the plan is a finding.
The [rounds-until-readable rule](intermediate-representation.md#stranger-rounds) and the meta-review signals carry over to plan review unchanged.
Before the web view drills to code and test results, the [reasoning role](vocabulary.md#def-reasoning-role) amends the plan model to record where each node's verification evidence lands.
Today the plan model records verification criteria only, not where the evidence lands.
No document type holds specification, examples and implementation links together.
Allegro's [conceptual-model proposal](https://github.com/majodali/allegro/blob/main/docs/plans/conceptual-model-methodology-delta.md) is the closest existing draft of a document type holding specification, examples and implementation links together.
The first orchestrated project is the second project the conceptual-model proposal waits for.
Standardized agent instructions across projects conflict with Allegro's own process documents until Allegro's approach and the project-orchestrator's approach merge.
The web view reads from commits only.
[Enlistment](https://github.com/majodali/project-orchestrator-service/blob/main/docs/mcp-enlistment.md) today is a `.mcp.json` in the repository clone.
Only Claude Code surfaces read a repository's `.mcp.json`.
Today a [surface without a repository clone](vocabulary.md#def-surface-without-a-repository-clone) cannot reach the service.
The route for a surface without a repository clone is a [remote MCP connector](vocabulary.md#def-remote-mcp-connector).
The service does not offer a remote MCP connector today.
Today a surface without a repository clone cannot make the git commit the service expects from the session.
The write model, decision 3 of the [service skeleton plan](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/p2-n002-service-skeleton.md) for node P2-N002, service skeleton and plan state, makes the session git's only writer.
The owner kept the write model at the review of the service on 2026-10-29.
Surfaces without a repository clone receive read, question and delegation tools through a remote MCP connector, in a node placed after the pilot.
The literate style, every project as a book, is roadmap work beyond what Allegro's book settled.

## First steps

Node P2-N010 of service [chunk 1](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md), plan-state update under the [advisory lease](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md), is done.
Node P2-N011, degrade to git-only with enlistment documentation, reached done on 2026-09-07.
Service chunk 1 closed on 2026-09-16, with the plan-state update and the degrade to git-only done.
Now that chunk 1 has closed, the [task-pull loop](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md) comes before [topics](https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md).
The [web view](vocabulary.md#def-web-view)'s first version drills to node and task only.
The [reasoning role](vocabulary.md#def-reasoning-role) writes the roadmap document after the review of the service of 2026-10-29, from this vision.

## Asks

No open asks.
Done on 2026-10-29: the owner named methodology-tools the first adopter.
Done on 2026-10-28: the owner ratified this document's IR.
Done on 2026-10-28: the owner ratified the four terms planning/execution model, stream, specification-by-example and web view.
Done on 2026-10-28: the owner's ratification of this document's IR authorized the [paraphraser](vocabulary.md#def-paraphraser)'s rendering of this document.
The same ratification authorized the [stranger](vocabulary.md#def-stranger) rounds under [W-009](rules/working-agreement.md#w-009--the-methodology-corpus-writes-its-deliverables-ir-first), the IR-first rule.

<!-- render map: C1→The direction sentence 2; C2→The direction sentence 3; C3→The direction sentence 4; C96→The direction sentence 5; C80→The direction sentence 6; C4→The direction sentence 7; C70→The direction sentence 8; C5→The direction sentence 9; C6→The direction sentence 10; C81→The direction sentence 11; C7→The direction sentence 12; C8→The direction sentence 13; C9→The direction sentence 14; C10→The direction sentence 15; C11→The direction sentence 16; C12→The direction sentence 17; C13→The direction sentence 18; C14→The direction sentence 19; C15→The direction sentence 20; C17→Decisions taken on 2026-10-28 sentence 1; C18→Decisions taken on 2026-10-28 sentence 2; C19→Decisions taken on 2026-10-28 sentence 3; C20→Decisions taken on 2026-10-28 sentence 4; C21→Decisions taken on 2026-10-28 sentence 5; C103→Decisions taken on 2026-10-28 sentence 6; C22→Decisions taken on 2026-10-28 sentence 7; C79→Decisions taken on 2026-10-28 sentence 8; C23→Decisions taken on 2026-10-28 sentence 9; C24→Decisions taken on 2026-10-28 sentence 10; C25→Decisions taken on 2026-10-28 sentence 11; C83→Decisions taken on 2026-10-28 sentence 12; C26→Decisions taken on 2026-10-28 sentence 13; C27→Decisions taken on 2026-10-28 sentence 14; C89→Decisions taken on 2026-10-28 sentence 15; C28→Decisions taken on 2026-10-28 sentence 16; C77→Decisions taken on 2026-10-28 sentence 17; C57→Decisions taken on 2026-10-28 sentence 18; C84→Decisions taken on 2026-10-28 sentence 19; C85→Decisions taken on 2026-10-28 sentence 20; C99→Decisions taken on 2026-10-29 sentence 1; C100→Decisions taken on 2026-10-29 sentence 2; C101→Decisions taken on 2026-10-29 sentence 3; C29→What the portfolio already provides sentence 1; C71→What the portfolio already provides sentence 2; C30→What the portfolio already provides sentence 3; C31→What the portfolio already provides sentence 4; C105→What the portfolio already provides sentence 5; C59→What the portfolio already provides sentence 6; C32→What the portfolio already provides sentence 7; C95→What the portfolio already provides sentence 8; C33→What the portfolio already provides sentence 9; C88→What the portfolio already provides sentence 10; C34→What the portfolio already provides sentence 11; C106→What the portfolio already provides sentence 12; C35→What the portfolio already provides sentence 13; C36→What the portfolio already provides sentence 14; C37→What the portfolio already provides sentence 15; C86→What the portfolio already provides sentence 16; C87→What the portfolio already provides sentence 17; C38→What the portfolio already provides sentence 18; C39→What the portfolio already provides sentence 19; C60→What the portfolio already provides sentence 20; C40→What the portfolio already provides sentence 21; C61→What the portfolio already provides sentence 22; C16→What the portfolio already provides sentence 23; C82→What the portfolio already provides sentence 24; C41→Gaps the roadmap closes sentence 1; C42→Gaps the roadmap closes sentence 2; C72→Gaps the roadmap closes sentence 3; C43→Gaps the roadmap closes sentence 4; C62→Gaps the roadmap closes sentence 5; C44→Gaps the roadmap closes sentence 6; C73→Gaps the roadmap closes sentence 7; C74→Gaps the roadmap closes sentence 8; C46→Gaps the roadmap closes sentence 9; C47→Gaps the roadmap closes sentence 10; C94→Gaps the roadmap closes sentence 11; C48→Gaps the roadmap closes sentence 12; C75→Gaps the roadmap closes sentence 13; C76→Gaps the roadmap closes sentence 14; C49→Gaps the roadmap closes sentence 15; C50→Gaps the roadmap closes sentence 16; C63→Gaps the roadmap closes sentence 17; C51→Gaps the roadmap closes sentence 18; C64→Gaps the roadmap closes sentence 19; C52→Gaps the roadmap closes sentence 20; C53→Gaps the roadmap closes sentence 21; C54→Gaps the roadmap closes sentence 22; C65→Gaps the roadmap closes sentence 23; C92→Gaps the roadmap closes sentence 24; C66→Gaps the roadmap closes sentence 25; C90→Gaps the roadmap closes sentence 26; C93→Gaps the roadmap closes sentence 27; C67→Gaps the roadmap closes sentence 28; C69→Gaps the roadmap closes sentence 29; C104→Gaps the roadmap closes sentence 30; C102→Gaps the roadmap closes sentence 31; C68→Gaps the roadmap closes sentence 32; C97→First steps sentence 1; C98→First steps sentence 2; C55→First steps sentence 3; C56→First steps sentence 4; C78→First steps sentence 5; C58→First steps sentence 6; A3→Asks sentence 2; A1→Asks sentence 3; A2→Asks sentence 4; A4→Asks sentence 5; A4→Asks sentence 6 -->
