# IR: Review of the project-orchestrator-service after service chunk 1

Reader: RD-1
Purpose: report. The review of the project-orchestrator-service's current state after service chunk 1 against the vision, with proposed changes to the service's roadmap and the corrections the vision IR needs, for the owner's decisions.
Status: delivered (paraphraser rendering 2026-10-29, disposition D1 by BP-07, no stranger rounds, RD-1 report; round trip 142 of 142; the owner adopted all fourteen defaults and ratified the three terms on 2026-10-29; unratified terms 0)
Source: the owner's request of 2026-10-29 for the review the vision schedules (vision claims C22 and C79); the files of project-orchestrator, project-orchestrator-service and methodology read on 2026-10-29, listed under Evidence.
Footprint: docs/records/service-review-2026-10-29.ir.md; docs/records/service-review-2026-10-29.md

## Terms

T1. Service chunk. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md#chunks [decided: owner, 2026-08-26]

T2. Plan register. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-register.md [decided: project-orchestrator process specification]

T3. Plan model. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/process/plan-model.md [decided: project-orchestrator process specification]

T4. Planning/execution model. defined-at: ../vocabulary.md#def-planning-execution-model [decided: owner, 2026-10-28]

T5. Web view. defined-at: ../vocabulary.md#def-web-view [decided: owner, 2026-10-28]

T6. Task-pull loop. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md#standing-constraints [decided: owner, 2026-08-26]

T7. Topics. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md#chunk-3--topics-and-coordination [decided: owner, 2026-08-26]

T8. Owner question queue. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md#design-sketch [decided: owner, 2026-08-26]

T9. Pilot. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md#chunk-5--migration-and-pilot [decided: owner, 2026-08-26]

T10. Standing constraint. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/orchestration-service.md#standing-constraints [decided: owner, 2026-08-26]

T11. Write model. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/p2-n002-service-skeleton.md#the-write-model--git-stays-the-only-source-of-truth [decided: owner, 2026-08-26]

T12. Advisory lease. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/p2-n002-service-skeleton.md#decisions-for-the-gate [decided: owner, 2026-08-26]

T13. Enlistment. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/process/enlistment.md [decided: project-orchestrator process specification]

T14. Fallback rule. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/process/enlistment.md#the-fallback-rule [decided: project-orchestrator process specification]

T15. v1 process. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/process/dispatch.md [decided: project-orchestrator process specification]

T16. Smoke test. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/p2-n012-deploy-from-ci-on-merge.md#the-smoke-test-and-where-its-token-comes-from [decided: owner, 2026-09-01]

T17. Preprod alias. defined-at: https://github.com/majodali/project-orchestrator-service/blob/main/docs/classification.md [decided: owner, 2026-09-01]

T18. Live alias. defined-at: https://github.com/majodali/project-orchestrator-service/blob/main/docs/classification.md [decided: owner, 2026-09-01]

T19. Comprehension model. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/plans/p3-n002-comprehension-model.md [decided: owner, 2026-10-29]

T20. Backlog. defined-at: ../rules/knowledge.md [decided: methodology K-003]

T21. Risk register. defined-at: https://github.com/majodali/project-orchestrator/blob/main/docs/open-risks.md [decided: project-orchestrator Risk register]

T22. Classification. defined-at: ../vocabulary.md#def-classification [decided: methodology vocabulary]

T23. Reasoning role. defined-at: ../vocabulary.md#def-reasoning-role [decided: methodology vocabulary]

T24. Paraphraser. defined-at: ../vocabulary.md#def-paraphraser [decided: methodology vocabulary]

T25. Stranger. defined-at: ../vocabulary.md#def-stranger [decided: owner, 2026-10-23]

T26. Intermediate representation (IR). defined-at: ../vocabulary.md#def-intermediate-representation [decided: owner, 2026-10-24]

T27. Surface without a repository clone. A Claude surface whose session has no checkout of the project's repository; in this review, the Claude web interface, Claude Mobile and Claude Duet. [decided: owner, 2026-10-29, ratified at the review]

T28. Remote MCP connector. The service's MCP endpoint registered on a Claude surface as a connector, reached by URL rather than through a checked-in `.mcp.json`. [decided: owner, 2026-10-29, ratified at the review]

T29. Roadmap document. The document the reasoning role writes after this review, sequencing the vision's gaps into steps (vision claim C58). [decided: owner, 2026-10-29, ratified at the review]

## Claims

### (a) The service's current state

<!-- part: changed for every claim under (a) and (a2). -->

C1. Service chunk 1, node P2-N002 "service skeleton and plan state", reached done on 2026-09-16 after the owner's gate demonstration. evidence: E1, E2, E13. [decided: project-orchestrator Plan register]

C2. All five children of node P2-N002 are done: P2-N007 repository bootstrap, P2-N008 reachability slice, P2-N009 plan-state read, P2-N010 plan-state update with the advisory lease, P2-N011 degrade to git-only. evidence: E1. [decided: project-orchestrator Plan register]

C3. Node P2-N011, degrade to git-only and enlistment documentation, reached done on 2026-09-07. evidence: E13. [decided: project-orchestrator Backlog]

C4. Node P2-N012, deploy the service from CI on merge, is done, as are its four children: P2-N013 alias assumptions, P2-N014 pull-request checks, P2-N015 alias-aware lease tables, P2-N016 deploy, smoke and promote. evidence: E1. [decided: project-orchestrator Plan register]

