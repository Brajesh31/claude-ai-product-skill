# AI Product Production Readiness Checklist

## Product value
- [ ] The feature solves a validated user problem.
- [ ] Success is measured by user outcomes, not model usage alone.
- [ ] A non-AI fallback or manual path exists where needed.
- [ ] The user understands the feature's limits.

## Model and prompt quality
- [ ] Prompts and model settings are versioned.
- [ ] Representative evaluation cases cover common and edge inputs.
- [ ] Structured outputs are schema-validated.
- [ ] Factual claims are grounded in approved sources where required.
- [ ] Regression tests run after model or prompt changes.
- [ ] Prompt injection and malicious retrieved content are tested.

## Reliability
- [ ] Timeouts, rate limits, retries, and provider outages are handled.
- [ ] Retries cannot duplicate external side effects.
- [ ] Streaming and partial responses have clear failure behavior.
- [ ] Fallback behavior is tested.
- [ ] Latency targets are measured at median and p95.

## Privacy and security
- [ ] Data collection is minimized.
- [ ] Sensitive data is not sent to a model without an approved basis.
- [ ] Logs redact secrets and unnecessary personal data.
- [ ] Tool access follows least privilege.
- [ ] High-impact actions require human confirmation.
- [ ] Retention, deletion, and access controls are documented.

## Cost and operations
- [ ] Cost per successful task is measured.
- [ ] Token, request, and spend limits are configured.
- [ ] Usage and quality dashboards exist.
- [ ] Alerts cover error rates, latency, and spend spikes.
- [ ] Rollback and incident response owners are named.

## Release decision
- Status: Ready / Limited rollout / Blocked
- Known gaps:
- Mitigation owner:
- Approver:
- Review date:
