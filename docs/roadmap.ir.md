# IR: Roadmap for the portfolio after the service review

Reader: RD-4
Purpose: document. The roadmap document the vision schedules after the review of the service: the vision's gaps sequenced into steps, each step naming the plan nodes that close it and the condition that opens it, carrying the owner's decisions of 2026-10-29.
Status: delivered IR-only (approved by the owner on 2026-10-30 with its five proposed claims confirmed and the term roadmap step ratified; no prose rendering and no stranger rounds, under the IR-only delivery the owner adopted the same day; mtool ir check 0 violations; unratified terms 0)
Source: the vision (docs/vision.ir.md); the service review after chunk 1 (docs/records/service-review-2026-10-29.ir.md) and the owner's reply of 2026-10-29 adopting its fourteen defaults; the project-orchestrator's Plan register after the specification gates of 2026-10-29.
Footprint: docs/roadmap.ir.md; docs/vocabulary.md

## Terms

T1. Roadmap document. defined-at: vocabulary.md#def-roadmap-document [decided: owner, 2026-10-29]

T2. Roadmap step. defined-at: vocabulary.md#def-roadmap-step [decided: owner, 2026-10-30]

T3. Planning/execution model. defined-at: vocabulary.md#def-planning-execution-model [decided: owner, 2026-10-28]

T4. Web view. defined-at: vocabulary.md#def-web-view [decided: owner, 2026-10-28]

T5. Stream. defined-at: vocabulary.md#def-stream [decided: owner, 2026-10-28]

T6. Specification-by-example. defined-at: vocabulary.md#def-specification-by-example [decided: owner, 2026-10-28]

T7. Surface without a repository clone. defined-at: vocabulary.md#def-surface-without-a-repository-clone [decided: owner, 2026-10-29]

T8. Remote MCP connector. defined-at: vocabulary.md#def-remote-mcp-connector [decided: owner, 2026-10-29]

T9. Pilot. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md [decided: owner, 2026-08-26]

T10. Task-pull loop. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md [decided: owner, 2026-08-26]

T11. Comprehension model. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/p3-n002-comprehension-model.md [decided: project-orchestrator P3-N002 plan]

T12. Reasoning role. defined-at: vocabulary.md#def-reasoning-role [decided: methodology vocabulary]

## Claims

### What the roadmap is

C1. The roadmap document sequences the vision's gaps into roadmap steps. evidence: E1, E2. [decided: owner, 2026-10-29]

C2. Each roadmap step names the plan nodes that close it and the condition that opens it. [decided: owner, 2026-10-30]

C3. A roadmap step's condition is a state of the planning/execution model, never a date. [decided: owner, 2026-10-30]

C4. The Plan register of each project stays the source of progress truth, and the roadmap document is a statement of intent over it. evidence: E3. [decided: owner, 2026-10-29]

C5. The roadmap is iterative: the owner and the reasoning role revise it at each review the vision or this document schedules. evidence: E1. [decided: owner, 2026-10-28]

C6. The portfolio's projects join the roadmap one at a time, each when the benefit to that project is shown. evidence: E1. [decided: owner, 2026-10-28]

### Step 1: the work in flight

C7. Step 1 is open now: its nodes were entered at the specification gates of 2026-10-29. evidence: E3. [decided: project-orchestrator Plan register]

C8. The comprehension model, node P3-N002, runs as four children: the thin slice P3-N006, the type and the K-003 amendment P3-N007, the instance P3-N008, and sibling ordering retired P3-N009. evidence: E3. [decided: project-orchestrator Plan register]

C9. The common risk catalogue, node P3-N003, runs as three children: one class end to end P3-N010, the sweep P3-N011, and the Article 8 proposal P3-N012. evidence: E3. [decided: project-orchestrator Plan register]

C10. Sequence mode, node P3-N005, runs as four children: the stop conditions P3-N013, the loop P3-N014, the demonstration P3-N015, and the determination P3-N016. evidence: E3. [decided: project-orchestrator Plan register]