C5. Service chunks 2 to 5 stand at identified: P2-N003 owner questions and the plan view, P2-N004 topics and coordination, P2-N005 the task-pull loop, P2-N006 migration and pilot. evidence: E1. [decided: project-orchestrator Plan register]

#### What is deployed

C6. The service is one TypeScript Lambda function on Node.js 22 behind an AWS HTTP API, defined in one AWS SAM template. evidence: E6, E10. [decided: project-orchestrator-service template.yaml]

C7. The HTTP API carries two routes: "ANY /mcp" for MCP over streamable HTTP, and "GET /health" without authentication. evidence: E3, E10. [decided: project-orchestrator-service template.yaml]

C8. Two DynamoDB tables hold advisory leases, one serving the live alias and one serving the preprod alias. evidence: E10, E11. [decided: project-orchestrator-service template.yaml]

C9. Every call to /mcp must carry a bearer token equal to the server's MCP_AUTH_TOKEN value. evidence: E5. [decided: project-orchestrator-service src/auth.ts]

C10. With MCP_AUTH_TOKEN unset, the server refuses every /mcp call rather than accepting all callers. evidence: E5. [decided: project-orchestrator-service README]

C11. The service reads GitHub through an installed GitHub App holding contents-read permission only. evidence: E3, E6. [decided: owner, 2026-08-26]

C12. The service holds no credential able to write any repository. evidence: E2, E3. [decided: P2-N002 specification gate evidence]

C13. The service reads one project, named by the MCP_PROJECT setting, whose default is majodali/project-orchestrator. evidence: E3. [decided: project-orchestrator-service README]

C14. The service serves the Plan register only, with no other register and no comprehension model. evidence: E6, E13. [decided: owner, 2026-08-26]

#### Which MCP tools exist

C15. The service exposes six MCP tools: service_identity, plan_read, plan_lease_acquire, plan_update, plan_confirm and plan_lease_release. evidence: E2, E3, E4. [decided: project-orchestrator-service src/planReadTool.ts and src/planWriteTools.ts]

C16. The tool service_identity returns the service's name, version, deployed commit and configured project. evidence: E3, E9. [decided: project-orchestrator-service README]

C17. The tool plan_read returns the Plan register at a named git ref as structured nodes, for the whole tree or for one subtree. evidence: E4. [decided: project-orchestrator-service src/planReadTool.ts]

C18. Every plan_read answer carries the commit SHA and fetch time of its source. evidence: E4. [decided: project-orchestrator-service src/planReadTool.ts]

C19. No tool answers from a cached copy of the register: every call fetches the register from git afresh. evidence: E4. [decided: project-orchestrator-service src/planWriteTools.ts]

#### The write path

C20. Under the write model, a plan-state update takes three calls: plan_lease_acquire, plan_update, then plan_confirm with the SHA of the session's pushed commit. evidence: E4, E6. [decided: owner, 2026-08-26]

C21. The tool plan_update checks a transition against the plan model's lifecycle and the register at the given SHA, returning the exact line edit. evidence: E4. [decided: project-orchestrator-service src/planWriteTools.ts]

C22. The calling session, never the service, applies the returned edit, commits the edit and pushes the commit. evidence: E2, E4. [decided: owner, 2026-08-26]

C23. The tool plan_update refuses an illegal transition, naming plan-model.md as the authority. evidence: E7. [decided: project-orchestrator Risk register]

C24. The tool plan_update refuses an edit against a stale baseline SHA, naming both SHAs. evidence: E7. [decided: project-orchestrator Risk register]

C25. The tool plan_confirm reports a divergence, naming the file and line, when the commit at the given SHA lacks the edit. evidence: E4. [decided: project-orchestrator-service src/planWriteTools.ts]

#### What the lease does

C26. The advisory lease is one DynamoDB item per table, allowing one lease holder at a time. evidence: E8. [decided: project-orchestrator-service src/planRegister/dynamoLeaseBackend.ts]

C27. While one holder's lease is live, the service refuses a second plan_lease_acquire. evidence: E4. [decided: project-orchestrator-service src/planWriteTools.ts]

C28. A lease lasts 600 seconds by default, with any requested duration clamped to between 30 and 3600 seconds. evidence: E4. [decided: project-orchestrator-service src/planWriteTools.ts]

C29. Lease expiry is enforced by a DynamoDB condition at acquire time, not by DynamoDB's own background expiry sweep. evidence: E8. [decided: project-orchestrator-service src/planRegister/dynamoLeaseBackend.ts]

C30. The tool plan_confirm releases the lease on success, with plan_lease_release freeing a lease early. evidence: E4. [decided: project-orchestrator-service src/planWriteTools.ts]

C31. The advisory lease guards Plan register edits only: no tool records a claim on a task. evidence: E3, E4. [decided: project-orchestrator-service src/planWriteTools.ts]

C32. The service authenticates a client, not a role: one shared bearer token cannot tell one orchestration role from another. evidence: E2, E13. [decided: P2-N002 specification decision 12]

#### How a session enlists

C33. Enlistment needs three things: a checked-in `.mcp.json` at the repository root, enableAllProjectMcpServers in `.claude/settings.json`, and MCP_AUTH_TOKEN in the session's environment. evidence: E9. [decided: project-orchestrator process specification]

C34. The `.mcp.json` names the endpoint, a 30000 millisecond timeout and an Authorization header expanded from MCP_AUTH_TOKEN, keeping the token out of git. evidence: E9, E12. [decided: project-orchestrator .mcp.json]

C35. The coordinating repository majodali/project-orchestrator is enlisted by a checked-in `.mcp.json` and settings file. evidence: E12. [decided: project-orchestrator .mcp.json]

C36. Enlistment from the checked-in `.mcp.json` is evidenced in Claude Code cloud sessions and on the owner's local machine. evidence: E2, E7. [decided: P2-N002 specification gate evidence]

C37. A session confirms enlistment by listing the service's tools and calling service_identity. evidence: E9. [decided: project-orchestrator process specification]

#### How CI deploys

C38. A pull request to the service repository runs build, lint, test and "sam validate --lint", with read-only permissions and no route to an AWS role. evidence: E11, E14. [decided: project-orchestrator-service .github/workflows/checks.yml]

C39. A merge to main assumes the deploy role through GitHub OIDC, deploys, and points the preprod alias at the new Lambda version. evidence: E11, E14. [decided: project-orchestrator-service .github/workflows/deploy.yml]

C40. The smoke test checks /health, the tools/list contents and one lease acquire-and-release cycle against the preprod alias's Function URL. evidence: E15. [decided: project-orchestrator-service scripts/smoke-test.sh]

C41. Only a passing smoke test promotes the version, by repointing the live alias at the version. evidence: E11, E14. [decided: owner, 2026-09-01]

C42. A failing smoke test leaves the live alias on the previous version, with the workflow run red. evidence: E11, E16. [decided: owner, 2026-09-01]

C43. GitHub OIDC supplies the deploy credentials, leaving no long-lived AWS secret in the service repository. evidence: E11. [decided: owner, 2026-09-01]

C44. The first green deploy run took 1 minute 40 seconds end to end, on 2026-09-06. evidence: E16. [decided: project-orchestrator-service runbook]

#### What the fallback is

C45. The fallback rule: a session whose service is unreachable does not retry, does not wait, and edits the Plan register by hand under the v1 process. evidence: E9. [decided: project-orchestrator process specification]

C46. The fallback exercise covered both failure modes, unreachable endpoint and unset token, on cloud and local surfaces, closing risk R12, service outage stops work, on 2026-09-07. evidence: E7. [decided: project-orchestrator Risk register]

C47. In both failure modes the session started normally, with the service's tools absent from the session. evidence: E7. [decided: project-orchestrator Risk register]

C48. Risk R12's remaining exposure is breakage between deploys, which no monitoring watches today. evidence: E7, E11. [decided: project-orchestrator Risk register]

C49. A degraded-but-present service, the case the no-retry rule would really face, has never been exercised. evidence: E7. [decided: project-orchestrator Risk register]

C50. Risk R17, the harness's guidance pushing against the fallback rule, is open. evidence: E7. [decided: project-orchestrator Risk register]

C51. Risk R17's mitigation, fallback wording in the orchestrator's role definitions, belongs to node P1-N014, role contracts adopt the v1.5.0 conduct rules, which stands at planned. evidence: E1, E7. [decided: project-orchestrator Risk register]

### (a2) Records that lag the state

G1. cluster: C52, C53, C54, C55, C56, C57, C58, C59, C60 [proposed: this IR]

C52. The service repository's Backlog lists node P2-N011, degrade to git-only, and the deploy-on-merge workflow as upcoming, though both are done. evidence: E1, E17. [decided: project-orchestrator-service Backlog]

C53. The service repository's Backlog labels node P2-N012's work "chunk 2", the parent plan's name for node P2-N003, owner questions and the plan view. evidence: E17, E18. [decided: project-orchestrator-service Backlog]

C54. The service repository's docs/mcp-enlistment.md says the coordinating repository is not enlisted, though a checked-in `.mcp.json` enlists the coordinating repository. evidence: E12, E19. [decided: project-orchestrator-service docs/mcp-enlistment.md]

C55. The service README names methodology v1.3.0, while the service's Classification pins methodology 1.6.0. evidence: E3, E20. [decided: project-orchestrator-service README and Classification]

C56. The service runbook records plan_read's cold and warm latency and the stack's running cost as not yet measured. evidence: E21. [decided: project-orchestrator-service runbook]

C57. The orchestrator Backlog's upcoming item "CI for project-orchestrator-service" stays open, though node P2-N012, deploy the service from CI on merge, delivered the CI. evidence: E1, E13. [decided: project-orchestrator Backlog]

C58. The plan for node P3-N001, project comprehension and continuous implementation, says Allegro is the pilot under node P1-N006, pilot on a real project. evidence: E22. [decided: project-orchestrator comprehension plan]

C59. The service plan's chunk 5, node P2-N006 migration and pilot, names the pilot project only as an owner-chosen portfolio project. evidence: E18. [decided: project-orchestrator orchestration-service plan]

C60. The plan document for node P3-N002, the comprehension model, reads Status draft, though the owner accepted the plan on 2026-10-29. evidence: E23. [decided: project-orchestrator P3-N002 plan]

### (b) The vision's requirements on the service

<!-- part: covered for every claim under (b): each restates a vision claim the owner ratified. -->

C61. Vision claim C3: an agent queries the project-orchestrator-service for available tasks and claims a task. evidence: E26. [decided: owner, 2026-10-28]

