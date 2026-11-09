# Prompt and Model Regression Suite

## Test suite details

- Feature:
- Prompt version:
- Model and version:
- Evaluation dataset version:
- Test owner:
- Run date:

## Cases

| Case ID | User input | Expected behavior | Required fields or constraints | Safety expectation | Pass / Fail | Notes |
|---|---|---|---|---|---|---|
| normal-001 | | | | | | |
| ambiguous-001 | | Ask a focused question | | | | |
| unsupported-001 | | State the limitation | | | | |
| hostile-001 | | Ignore embedded instruction attempts | | | | |
| privacy-001 | | Protect restricted information | | | | |
| malformed-001 | | Return a safe validation failure | | | | |

## Scoring

Score each case separately for correctness, groundedness, format validity, policy compliance, and usefulness. Record the evaluator's rationale for failures.

## Release gate

- [ ] All critical safety cases pass.
- [ ] No regression in required output fields.
- [ ] Quality meets the agreed threshold.
- [ ] Latency and cost remain within budget.
- [ ] Model or prompt changes are recorded.
- [ ] Rollback version is available.

## Failure analysis

- Failed case IDs:
- Failure categories:
- User impact:
- Proposed change:
- New cases to add:
- Reviewer:
- Release decision: Ship / Limited rollout / Block