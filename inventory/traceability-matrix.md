# Traceability matrix

One language for requirement, implementation, proof, and decision.

Requirement source: `<contract, backlog, or specification>`.

A stage starts after the previous decision is `passed`. Inside a stage, API evidence comes before the UI journey. A branch does not block the critical path.

Critical path: `<one sentence, from the first precondition to the outcome>`.

| Stage | Starts when | What becomes valid | Ids | Exits when |
|---|---|---|---|---|
| 1. `<name>` | — | `<first precondition>` | QA-001 | `<observable exit>` |
| 2. `<name>` | Stage 1 | `<next capability>` | QA-002 | `<observable exit>` |

| Id | Requirement | Task | Commit | Pull request | Test | Evidence | Decision |
|---|---|---|---|---|---|---|---|
| QA-001 | `requirements/<feature>.md` | | | | | | implemented |
| QA-002 | `<clause or story>` | `<work item>` | `<sha>` | `#<n>` | `<test file>` | `evidence/stage-2/` | passed |

Decision is `implemented`, `passed`, `failed`, or `deferred`.

A wide requirement counts only the slice named in the stage. A deferred slice keeps its impediment and moment in the case. The row stays `deferred` until that moment.