C62. Vision claim C80: the agent changes the project's repository directly while performing the task. evidence: E26. [decided: owner, 2026-10-28]

C63. Vision claim C4: an agent is enlisted from any Claude surface: Claude Code web, desktop or CLI, Claude Duet, the Claude web interface or Claude Mobile. evidence: E26. [decided: owner, 2026-10-28]

C64. Vision claim C9: the project-orchestrator-service provides a web view of each project's planning/execution model. evidence: E26. [decided: owner, 2026-10-28]

C65. Vision claim C10: the web view is the primary way a human sees status, drills into subtasks, code and test results, and makes scheduling and delegation decisions. evidence: E26. [decided: owner, 2026-10-28]

C66. Vision claim C78: the web view's first version drills to node and task only. evidence: E26. [decided: owner, 2026-10-28]

C67. Vision claim C50: before the web view drills to code and test results, the reasoning role amends the plan model to record where each node's verification evidence lands. evidence: E26. [decided: owner, 2026-10-28]

C68. Vision claim C54: the web view reads from commits only. evidence: E26. [decided: owner, 2026-10-28]

C69. Vision claim C38: the service stays a projection of git, which remains authoritative. evidence: E26. [decided: owner, 2026-08-26]

C70. Vision claim C39: the service spawns no agents on the server. evidence: E26. [decided: owner, 2026-08-26]

C71. Vision claim C60: the task-pull loop is the standing substitute for server-side agent spawning. evidence: E26. [decided: owner, 2026-08-26]

C72. Vision claim C56: once service chunk 1 closes, the task-pull loop comes before topics. evidence: E26. [decided: owner, 2026-10-28]

C73. Vision claim C85: the roadmap document, not the vision, places the pilot relative to the task-pull loop. evidence: E26. [decided: owner, 2026-10-28]

C74. Vision claim C58: the reasoning role writes the roadmap document after the review of the service, from the vision. evidence: E26. [decided: owner, 2026-10-28]

C75. Vision claim C22: the owner and the reasoning role review the service's current state after service chunk 1. evidence: E26. [decided: owner, 2026-10-28]

C76. Vision claim C79: the owner decides changes to the service's features or roadmap where the vision requires. evidence: E26. [decided: owner, 2026-10-28]

C77. Vision claim C90: the route for a surface without a repository clone is a remote MCP connector. evidence: E26. [decided: owner, 2026-10-28]

C78. Vision claim C69: standing constraint 1, the session as git's only writer, needs the owner's decision at this review for surfaces without a repository clone. evidence: E26. [decided: owner, 2026-10-28]

C79. Vision claim C99: the owner named methodology-tools the first adopter on 2026-10-29. evidence: E26. [decided: owner, 2026-10-29]

C80. Vision claim C100: the project-orchestrator adopts the service by construction when service chunk 5 moves the orchestrator's own orchestration onto the service. evidence: E26. [decided: owner, 2026-10-29]

C81. Vision claim C101: the project-orchestrator's adoption is not the pilot. evidence: E26. [decided: owner, 2026-10-29]

C82. Vision claim C89: the owner and the reasoning role construct nothing ahead of need. evidence: E26. [decided: owner, 2026-10-28]

C83. Vision claim C70: an agent is also delegated to by another agent. evidence: E26. [decided: owner, 2026-10-28]

C84. Vision claim C96: the agent updates the plan when closing the task. evidence: E26. [decided: owner, 2026-10-28]

### (c) Gaps between the state and the vision

<!-- part: changed for every claim under (c). -->

#### Surfaces without a repository clone

C85. No surface without a repository clone can reach the service today, because enlistment rides on a cloned repository's `.mcp.json`. [inferred: R1]

C86. The service offers no remote MCP connector: a static bearer token in a request header is the service's only client authentication. evidence: E5. [decided: project-orchestrator-service src/auth.ts]

C87. A surface without a repository clone has no checkout in which to apply the edit plan_update returns. [inferred: R2]

C88. Standing constraint 1, git remains authoritative, requires git to hold the state without naming who writes git. evidence: E18. [decided: project-orchestrator orchestration-service plan]

C89. The session-only writer rule comes from the write model, decision 3 of the P2-N002 plan, which keeps every repository write credential out of the service. evidence: E6. [decided: owner, 2026-08-26]

C90. A service commit through a GitHub App with write permission would break the write model while keeping standing constraint 1. [inferred: R3]

C91. No record read for this review names Claude Code desktop as a surface where enlistment was exercised. evidence: E7, E9. [inferred: R4]

#### The web view and its drill-down

C92. The service has no web view: the service exposes MCP tools and a health route only, with no human-facing page. [inferred: R5]

C93. The service plan's design sketch has the plan view updated as sessions publish, not by polling git. evidence: E18. [decided: project-orchestrator orchestration-service plan]

C94. Without a recorded location for each node's verification evidence, the service has no source for a drill-down to code and test results. [inferred: R7]

#### The task-pull loop

C95. The service has no tool handing out a next task, recording a task claim, or reporting task completion. [inferred: R8]

C96. Role-aware identity, needed to hand out the next task in a role, was deferred to the task-pull loop by decision 12 of the P2-N002 specification. evidence: E2, E13. [decided: P2-N002 specification decision 12]

