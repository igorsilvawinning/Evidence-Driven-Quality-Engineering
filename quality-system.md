# Operating rules

A release moves when the current stage has a decision backed by evidence, and every deferred row names an impediment and a moment.

## States

| State | Meaning |
|---|---|
| implemented | A test file or the feature code exists. Nothing has been proved yet |
| passed | The case ran and the evidence matches the criterion |
| failed | The evidence contradicts the criterion. Open a work item |
| deferred | The proof cannot run now. The impediment and the moment are written |

## Channels

When the product has a UI and an API, a stage uses three channels: the automated test, the browser, and the HTTP collection. Load, security, exploration, and production observation are extra channels, stored in `evidence/`.

## Where an assistant acts

The assistant drafts. A person accepts the decision.

| Input | Assistant output | File |
|---|---|---|
| A feature note | Acceptance criteria, edge cases, business risks, open questions | `requirements/<feature>.md` |
| A requirement or a deferred item | Impact, probability, priority | `risks/RSK-nnn.md` |
| A new `QA-nnn` | Positive, negative, boundary, and exploratory cases | `cases/` for that id |
| Tool output (test runner, collection, pipeline, coverage) | The stage report, citing the evidence paths | `reports/` |

The assistant does not invent a commit, a pull request, or a test path. Those fields stay empty until the repository has them.

## Activities

| Activity | Record |
|---|---|
| Planning | `inventory/traceability-matrix.md`, `inventory/next-steps.md` |
| Requirement check | one matrix row |
| Functional, exploratory, integration | the case, then `evidence/` |
| Regression | re-run automated proof of closed stages before the next decision |
| Automation | the test file. If the pipeline does not run it, that is a process gap on the row |
| Performance, security, production | `evidence/load`, `evidence/security`, `evidence/production` |
| Release | the report for that stage, with the commit and the pull request filled in |
