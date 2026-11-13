# Quality folder — template

Copy this folder into a project and rename it `Q&A`. Fill the placeholders. Keep the method. Delete the examples that do not apply.

The folder is the quality record for the whole development cycle. Finding a defect is one outcome. The others are: a business requirement is tied to evidence, every activity closes the same way, a risk that cannot be exercised yet has an impediment and a time, and the development process improves when the evidence shows a method gap.

## How to start

1. Write the product's critical path as ordered stages in `inventory/traceability-matrix.md`. A later stage starts only after the previous one has evidence.
2. Give each acceptance criterion an id: `QA-001`, `QA-002`, and so on.
3. For the stage you are about to run, write the case in `cases/`.
4. Run three channels whenever the product has a UI and an API: the automated test, the browser, and the HTTP collection.
5. Store the result in `evidence/`. A screenshot without the id and the expected result does not count.
6. Close the stage in `reports/`. If something failed, open a work item. Do not change product code in the middle of the proof.
7. Before accepting the next stage, re-run the automated tests of the stages already closed.

The quality system, the activity map, and the closure standard are in `quality-system.md`.

## Layout

```text
Q&A/
  README.md
  quality-system.md
  inventory/
    traceability-matrix.md
    next-steps.md
  cases/
    stage-1/
      QA-001.md
  evidence/
    api/                  automated output and the HTTP collection
    stage-1/              screenshots for that stage
    journeys/
    load/
    security/
    production/
    usability/
  reports/
    template.md
```

## File rules

- The matrix id appears in the evidence file name and in the report.
- Do not copy product source into this folder. Point at the test file path.
- Do not store passwords, tokens, or customer data.
- `covered` means a test file exists. It does not mean the test was run or the requirement is accepted.
- `deferred` requires an impediment and the moment the proof becomes possible.
