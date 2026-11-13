# Quality system

Use this file as the frame. The stage list in `inventory/traceability-matrix.md` is the functional acceptance of the product's critical path. It does not replace the rest of the lifecycle.

A release to the client moves forward when the current stage is closed and every deferred risk in this file has an impediment and a moment.

## Closure standard

Every activity, functional or otherwise, closes with the same four fields.

| Field | Content |
|---|---|
| Criterion | What the business or the requirement demands, with a `QA-nnn` id once it is on the matrix |
| How | Automated test, browser, HTTP collection, exploration, load, security, or production observation. Repeat the first three whenever the UI and the API are in reach |
| Result | `passed`, `failed`, or `deferred`. `covered` means only that the test file exists |
| If deferred | The impediment, and the moment the proof becomes possible |

A `failed` result produces a report in `reports/` and a work item. Product code is not changed during the proof.

## Activities

| Activity | Purpose | Where it lives |
|---|---|---|
| Planning | Order, precondition, and what is out of scope | `inventory/traceability-matrix.md`, `inventory/next-steps.md` |
| Requirement validation | A requirement has evidence, not only a sentence | One matrix row and a case in `cases/` |
| Functional test | The behaviour a person sees | Browser, HTTP collection, and the stage case |
| Exploratory test | What the script did not foresee | A note on the stage case: what was tried and what appeared |
| Integration test | The API and its dependencies together | The project's automated API tests and `evidence/api/` |
| Regression | What already passed still passes after a change | Re-run the automated tests and the collection of every closed stage before accepting the next one |
| Automation | The proof the pipeline should repeat without a person | The test file in the repository. If the pipeline does not run it, record that as a process gap, not as a product defect |
| Performance | Latency and load of the product itself | A matrix row plus `evidence/load/` |
| Security | Session, permission, secrets, audit, and incident notification | The stages that own them, plus `evidence/security/` |
| Business acceptance | The critical path from the first precondition to the delivered outcome | The ordered stages |
| Production quality | What the live environment shows after delivery | `evidence/production/`, with the date and the symptom |
| Process improvement | The method was short or wrong, and the fix is in the method | A line in the section below |

## Deferred risks

Copy a row when a proof cannot be done in the current environment. Delete the example.

| Risk | Impediment | When it can be validated |
|---|---|---|
| Example: invalid credential cannot be shown while the dev bypass is on | The running environment ignores the credential header | When the app runs with the bypass off and a real issuer configured |

## Process rules

1. Close a stage on three channels when the product has a UI and an API: automated test, browser, and HTTP collection.
2. Write what cannot be proved now with an impediment and a moment. Do not mark the stage closed in silence.
3. Re-run the automated tests of closed stages before accepting the next stage.
4. If the pipeline does not run the tests this folder treats as the automated proof, say so in the stage report. That is a process gap.
