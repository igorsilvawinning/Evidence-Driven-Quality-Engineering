# Evidence

A result of an execution, tied to a `QA-nnn`.

| Folder | What to store |
|---|---|
| `api/` | Automated test output and the HTTP collection for the same criterion |
| `stage-<n>/` | Screenshots of the browser and the collection for that stage |
| `journeys/` | Exported journey video or image |
| `load/` | Load-test summary: thresholds, virtual users, duration |
| `security/` | Security proof that is not already inside a stage folder |
| `production/` | A dated note from the live environment: symptom and impact |
| `usability/` | Guided-session photo or video, with the script beside it |

File name: `QA-nnn-<date>-<result>`, with result `passed` or `failed`.

Do not store passwords, tokens, or full database exports.