C11. Node P1-N014, role contracts adopt the methodology's conduct rules, reached done on 2026-10-29, before the pilot. evidence: E2, E3. [decided: project-orchestrator Plan register]

C12. Node P3-N007 drafts the amendment of K-003 by one conditional clause, under which a project that declares a planning/execution model takes that model as its progress truth. evidence: E3. [decided: owner, 2026-10-29]

C13. The project-orchestrator switches its own Backlog to a rendering of the planning/execution model only when the amendment is released and pinned. evidence: E3. [decided: owner, 2026-10-29]

### Step 2: the task-pull loop

C14. Step 2 is the task-pull loop, node P2-N005, the next service chunk. evidence: E2. [decided: owner, 2026-10-29]

C15. Step 2 opens now, because service chunk 1 closed on 2026-09-16. evidence: E1, E2. [decided: owner, 2026-10-29]

C16. The task-pull loop carries per-task claims, role-aware identity, the branch-name fallback claim and claim release. evidence: E2. [decided: owner, 2026-10-29]

C17. The task-pull loop is the standing substitute for server-side agent spawning. evidence: E1. [decided: owner, 2026-10-28]

### Step 3: the web view's first version

C18. Step 3 is the web view's first version, a node split out of P2-N003, owner questions and the plan view. evidence: E2. [decided: owner, 2026-10-29]

C19. Step 3 may run in parallel with step 2. evidence: E2. [decided: owner, 2026-10-29]

C20. The web view's first version is specified against the comprehension model after P3-N006, the five-resource slice, closes. evidence: E2. [decided: owner, 2026-10-29]

C21. The web view's first version is read-only, reads from commits only, and drills to node and task. evidence: E1, E2. [decided: owner, 2026-10-29]

C22. The service plan's design sketch loses its live-update line. evidence: E2. [decided: owner, 2026-10-29]

### Step 4: the pilot on methodology-tools

C23. Step 4 is the pilot on methodology-tools, inside node P2-N006, migration and pilot. evidence: E1, E2. [decided: owner, 2026-10-29]

C24. Step 4 opens when steps 2 and 3 close and node P1-N014 is done. evidence: E2. [decided: owner, 2026-10-29]

C25. Service chunk 5 keeps its order: the project-orchestrator's own orchestration migrates onto the service, then the pilot runs. evidence: E2. [decided: owner, 2026-10-29]

C26. Multi-project plan state is built inside node P2-N006. evidence: E2. [decided: owner, 2026-10-29]

C27. The project-orchestrator's adoption of the service at chunk 5 is by construction and is not the pilot. evidence: E1. [decided: owner, 2026-10-29]

C28. At the pilot, methodology-tools declares its planning/execution model in its Classification, and K-003's amended clause then applies to it. [inferred: R4]

C29. The pilot's close is the next review of this roadmap. [decided: owner, 2026-10-30]

### Step 5: after the pilot

C30. Step 5 opens when the pilot closes. [decided: owner, 2026-10-30]

C31. The owner question queue, the second node split out of P2-N003, carries the web view's scheduling and delegation decisions and comes after the pilot. evidence: E2. [decided: owner, 2026-10-29]

C32. Topics, node P2-N004, come after the pilot and are built only on a shown need. evidence: E2. [decided: owner, 2026-10-29]

C33. A remote MCP connector node comes after the pilot and starts by checking which authentication the surfaces without a repository clone accept. evidence: E2. [decided: owner, 2026-10-29]

C34. Surfaces without a repository clone receive read, question and delegation tools only, under the write model kept at the review. evidence: E2. [decided: owner, 2026-10-29]

C35. The plan-model amendment recording where each node's verification evidence lands comes after the pilot. evidence: E2. [decided: owner, 2026-10-29]

C36. The web view drills to code and test results only after that amendment. evidence: E1. [inferred: R6]

C37. The scheduled check for breakage between deploys stays in the Backlog through the pilot. evidence: E2. [decided: owner, 2026-10-29]

