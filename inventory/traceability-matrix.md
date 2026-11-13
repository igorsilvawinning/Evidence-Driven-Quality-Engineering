# Traceability matrix

Source of requirements: `<contract, backlog, or specification, with the reference>`.

`covered` means a test file exists for part of the requirement. It does not mean the test ran or the clause is accepted. `no evidence` means there is no test that demonstrates the criterion. Add epic or feature ids in the existing column when they exist. Do not invent them.

## Validation order

A stage starts when the previous one passed. Inside a stage, the API proof comes before the UI journey. An optional branch does not block the happy path.

The critical path of this product is: `<one sentence, from the first precondition to the delivered outcome>`.

| Stage | Starts when | What becomes valid | Ids | Exits when |
|---|---|---|---|---|
| 1. `<name>` | — | `<the first precondition>` | QA-001 | `<observable exit>` |
| 2. `<name>` | Stage 1 | `<next capability>` | QA-002 | `<observable exit>` |

Replace the two example rows with the real path. Keep one row per stage.

| Id | Source | Clause or epic | Acceptance criterion | Level | Priority | Evidence | State |
|---|---|---|---|---|---|---|---|
| QA-001 | `<contract or backlog>` | `<clause>` | `<what must be true>` | journey | stage 1 | | no evidence |
| QA-002 | `<contract or backlog>` | `<clause>` | `<what must be true>` | api | stage 2 | `<path to the test file>` | covered |

Level is one of `api`, `journey`, `load`, `security`, `usability`. State is one of `no evidence`, `covered`, `passed`, `failed`, `deferred`.

A wide row counts only the slice named in the stage. The rest of the criterion is not an entry gate. When a slice is deferred, the evidence cell names the impediment and the moment, and the state stays `deferred` or `covered` for the whole row.