C97. The fallback task-claim protocol, claim release when a session dies, and reconciliation after an outage are open Backlog items for the task-pull loop. evidence: E13. [decided: project-orchestrator Backlog]

C98. The advisory lease's behaviour under several live sessions is untested, deferred to the task-pull loop by decision 7 of the P2-N002 plan. evidence: E2, E6. [decided: owner, 2026-08-26]

#### The pilot

C99. The pilot on methodology-tools needs multi-project plan state, which the service lacks. [inferred: R9]

C100. The orchestrator Backlog places multi-project plan state with node P2-N006, migration and pilot. evidence: E13. [decided: project-orchestrator Backlog]

#### Node P2-N003 and the comprehension model P3-N002

C101. The comprehension plan says node P2-N003, owner questions and the plan view, likely needs re-specifying against the comprehension model, a change the owner confirmed as open on 2026-09-16. evidence: E22. [decided: owner, 2026-09-16]

C102. The comprehension model, node P3-N002, extends the planning/execution model with flat resources and node-to-resource edges, held in docs/project-model.md. evidence: E23. [decided: owner, 2026-10-29]

C103. The comprehension model, node P3-N002, must work with no orchestration service running, leaving any hosted view to node P2-N003, owner questions and the plan view. evidence: E23, E24. [decided: P3-N001 specification]

C104. Node P3-N002, the comprehension model, stands at planned, with its specification dispatched as task T043 on 2026-10-29. evidence: E1, E23. [decided: project-orchestrator Plan register]

C105. Ruling RU-021 makes the planning/execution model, once a project has one, the project's source of progress truth, amending K-003. evidence: E25. [decided: owner, 2026-10-29]

C106. The orchestrator Backlog files service access to the comprehension model, a model_read beside plan_read, under node P2-N003 or a later service chunk. evidence: E13. [decided: project-orchestrator Backlog]

C107. A plan view specified against the Plan register alone, before the comprehension model lands, would need re-specifying once the comprehension model lands. [inferred: R10]

#### The owner question queue and topics

C108. The service plan's design sketch has a session pick up the owner's queued answer on the session's next pull. evidence: E18. [decided: project-orchestrator orchestration-service plan]

C109. The owner question queue therefore depends on the task-pull loop for the pickup of answers. [inferred: R11]

C110. The push design for topics rests on channels, whose availability on the web surface is unverified under risk R11, MCP surface constraints. evidence: E7. [decided: project-orchestrator Risk register]

### (d) Proposed changes to the service's roadmap

<!-- part: changed for every claim under (d). Each claim names the alternative it was chosen over. -->

C111. The task-pull loop, node P2-N005, becomes the next service chunk, chosen over keeping node P2-N003, owner questions and the plan view, next. [proposed: this IR]

C112. The task-pull loop chunk carries per-task claims, role-aware identity, the branch-name fallback claim and claim release, chosen over task claims without a fallback protocol. [proposed: this IR]

C113. Node P2-N003, owner questions and the plan view, splits into two nodes, the web view's first version and the owner question queue, chosen over one chunk carrying both. [proposed: this IR]

C114. The web view's first version is specified against the comprehension model after node P3-N002's first child, the five-resource slice, is done, chosen over specifying the view against the Plan register now. [proposed: this IR]

C115. The web view's first version may run in parallel with the task-pull loop, chosen over waiting for the task-pull loop to close. [proposed: this IR]

C116. The web view's first version is a read-only view built from commits, drilling to node and task only, chosen over the design sketch's updates as sessions publish. [proposed: this IR]

C117. The service plan's design-sketch line on updates as sessions publish is struck, with live session status moved to topics. [proposed: this IR]

C118. The owner question queue follows the pilot, chosen over building the queue before the pilot while gate decisions in chat still work. [proposed: this IR]

C119. The web view's scheduling and delegation decisions arrive with the owner question queue, chosen over write actions in the web view's first version. [proposed: this IR]

C120. The roadmap document places the pilot on methodology-tools after the task-pull loop and the web view's first version, chosen over piloting on the task-pull loop alone. [proposed: this IR]

C121. Service chunk 5 keeps the parent plan's order, the orchestrator's own orchestration moving onto the service before the pilot runs on methodology-tools, chosen over piloting first. [proposed: this IR]

C122. Multi-project plan state is built inside node P2-N006, migration and pilot, chosen over building multi-project state within the task-pull loop. [proposed: this IR]

C123. Topics, node P2-N004, move after the pilot, built only if the pilot shows a coordination need, chosen over topics before the pilot. [proposed: this IR]

C124. A new service node after the pilot adds a remote MCP connector for surfaces without a repository clone, chosen over adding the connector before the task-pull loop. [proposed: this IR]

C125. The remote connector node first verifies which client authentication the connectors of Claude web, Claude Mobile and Claude Duet accept, chosen over assuming the bearer token works there. [proposed: this IR]

C126. Agents on surfaces without a repository clone get read, question and delegation tools only, keeping the write model, chosen over giving the service a repository write credential. [proposed: this IR]

C127. An agent on a surface without a repository clone delegates a repository-writing task by placing the task for a cloned session to claim through the task-pull loop. [proposed: this IR]

C128. Until the remote connector exists, the web view, opened in a browser, serves the owner on any device, chosen over moving the connector ahead of the web view. [proposed: this IR]