C38. Whether Allegro's planning DSL and the project-orchestrator's plan model merge, and how, is decided after the pilot. evidence: E1. [decided: owner, 2026-10-28]

### Steps on the methodology side

C39. The stranger extends to plans and specifications as a methodology step, with no plan node yet. evidence: E1. [decided: owner, 2026-10-28]

C40. The stranger's extension to plans opens when node P3-N016 delivers its determination on sequence mode. [decided: owner, 2026-10-30]

C41. Stop signals inside a stream are a methodology step after node P3-N016. evidence: E1, E3. [decided: owner, 2026-10-29]

C42. Streams approved as scope, budget and accepted risks follow the stop signals inside a stream. evidence: E1. [inferred: R8]

C43. The literate style, every project as a book, is a methodology step with no opening condition yet. evidence: E1. [decided: owner, 2026-10-28]

C44. The document type holding specification, examples and implementation links together opens when the pilot has a second project, as the conceptual-model proposal waits for. evidence: E1. [decided: owner, 2026-10-28]

C45. Standardized agent instructions across projects wait for the merge of Allegro's approach and the project-orchestrator's. evidence: E1. [decided: owner, 2026-10-28]

### Housekeeping the review ordered

C46. One housekeeping task corrects the records that lag the state in the service and orchestrator repositories, naming methodology-tools as the pilot in the comprehension plan and the service plan. evidence: E2. [decided: owner, 2026-10-29]

C47. The vision IR's chunk-1 claims were corrected on 2026-10-29 and the vision re-rendered under W-009. evidence: E2. [decided: owner, 2026-10-29]

## Relations

R1. C2 depends-on C1 because a sequence of steps needs each step to say what closes it and what opens it.

R2. C3 depends-on C4 because a register state is observable where a date is a guess.

R3. C15 depends-on C14 because the next chunk opens when the previous one closes.

R4. C28 depends-on C12 because the amended clause applies to a project only through its declaration.

R5. C24 depends-on C20 because the pilot runs on a view specified against the slice.

R6. C36 depends-on C35 because a drill-down needs a recorded location for its evidence.

R7. C20 depends-on C8 because P3-N006 is the five-resource slice the view is specified against.

R8. C42 depends-on C41 because a stream without stop signals inside it runs to its boundary unchecked.

R9. C40 depends-on C10 because P3-N016 is the determination the extension builds on.

R10. C29 depends-on C5 because an iterative roadmap names its next revision.

R11. C34 depends-on C33 because the tools reach those surfaces only through the connector.

## Evidence

E1. docs/vision.ir.md (reviewed, edited 2026-10-29): claims C21 to C27, C38, C39, C42, C44, C46 to C58, C60, C62 to C64, C68, C69, C72 to C76, C85, C89, C90, C99 to C102.

E2. docs/records/service-review-2026-10-29.ir.md: asks A1 to A14, each adopted at its default by the owner on 2026-10-29, and claims C86 to C133 under the proposed roadmap changes.

E3. project-orchestrator docs/plan-register.md on branch p3-gates-2026-10-29 (2026-10-29): P3-N002, P3-N003 and P3-N005 `[broken-down]` with children P3-N006 to P3-N016 `[identified]`; P1-N014 `[executing]`; the Backlog entry on switching the Backlog to a rendering; RU-021.

E4. project-orchestrator docs/plans/orchestration-service.md: chunks 2 to 5 as nodes P2-N003 to P2-N006, standing constraint 1, the design sketch.

## Asks

A1. Edit the draft: confirm, change or strike each proposed claim. Done: all five confirmed by the owner on 2026-10-30. Depends: C2, C3, C29, C30, C40.

A2. Ratify or strike the term roadmap step. Done: ratified by the owner on 2026-10-30. Depends: T2.

A3. Authorize the paraphraser's rendering of docs/roadmap.md and the stranger rounds under W-009. Done otherwise: the owner chose IR-only delivery on 2026-10-30, so no rendering runs and the IR is the roadmap document. Depends: A1.
