# IR: Vision for the methodology and the portfolio

Reader: RD-4
Purpose: document. The vision the portfolio builds toward over an iterative roadmap: the direction the owner set, the decisions already taken, what the portfolio already provides, the gaps a roadmap closes, and the decisions still open.
Status: rendered (paraphraser, 2026-10-28, disposition D2 by BP-03; ratified by the owner 2026-10-28 with the four terms; count 1 ended at the limit, round 10 not readable, round 10's fixes confirmed; round trip 96 of 96; declared 5, changed 5, surprises 0, misses 0; unratified terms 0)
Source: the owner's message of 2026-10-28 stating the vision in eight points; the reasoning role's assessment of the same day; the owner's reply of 2026-10-28 deciding four asks and agreeing the recommendations and terms; the owner's two notes of 2026-10-28 on agent surfaces and on the literate approach.
Footprint: docs/vision.ir.md; docs/vision.md; docs/vision.review.md; docs/backlog.md; docs/vocabulary.md

## Terms

T1. Plan model. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-model.md [decided: project-orchestrator process specification]

T2. Plan register. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-register.md [decided: project-orchestrator process specification]

T3. Task-pull loop. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md [decided: owner, 2026-08-26]

T4. Pilot. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md [decided: owner, 2026-08-26]

T5. Backlog. defined-at: rules/knowledge.md#k-003--the-backlog-is-the-single-source-of-progress-truth [decided: methodology K-003]

T6. Chunk gate. defined-at: vocabulary.md#def-chunk-gate [decided: methodology vocabulary]

T7. Convergence. defined-at: vocabulary.md#def-convergence [decided: owner, 2026-10-23]

T8. Stranger. defined-at: vocabulary.md#def-stranger [decided: owner, 2026-10-23]

T9. Intermediate representation (IR). defined-at: vocabulary.md#def-intermediate-representation [decided: owner, 2026-10-24]

T10. Meta-review signal. defined-at: vocabulary.md#def-meta-review-signal [decided: owner, 2026-10-27]

T11. Planning DSL. defined-at: https://github.com/majodali/allegro/blob/main/docs/book/vivace/planning-dsl.md [decided: allegro, 2026-10-25]

T12. Planning/execution model. defined-at: vocabulary.md#def-planning-execution-model [decided: owner, 2026-10-28]

T13. Stream. defined-at: vocabulary.md#def-stream [decided: owner, 2026-10-28]

T14. Specification-by-example. defined-at: vocabulary.md#def-specification-by-example [decided: owner, 2026-10-28]

T15. Web view. defined-at: vocabulary.md#def-web-view [decided: owner, 2026-10-28]

## Claims

### The direction

C1. Every project in the portfolio that benefits uses the project-orchestrator, adopted one project at a time. [decided: owner, 2026-10-28]

C2. Each project keeps a comprehensive plan in the project's repository, kept current by agents as the agents perform each task. [decided: owner, 2026-10-28]

C3. An agent queries the project-orchestrator-service for available tasks and claims a task. [decided: owner, 2026-10-28]

C96. The agent updates the plan when closing the task. [decided: owner, 2026-10-28]

C80. The agent changes the project's repository directly while performing the task. [decided: owner, 2026-10-28]

C4. An agent is enlisted from any Claude surface: Claude Code web, desktop or CLI, Claude Duet, the Claude web interface or Claude Mobile. [decided: owner, 2026-10-28]

C70. An agent is also delegated to by another agent. [decided: owner, 2026-10-28]

C5. Projects and agents using the project-orchestrator standardize agent instructions across planning, documentation, communication and engineering practice. [decided: owner, 2026-10-28]

C6. When Allegro provides modeling, project information and methodology practices are modeled in Allegro. [decided: owner, 2026-10-28]

C81. Modeling in Allegro gives type checking, validation, constraint checking and defined model operations. [decided: owner, 2026-10-28]

C7. An evolving standard set of models covers specification and design, planning, engineering, documentation and communication, and operations, serving every project. [decided: owner, 2026-10-28]

C8. Each project's planning/execution model is the primary source of progress and status truth. [decided: owner, 2026-10-28]

C9. The project-orchestrator-service provides a web view of each project's planning/execution model. [decided: owner, 2026-10-28]

C10. The web view is the primary way a human sees status, drills into subtasks, code and test results, and makes scheduling and delegation decisions. [decided: owner, 2026-10-28]

C11. Projects use a literate style in which planning, specification, documentation and implementation models are tightly integrated. [decided: owner, 2026-10-28]

C12. A new reader gets up to speed by reading the project like a book. [decided: owner, 2026-10-28]

C13. New functionality is defined by the literate style and specification-by-example as far as possible. [decided: owner, 2026-10-28]

C14. Projects are implemented in larger streams of autonomous work that focus on outcomes and risks rather than a chunk gate on every chunk. [decided: owner, 2026-10-28]

C15. Convergence is handled by evolving formal models, evolving agent instructions and adversarial agent review. [decided: owner, 2026-10-28]

### Decisions taken on 2026-10-28

C17. The vision is built by an iterative roadmap. [decided: owner, 2026-10-28]

C18. The owner amends a methodology rule such as K-003 at the point in the roadmap where a project needs the change. [decided: owner, 2026-10-28]

C19. The Backlog's remaining jobs, the implementation map and the list of what is next, become renderings of the planning/execution model. [decided: owner, 2026-10-28]

C20. The Backlog becomes a rendering per project, as each project adopts the project-orchestrator. [decided: owner, 2026-10-28]

C21. Completing service chunk 1 is the next step. [decided: owner, 2026-10-28]

C22. The owner and the reasoning role review the service's current state after chunk 1. [decided: owner, 2026-10-28]

C79. The owner decides changes to the service's features or roadmap where the vision requires. [decided: owner, 2026-10-28]

C23. The owner adds a project to the service when adoption benefits the project. [decided: owner, 2026-10-28]

C24. No project in the portfolio is known that should not use the service. [decided: owner, 2026-10-28]

C25. Eventually Allegro's approach and the project-orchestrator's approach merge into one model. [decided: owner, 2026-10-28]

C83. The merged model lets Allegro adopt the project-orchestrator. [decided: owner, 2026-10-28]

C26. After the pilot, the owner decides how and when Allegro's approach and the project-orchestrator's approach merge. [decided: owner, 2026-10-28]

C27. The plan model, the IR and the role definitions stay documents until Allegro models them. [decided: owner, 2026-10-28]

C89. The owner and the reasoning role construct nothing ahead of need. [decided: owner, 2026-10-28]

C28. The vision document lives in the methodology repository as docs/vision.md. [decided: owner, 2026-10-28]

C77. Before the vision document is rendered, the reasoning role drafts the document's IR for the owner to edit. [decided: owner, 2026-10-28]

C57. The owner names the first adopter by benefit before the pilot starts. [decided: owner, 2026-10-28]

C84. The first adopter's plan is the pilot. [decided: owner, 2026-10-28]

C85. The roadmap document, not this vision, places the pilot relative to the task-pull loop. [inferred: R25]

### What the portfolio already provides

C29. The plan model defines a project's plan as a tree of nodes with seven stages. evidence: E1. [decided: project-orchestrator process specification]

C71. A node is specified on the way down the tree and verified on the way up. evidence: E1. [decided: project-orchestrator process specification]

C30. In the plan model a feature is its validation: the set of functional tests that constitute the feature. evidence: E1. [decided: project-orchestrator process specification]

C31. The service reads real plan state from git. evidence: E2. [decided: project-orchestrator Plan register]

C59. Plan-state update with an advisory lease is node P2-N010, not yet started. evidence: E2. [decided: project-orchestrator Plan register]

C32. Role definitions live once in the orchestrator plugin. evidence: E3. [decided: project-orchestrator plugin]

C95. A script mirrors the role definitions into projects and checks the copies match the plugin. evidence: E3. [decided: project-orchestrator plugin]

C33. The methodology supplies the rules. evidence: E3. [decided: project-orchestrator process specification]

C88. The project-orchestrator supplies the roles that apply the rules. evidence: E3. [decided: project-orchestrator process specification]

C34. Dispatch has approved scope as the hard boundary, with an optional task or token budget attached when the owner grants scope. evidence: E4. [decided: project-orchestrator process specification]

C35. The IR, the claims check, same-instance confirmation and the four meta-review signals are the convergence machinery for prose. evidence: E5. [decided: IR specification]

C36. Allegro's book is the portfolio's one literate project, developed only as far as Allegro needed. evidence: E6. [decided: owner, 2026-10-28]

C37. Allegro's planning DSL exists as Allegro's first Vivace domain model. evidence: E7. [decided: allegro, 2026-10-25]

C86. The planning DSL is demonstrable at rung 3 of Allegro's demo ladder. evidence: E7. [decided: allegro, 2026-10-25]

C87. The planning DSL models a plan as a directed acyclic graph of outcomes. evidence: E7. [decided: allegro, 2026-10-25]

C38. The service stays a projection of git, which remains authoritative. evidence: E8. [decided: owner, 2026-08-26]

C39. The service spawns no agents on the server. evidence: E8. [decided: owner, 2026-08-26]

C60. The task-pull loop is the standing substitute for server-side agent spawning. evidence: E8. [decided: owner, 2026-08-26]

C40. Today K-003 makes the Backlog the single source of progress truth. evidence: E9. [decided: methodology K-003]

C61. The orchestrator's founding ruling 1 keeps the Plan register and the Backlog in sync. evidence: E9. [decided: project-orchestrator ruling 1, 2026-08-24]

C16. Adversarial review is effective. [decided: owner, 2026-10-28]

C82. Adversarial review has low efficiency until formal models and processes keep the review convergent. [decided: owner, 2026-10-28]

### Gaps the roadmap closes

C41. The plan model and Allegro's planning DSL hold two plan models: a tree with seven stages, a graph of outcomes. [inferred: R6]

C42. The merged model of C25 combines the two plan models in C41. [decided: owner, 2026-10-28]

C72. Allegro's planning DSL demo may not match the project-orchestrator's plan model. [decided: owner, 2026-10-28]

C43. The dispatch loop stops at a stream's boundary: a gate, an empty actionable set, a blocked task or exhausted scope. evidence: E4. [decided: project-orchestrator process specification]

C62. No stop signal exists inside a stream. [inferred: R9]

C44. Stop signals inside a stream take the meta-review signals' shape: mechanical where a count exists, a wording match for a hand check otherwise. [decided: owner, 2026-10-28]

C73. Before a stream starts, the owner approves the stream as scope, budget and accepted risks. [decided: owner, 2026-10-28]

C74. The dispatch loop then runs until a stop signal or the stream's end. [decided: owner, 2026-10-28]

C46. The reasoning role running a stream keeps a running record of findings and the confidence in each finding's fix. [decided: owner, 2026-10-28]

C47. Today the convergence machinery of C35 applies to prose only. [decided: owner, 2026-10-28]

C94. Plans and specifications therefore have no stranger. [inferred: R26]

C48. The stranger extends to plans and specifications. [decided: owner, 2026-10-28]

C75. A fresh reviewer restates the plan from the Plan register and each node's verification criteria before reading the plan's reasoning. [decided: owner, 2026-10-28]

C76. A mismatch between the fresh reviewer's restatement and the plan is a finding. [decided: owner, 2026-10-28]

C49. The rounds-until-readable rule and the meta-review signals carry over to plan review unchanged. [decided: owner, 2026-10-28]

C50. Before the web view drills to code and test results, the reasoning role amends the plan model to record where each node's verification evidence lands. [inferred: R16]

C63. Today the plan model records verification criteria only, not where the evidence lands. evidence: E1. [decided: project-orchestrator process specification]

C51. No document type holds specification, examples and implementation links together. evidence: E10. [decided: owner, 2026-10-28]

C64. Allegro's conceptual-model proposal is the closest existing draft of a document type holding specification, examples and implementation links together. evidence: E10. [decided: owner, 2026-10-28]

C52. The first orchestrated project is the second project the conceptual-model proposal waits for. evidence: E10. [decided: owner, 2026-10-28]

C53. Standardized agent instructions across projects conflict with Allegro's own process documents until Allegro's approach and the project-orchestrator's approach merge. [decided: owner, 2026-10-28]

C54. The web view reads from commits only. [decided: owner, 2026-10-28]

C65. Enlistment today is a `.mcp.json` in the repository clone. evidence: E12. [decided: project-orchestrator-service documentation]

C92. Only Claude Code surfaces read a repository's `.mcp.json`. evidence: E12. [decided: project-orchestrator-service documentation]

C66. Today a surface without a repository clone cannot reach the service. evidence: E12. [decided: owner, 2026-10-28]

C90. The route for a surface without a repository clone is a remote MCP connector. evidence: E12. [decided: owner, 2026-10-28]

C93. The service does not offer a remote MCP connector today. evidence: E12. [decided: project-orchestrator-service documentation]

C67. Today a surface without a repository clone cannot make the git commit the service expects from the session. evidence: E12. [decided: owner, 2026-10-28]

C69. Standing constraint 1, the session as git's only writer, needs the owner's decision at the review of the service for surfaces without a repository clone. [inferred: R22]

C68. The literate style, every project as a book, is roadmap work beyond what Allegro's book settled. [decided: owner, 2026-10-28]

### First steps

C97. Node P2-N010 of service chunk 1 is plan-state update under the advisory lease. evidence: E2. [decided: project-orchestrator Plan register]

C98. Node P2-N011 is degrade to git-only with enlistment documentation. evidence: E2. [decided: project-orchestrator Plan register]

C55. Service chunk 1 closes when the plan-state update and the degrade to git-only are done. evidence: E2. [decided: project-orchestrator Plan register]

C56. Once chunk 1 closes, the task-pull loop comes before topics. [decided: owner, 2026-10-28]

C78. The web view's first version drills to node and task only. [decided: owner, 2026-10-28]

C58. The reasoning role writes the roadmap document after the review of the service, from this vision. [decided: owner, 2026-10-28]

## Relations

R1. C19 refines C8 because C19 names what the Backlog keeps once the planning/execution model is primary.

R2. C18 depends-on C17 because a rule changes at a roadmap step, so the roadmap must exist first.

R3. C20 depends-on C18 because each project's K-003 change is the roadmap step at which the project adopts the orchestrator.

R4. C26 depends-on C22 because the service review precedes the pilot, and the pilot precedes the merge decision.

R5. C56 depends-on C22 because the service review confirms or changes the order C56 proposes.

R6. C37 contradicts C29 because one portfolio holds two definitions of a plan.

R7. C42 refines C25 because C42 names which two things are combined.

R8. C73 refines C14 because C73 states what approving a stream means.

R9. C62 depends-on C43 because the four stops in C43 are all at a stream's boundary, none inside a stream.

R17. C44 depends-on C62 because a stop signal is added where no signal exists.

R18. C50 depends-on C63 because the drill-down needs what the plan model does not yet record.

R10. C48 refines C15 because adversarial review of plans is the plan-level reading of C15.

R11. C49 depends-on C35 because the rules carried over are the prose rules.

R12. C54 depends-on C38 because a primary human surface over a projection is sound only when every view reads the authoritative store.

R13. C52 depends-on C51 because the second project is needed only while the document type is a proposal.

R14. C57 depends-on C23 because adoption by benefit decides who comes first.

R15. C46 supports C16 because a record of findings and fix confidence is one of the processes that keep review convergent.

R16. C50 depends-on C10 because the drill-down to test results is what the web view promises, and C63 says the plan model does not yet record the evidence.

R19. C66 depends-on C4 because the surfaces C4 names include ones with no repository clone.

R20. C67 depends-on C4 because the surfaces C4 names include ones with no repository clone.

R21. C68 refines C11 because C68 says the literate style is still to be designed, not copied from Allegro.

R22. C69 depends-on C67 because the writer the constraint assumes is absent on those surfaces.

R23. C42 depends-on C72 because the possible mismatch is why the two plan models are combined rather than one adopted.

R24. C69 depends-on C79 because the owner's decisions on the service fall at the review of the service after chunk 1.

R25. C85 depends-on C58 because the sequence beyond chunk 1 is the roadmap document's content, not this vision's.

R26. C94 depends-on C47 because a stranger for plans would be part of the machinery C47 limits to prose.

## Evidence

E1. project-orchestrator docs/process/plan-model.md, sections "The hierarchy", "Features" and "The node lifecycle": the tree, the V-shaped progression, the seven-stage table, and the sentence "a feature is its validation".

E2. project-orchestrator docs/plan-register.md at main (merge of PR #11): P2-N009 `[done]`, P2-N010 `[identified]`, P2-N011 `[identified]`.

E3. project-orchestrator plugin/README.md line 45: `sync_agents.ts` mirrors the plugin's agents into `.claude/agents/`, with `--check` verifying the mirror; docs/process/roles.md cites methodology rules by identifier for each role's duties.

E4. project-orchestrator docs/process/dispatch.md, section "The loop", step 4 (stops at a gate, an empty actionable set, a blocked task, or exhausted scope); docs/open-risks.md R2 (the owner MAY attach a task or token budget to a scope grant).

E5. methodology docs/intermediate-representation.md, sections "Stranger rounds" and "Meta-review"; communication-pipeline scripts/claims-check.mjs and scripts/signals.mjs.

E6. allegro docs/book/README.md: the book, decision D52 of 2026-10-21.

E7. allegro docs/book/vivace/planning-dsl.md §1 and §2.1 (a plan is a directed acyclic graph of plan nodes; Shape 1, execution external); docs/plans/release-track.md line 203 (rung 3 demoable, 2026-10); docs/plans/planning-pilot.md (status active, 2026-10-25).

E8. project-orchestrator docs/plans/orchestration-service.md, "Standing constraints" 1 (git remains authoritative) and 5 (no server-side agent spawning; the task-pull loop is the substitute); "Chunks" 1 to 5.

E9. methodology docs/rules/knowledge.md K-003; project-orchestrator docs/process/plan-model.md, section "Relationship to the Backlog (K-003)", owner ruling 1 of 2026-08-24.

E10. allegro docs/plans/conceptual-model-methodology-delta.md (status: draft proposal); methodology docs/backlog.md, entry "Convergence", "standard types need a second project".

E11. The session of 2026-10-28: the owner's vision message (eight points), the reasoning role's assessment, and the owner's reply ("You can draft the vision in IR"; "I agree with all your recommendations and terms, except let's change define-by-example to specification-by-example").

E12. project-orchestrator-service README.md ("every write is the session's own git commit, which this service validates but never makes"); docs/mcp-enlistment.md ("Claude Code reads a repository-root `.mcp.json` automatically on both the local and web surfaces"); src/auth.ts, bearer-token auth only.

## Asks

A1. Edit the draft: confirm, change or strike each proposed claim. Done: the owner ratified the draft on 2026-10-28. Depends: C44, C46, C47, C48, C49, C50, C51, C52, C53, C54, C56, C57, C58, C64, C66, C67.

A2. Ratify or strike the four proposed terms. Done: ratified by the owner on 2026-10-28. Depends: T12, T13, T14, T15.

A3. Name the first adopter. Depends: C57.

A4. Authorize the paraphraser's rendering of docs/vision.md and the stranger rounds, so the document is delivered under W-009. Done: the owner's ratification of 2026-10-28 authorized both; rendered the same day. Depends: A1.
