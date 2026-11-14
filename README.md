# Evidence-Driven Quality Engineering

A validation operating system. The center is evidence, not the test.

```text
Requirement → QA-ID → Case → Execution → Evidence → Decision
```

The same chain reaches the code:

```text
Requirement → Task → Commit → Pull request → Validation → Evidence → Release
```

Copy this folder into a product. Fill the ids. Keep the chain. A decision without evidence does not close a stage.

## What a row must be able to point at

| Link | Example |
|---|---|
| Requirement | `requirements/feature-login.md` |
| QA-ID | `QA-001` |
| Task | the work-item id |
| Commit | `abc123` |
| Pull request | `#44` |
| Test | `Login.spec.ts` |
| Evidence | `evidence/stage-1/` |
| Decision | `passed`, `failed`, `deferred`, or `implemented` |

`implemented` means the code or the test file exists. It does not mean the behaviour was proved.

## Layout

```text
README.md
quality-system.md
requirements/          source text; an assistant drafts criteria, edges, risks, questions
risks/                 RSK-nnn with impact, probability, priority
inventory/             the matrix and the next stage
cases/                 the human script for one QA-ID
evidence/              proof: collection, screenshots, load, security, production
reports/               a short decision. Tools produce the raw output; a person or an assistant writes the summary
```

## Rules

- `deferred` is an artifact: impediment and the moment the proof becomes possible.
- Re-run the automated proof of closed stages before the next stage is accepted.
- Do not store passwords, tokens, or customer data.
- Product code is not changed during a proof. A `failed` decision opens a work item.
