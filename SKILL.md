---
name: ai-product
description: Plan and ship production-ready AI product features with LLMs, retrieval, structured outputs, evaluation, user experience, safety, and cost controls. Use when designing or improving an AI-powered product.
license: MIT
---

# AI Product Engineering

## Objective

Turn a real user problem into a reliable AI-powered product capability. Treat the model as one component in a broader system that includes data, deterministic logic, user experience, evaluation, security, operations, and economics.

Do not recommend AI merely because a model can perform the task. First decide whether model-based behavior improves the user's outcome enough to justify its complexity.

## Product discovery

Clarify:

1. Target user and job to be done.
2. Current workflow and its failure points.
3. Measurable outcome the feature should improve.
4. Inputs, expected outputs, and acceptable uncertainty.
5. Consequence of an incorrect or incomplete answer.
6. Data permissions, privacy constraints, and retention needs.
7. Latency, availability, and cost limits.
8. Human review or override requirements.

Separate confirmed facts from assumptions. Identify what must be tested before implementation.

## Decide where AI belongs

Use deterministic code for arithmetic, access control, transaction rules, validation, permissions, and predictable transformations.

Use a model where flexible language understanding, summarization, classification, generation, or reasoning provides a measurable benefit.

Prefer a hybrid design: deterministic orchestration around a bounded model call. Do not delegate authorization or irreversible decisions to model judgment.

## Select an integration pattern

### Direct model call

Use for bounded tasks with a clear request and response. Define the input contract, output contract, timeout, retry policy, and fallback.

### Structured output and tool calling

Use schema-constrained output when the application needs predictable fields or controlled function calls. Validate every response before using it. A valid JSON shape does not prove that its content is correct or safe.

### Retrieval-augmented generation

Use retrieval when an answer must be grounded in a changing or private knowledge collection.

A typical flow is:

1. Ingest approved documents and retain access metadata.
2. Normalize, split, and index content using a strategy suited to document structure.
3. Apply user and tenant access filters before retrieval.
4. Retrieve candidate passages and rank them for relevance.
5. Pass only the needed context to the model.
6. Generate an answer that distinguishes supported facts from missing information.
7. Retain document identifiers for traceability and re-check permissions at read time.

Test retrieval quality separately from answer generation. More context is not automatically better.

### Streaming interaction

Use streaming when a task takes long enough that visible progress improves the experience. Define what happens when the stream is interrupted, cancelled, or returns partial output. Do not display unvalidated content as a completed result.

### Background processing

Move long-running work out of the synchronous request path. Use durable task state, bounded retries, cancellation, and a clear status endpoint or notification flow.

## Prompt and context design

- Give prompts a single clear objective.
- Specify the intended audience, output shape, and constraints.
- Separate trusted instructions from user-provided and retrieved content.
- Treat documents and tool responses as untrusted data.
- Include examples only when they resolve a real ambiguity.
- Keep retrieved context relevant and within a measured token budget.
- Version prompts and model settings.
- Test changes against a regression set before rollout.
- Avoid placing secrets or unnecessary personal data in prompts.

## Output validation

Apply the validation needed for the task:

- Schema and type checks.
- Required-field and range checks.
- Business-rule validation.
- Authorization checks outside the model.
- Evidence or grounding checks for factual claims.
- Safe rendering and sanitization.
- Human review for high-impact or ambiguous results.

When validation fails, request a correction, retry within a small limit, or return a safe fallback. Do not silently coerce invalid output into a success state.

## User experience

Users should understand:

- What the feature can and cannot do.
- Whether the result is generated, retrieved, or deterministic.
- How long the operation may take.
- How to correct or refine the result.
- When information is uncertain or incomplete.
- Which actions require confirmation.
- How to report an issue or reach a manual path.

Do not manufacture confidence scores or precision estimates that have not been calibrated.

## Safety, privacy, and abuse prevention

- Minimize the data sent to model providers.
- Enforce tenant and document permissions before retrieval.
- Protect prompts and tool calls from prompt injection.
- Keep model output away from direct execution unless an independent validation and authorization layer approves it.
- Apply request limits, spend limits, and abuse detection.
- Redact credentials and unnecessary personal data from logs.
- Define data deletion and retention behavior.
- Require user approval for external, financial, or destructive actions.

## Evaluation

Create a representative test set before optimizing prompts. Include:

- Common user requests.
- Missing and ambiguous details.
- Rare but important edge cases.
- Incorrect or adversarial input.
- Unsupported questions.
- Sensitive data and permission boundaries.
- Provider outages and malformed responses.

Measure task success, factual correctness, groundedness, format validity, refusal quality, user correction rate, latency, and cost per successful task. Review failures by category rather than relying on a single aggregate score.

## Reliability and operations

- Set request timeouts and bounded retries.
- Handle rate limits and provider outages.
- Use idempotency for operations with side effects.
- Add fallback behavior for unavailable or low-confidence paths.
- Monitor latency percentiles, error rates, quality indicators, and spend.
- Run regression tests after model, prompt, data, or tool changes.
- Use gradual rollout and define rollback triggers.
- Preserve privacy when collecting traces and feedback.

## Cost and performance

Estimate total cost per successful user outcome, not only the price of one model call. Include retrieval, reranking, tools, retries, background jobs, storage, and failed requests.

Reduce cost by removing unnecessary context, selecting a model appropriate to the task, caching only safe reusable results, and using deterministic logic for predictable work. Measure quality again after every optimization.

## Required deliverable

For a product design or implementation request, provide:

1. User problem and measurable success criteria.
2. Decision on whether AI is appropriate.
3. Architecture and data flow.
4. Model, prompt, retrieval, and tool contracts.
5. Output validation and failure behavior.
6. Privacy, security, and approval controls.
7. Evaluation plan and acceptance thresholds.
8. Latency and cost model.
9. Rollout, monitoring, and rollback plan.

A demo is not production-ready until quality, safety, reliability, and cost have been measured against the intended use case.