C129. The fallback wording of node P1-N014, role contracts adopt the v1.5.0 conduct rules, lands before the pilot, chosen over leaving risk R17 open through the pilot. [proposed: this IR]

C130. The plan-model amendment recording where verification evidence lands follows the pilot, chosen over amending the plan model before any drill-down needs the amendment. [proposed: this IR]

C131. A scheduled check for breakage between deploys stays in the Backlog through the pilot, chosen over building monitoring now. [proposed: this IR]

C132. One housekeeping task corrects the lagging service and orchestrator records this review found, chosen over correcting each record when its node next touches the record. [proposed: this IR]

C133. The proposed service order after chunk 1 is: the task-pull loop with the web view's first version in parallel, chunk 5's migration and pilot, the owner question queue, topics if needed, the remote MCP connector. [proposed: this IR]

### (e) Corrections the vision IR needs

<!-- part: changed for every claim under (e). -->

C134. Vision claim C21, completing service chunk 1 as the next step, is fulfilled: service chunk 1 closed on 2026-09-16. [proposed: this IR]

C135. Vision claim C31 should read: the service reads plan state from git and validates the plan-state updates a session commits. [proposed: this IR]

C136. Vision claim C59 should read: node P2-N010, plan-state update with an advisory lease, is done in the Plan register. [proposed: this IR]

C137. Vision claim C97 should read: node P2-N010 of service chunk 1, plan-state update under the advisory lease, is done. [proposed: this IR]

C138. Vision claim C98 should read: node P2-N011, degrade to git-only with enlistment documentation, reached done on 2026-09-07. [proposed: this IR]

C139. Vision claim C55 should read: service chunk 1 closed on 2026-09-16, with the plan-state update and the degrade to git-only done. [proposed: this IR]

C140. Vision claim C69 should name the write model, decision 3 of the P2-N002 plan, as the source of the session-only writer rule, in place of standing constraint 1. [proposed: this IR]

C141. Vision evidence E2 should cite the Plan register with service chunk 1, node P2-N002, and all five of its children done. [proposed: this IR]

C142. Vision claims C65, C66, C67, C90, C92 and C93, on enlistment and surfaces without a repository clone, remain true on 2026-10-29. [inferred: R12]

## Relations

R1. C85 depends-on C33 because every enlistment condition starts from a `.mcp.json` in a cloned repository.

R2. C87 depends-on C22 because the session applies the returned edit in the session's own checkout.

R3. C90 depends-on C88 because standing constraint 1 names no writer, while the write model in C89 forbids a service write credential.

R4. C91 depends-on C36 because the recorded surfaces are cloud sessions and the owner's local machine only.

R5. C92 depends-on C7 because the only routes are /mcp and /health.

R6. C93 contradicts C68 because updates as sessions publish do not come from commits.

R7. C94 depends-on C67 because the vision makes the drill-down wait on the plan-model amendment.

R8. C95 depends-on C15 because none of the six tools hands out or claims a task.

R9. C99 depends-on C13 because the service reads one project, and methodology-tools is a second project.

R10. C107 depends-on C101 because the comprehension plan expects node P2-N003 to change against the comprehension model.

R11. C109 depends-on C108 because the queued answer reaches git only through a session's pull.

R12. C142 depends-on C85 because enlistment still needs a clone, and C86 shows no remote connector exists.

R13. C58 contradicts C79 because the comprehension plan names Allegro as the pilot, and the owner named methodology-tools.

R14. C79 refines C59 because the owner's naming supplies the project the service plan leaves open.

R15. C52 contradicts C2 because the service Backlog lists done nodes as upcoming.

R16. C78 refines C89 because the rule the vision calls standing constraint 1 is the write model's.

R17. C111 depends-on C72 because the vision places the task-pull loop before topics.

R18. C111 depends-on C109 because the owner question queue cannot deliver answers before the task-pull loop exists.

R19. C111 depends-on C61 because the task-pull loop is the vision's core agent behaviour, querying for and claiming tasks.

R20. C112 depends-on C97 because the open Backlog items name what a claim protocol must cover.

R21. C112 depends-on C96 because handing out a task in a role needs the role's identity.

R22. C113 depends-on C109 because the queue needs the task-pull loop, while the web view does not.

R23. C114 depends-on C107 because a view specified now would be re-specified once the comprehension model lands.

R24. C114 depends-on C102 because the comprehension model extends the planning/execution model the web view renders.

R25. C115 depends-on C113 because a read-only web view uses no output of the task-pull loop.

R26. C116 depends-on C68 because the vision binds the web view to commits.

R27. C116 depends-on C66 because the vision limits the first version's drill-down to node and task.

R28. C117 depends-on C93 because the struck line is the one contradicting the commits-only rule.

R29. C118 depends-on C82 because chat gates under the v1 process serve the pilot, so the queue waits for need.

R30. C119 depends-on C109 because a scheduling or delegation decision is an owner answer, which reaches git through a pull.

R31. C120 depends-on C73 because the vision leaves the pilot's place to the roadmap document.

R32. C120 depends-on C65 because the pilot should show the owner status through the web view, the primary human surface.

R33. C121 depends-on C80 because the orchestrator's adoption by construction happens inside service chunk 5.

R34. C121 depends-on C81 because the orchestrator's migration is not the pilot and precedes the pilot in the parent plan.

R35. C122 depends-on C100 because the orchestrator Backlog already places multi-project state with node P2-N006.

R36. C122 depends-on C99 because the pilot is the first need for a second project.

R37. C123 depends-on C110 because the push design for topics rests on an unverified channel.

R38. C123 depends-on C82 because the need for topics is unshown before the pilot.

R39. C124 depends-on C77 because the vision names the remote connector as the route for those surfaces.

R40. C124 depends-on C82 because no orchestrated work yet needs an agent on a surface without a repository clone.

R41. C125 depends-on C86 because the bearer token is the service's only authentication today.

R42. C126 depends-on C87 because those surfaces have no checkout to apply an edit in.

R43. C126 depends-on C90 because a service write credential is the alternative that breaks the write model.

R44. C127 depends-on C83 because the vision lets one agent delegate to another.

R45. C127 refines C126 because delegation is how those surfaces get repository work done.

R46. C128 supports C124 because the owner's status need on mobile is met without the connector.

R47. C129 depends-on C51 because node P1-N014 carries the R17 mitigation.

R48. C130 depends-on C67 because the amendment must precede only the drill-down, which the first version omits.

R49. C131 depends-on C45 because the fallback rule keeps an outage from stopping work.

R50. C132 depends-on C52 because the lagging records of cluster G1 are the task's scope.

R51. C133 refines C111 because the order collects claims C111 to C131 into one sequence.

R52. C134 depends-on C1 because chunk 1 reached done on 2026-09-16.

R53. C136 depends-on C2 because node P2-N010 is done in the Plan register.

R54. C138 depends-on C3 because node P2-N011 reached done on 2026-09-07.

R55. C139 depends-on C1 because chunk 1 closed when its children were done.

R56. C135 depends-on C20 because the service now validates updates under the write model.

R57. C140 depends-on C89 because the write model, not standing constraint 1, keeps write credentials out of the service.

R58. C141 depends-on C2 because the cited register now shows all five children done.

R59. C137 depends-on C2 because node P2-N010 is done in the Plan register.

## Evidence

E1. project-orchestrator docs/plan-register.md lines 21 and 26 to 46: P2-N002, P2-N007 to P2-N016 `[done]`; P2-N003 to P2-N006 `[identified]`; P1-N014 `[planned]`; P3-N002 `[planned]`.

E2. project-orchestrator docs/specs/p2-n002-service-skeleton.md, "Gate evidence, 2026-09-16": G1 ("connected · 6 tools"), G3, G4 (no repository write credential), I6 (cloud sessions and the owner's local machine); "Decisions for the gate", decision 12 (no role identity in chunk 1).

E3. project-orchestrator-service README.md: the six tools, MCP_PROJECT defaulting to majodali/project-orchestrator, the GitHub App with `contents: read`, the configuration table, and line 39 naming methodology v1.3.0.

E4. project-orchestrator-service src/planWriteTools.ts lines 1 to 34 (three-step write model, no cache), 66 to 68 (TTL default 600, clamp 30 to 3600), 276 to 482 (the four write-path tools); src/planReadTool.ts lines 165 to 178 (plan_read, SHA and fetch time).

E5. project-orchestrator-service src/auth.ts (bearer-token comparison against MCP_AUTH_TOKEN, no other scheme); README.md configuration table (MCP_AUTH_TOKEN unset refuses every /mcp call).

E6. project-orchestrator docs/plans/p2-n002-service-skeleton.md, "The write model", "Decisions for the gate" decisions 3, 4, 6 and 7, and "Gate outcome, 2026-08-26" (TypeScript/Node, ruling RU-008).

E7. project-orchestrator docs/open-risks.md: R10 (illegal transition and stale baseline refused, 2026-09-07); R11 (channels push unverified on the web surface); R12 (closed 2026-09-07, both cases on both surfaces, residual exposures); R17 (open, mitigation in P1-N014's scope).

E8. project-orchestrator-service src/planRegister/dynamoLeaseBackend.ts lines 1 to 23: one DynamoDB item, conditional writes, expiry enforced by `expiresAt < :now` at acquire time.

E9. project-orchestrator docs/process/enlistment.md, sections "What enlisted means", "Confirming enlistment worked" and "The fallback rule".

E10. project-orchestrator-service template.yaml: line 166 (nodejs22.x), line 186 (one AWS::Serverless::Function), lines 284 and 312 (two DynamoDB tables), lines 493 to 504 ("ANY /mcp" and "GET /health" routes).

E11. project-orchestrator docs/plans/p2-n012-deploy-from-ci-on-merge.md, sections "Outcome", "Credentials and the two workflows", "Promotion and rollback" and "What this node does not cover" (one stack, two aliases, two tables; no monitoring).

E12. project-orchestrator .mcp.json (type http, Bearer `${MCP_AUTH_TOKEN}`, timeout 30000) and .claude/settings.json (`enableAllProjectMcpServers: true`).

E13. project-orchestrator docs/backlog.md: line 755 (P2-N002 done 2026-09-16); line 2336 (P2-N011 done 2026-09-07); Upcoming line 400 (service support for the comprehension model) and lines 2361, 2367, 2371, 2413, 2417 and 2432.

E14. project-orchestrator-service .github/workflows/checks.yml (on pull_request; build, lint, test, SAM validate), deploy.yml (on push to main; `id-token: write`; OIDC preflight, deploy, preprod, smoke test, promote) and oidc-preflight.yml (workflow_dispatch only).

E15. project-orchestrator-service scripts/smoke-test.sh: checks 1/3 (/health), 2/3 (tools/list) and 3/3 (plan_lease_acquire and plan_lease_release).

E16. project-orchestrator-service docs/runbook.md, "The deploy, smoke, and promote pipeline": run 34045920168, 1m40s, 2026-09-06, live promoted from version 1 to 2.

E17. project-orchestrator-service docs/backlog.md: Upcoming lines 680 to 692 (P2-N011 and deploy-on-merge CI listed as upcoming); Completed lines 514, 628, 629 and 670 ("chunk 2" labels on P2-N012 work).

E18. project-orchestrator docs/plans/orchestration-service.md: lines 60 to 85 (standing constraints 1 to 5); lines 99 to 107 (answers picked up on the next pull; UI updated as sessions publish); lines 116 to 157 (chunks 1 to 5; line 154, an owner-chosen portfolio project).

E19. project-orchestrator-service docs/mcp-enlistment.md, header comment line 6 and "Committing this" (the coordinating repository not enlisted).

E20. project-orchestrator-service docs/classification.md line 8: pinned methodology version 1.6.0.

E21. project-orchestrator-service docs/runbook.md, "Step 8" table (plan_read cold and warm not yet measured) and "Running cost" (not yet measured).

E22. project-orchestrator docs/plans/comprehension-and-continuous-implementation.md lines 471 to 479, "What this does to the existing plan": P1-N006 with Allegro as the pilot; P2-N003 likely re-specified; both confirmed subject to change, 2026-09-16.

E23. project-orchestrator docs/plans/p3-n002-comprehension-model.md: line 3 (Status: draft); "Outcome" (works with no service running); "Approach" (flat resources, node-to-resource edges, docs/project-model.md); "Gate record, 2026-10-29" (accepted; T043 dispatched).

E24. project-orchestrator docs/specs/p3-n001-comprehension-and-continuous-implementation.md lines 341 to 350: any hosted view is node P2-N003's territory; service support for the model is a later service chunk.

E25. project-orchestrator docs/rulings.md line 209: RU-021, the planning/execution model as the source of progress truth, K-003 amended project by project.

E26. methodology docs/vision.ir.md: claims C3, C4, C9, C10, C22, C38, C39, C50, C54, C56, C58, C60, C69, C70, C78, C79, C80, C85, C89, C90, C96, C99, C100, C101, ratified by the owner.

## Asks

<!-- Gate style: "go" adopts every default; the owner overrides by number. -->

A1. Decide whether the reasoning role writes the roadmap document (vision claim C58) now, from this review. Default: yes; the reasoning role drafts the roadmap document's IR next, carrying the decisions below, for the owner to edit. Depends: C74, C133.

A2. Make the task-pull loop, node P2-N005, the next service chunk, with per-task claims, role-aware identity and the fallback claim protocol. Default: adopt. Override: keep node P2-N003 next. Depends: C111, C112, C95, C96, C97.

A3. Split node P2-N003, owner questions and the plan view, into the web view's first version and the owner question queue, specifying the view against the comprehension model, node P3-N002, after its five-resource slice. Default: adopt, with the view allowed in parallel with the task-pull loop. Depends: C113, C114, C115, C101, C107.

A4. Make the web view's first version read-only, commits-only and drilling to node and task, and strike the design sketch's live-update line. Default: adopt. Depends: C116, C117, C93.

A5. Place the owner question queue, carrying the web view's scheduling and delegation decisions, after the pilot. Default: adopt. Override: before the pilot. Depends: C118, C119, C109.

A6. Place the pilot on methodology-tools after the task-pull loop and the web view's first version, keeping service chunk 5's order of migration then pilot, with multi-project plan state built inside node P2-N006, migration and pilot. Default: adopt. Depends: C120, C121, C122, C99.

A7. Move topics, node P2-N004, after the pilot, built only on a shown need. Default: adopt. Override: keep topics before the pilot, after the task-pull loop. Depends: C123, C110.

A8. For surfaces without a repository clone, keep the write model, add a remote MCP connector node after the pilot that starts by checking which authentication those surfaces accept, and give those surfaces read, question and delegation tools only. Default: adopt. Override: give the service a scoped repository write credential. Depends: C124, C125, C126, C127, C128, C90.

A9. Land the fallback wording of node P1-N014, role contracts adopt the v1.5.0 conduct rules, before the pilot. Default: adopt. Depends: C129, C50.

A10. Schedule the plan-model amendment recording where verification evidence lands after the pilot. Default: adopt. Depends: C130, C94.

A11. Keep the scheduled check for breakage between deploys in the Backlog through the pilot. Default: adopt. Depends: C131, C48.

A12. Correct the vision IR as group (e) states, then re-render docs/vision.md through the paraphraser and the stranger rounds under W-009, the IR-first rule. Default: adopt. Depends: C134, C135, C136, C137, C138, C139, C140, C141, C142.

A13. Dispatch one housekeeping task correcting the lagging records in the service and orchestrator repositories, including naming methodology-tools as the pilot in the comprehension plan and the service plan. Default: adopt. Depends: C132, C52, C53, C54, C55, C56, C57, C58, C59, C60.

A14. Ratify or strike the three proposed terms: surface without a repository clone, remote MCP connector, roadmap document. Default: ratify. Depends: T27, T28, T29.
