# claude-ai-product-skill

A Claude Code skill for designing and delivering useful, safe, and economically sustainable AI product features.

## Capabilities

- AI use-case discovery and product validation.
- LLM integration and structured output design.
- Retrieval-augmented generation architecture.
- Prompt and context engineering.
- Streaming and background task experiences.
- Output validation, safety, and privacy controls.
- Evaluation, observability, latency, and cost optimization.
- Production rollout and rollback planning.

## Install

~~~bash
git clone https://github.com/Brajesh31/claude-ai-product-skill.git ~/.claude/skills/ai-product
~~~

## Use

~~~text
/ai-product
~~~

Provide the target user, current workflow, desired outcome, data requirements, model environment, quality threshold, latency target, and budget.

## Recommended process

1. Validate the user problem.
2. Decide whether AI is the right tool.
3. Define the system and data boundaries.
4. Specify prompt, model, retrieval, and output contracts.
5. Build an evaluation set.
6. Measure quality, safety, latency, and cost.
7. Add fallbacks and operational controls.
8. Roll out gradually and monitor real outcomes.

## Supporting materials

| File | Purpose |
|---|---|
| [AI feature product brief](resources/ai-feature-product-brief.md) | Decide whether AI is justified and define behavior, data, metrics, and rollout. |
| [LLM evaluation matrix](resources/llm-evaluation-matrix.csv) | Record test cases, quality, safety, latency, and cost. |
| [Production readiness checklist](resources/production-readiness-checklist.md) | Review reliability, validation, privacy, cost controls, and rollback. |
| [Prompt regression suite template](resources/prompt-regression-suite-template.md) | Maintain repeatable tests for prompt and model changes. |
| [AI inference cost model](resources/ai-inference-cost-model.csv) | Estimate model, retrieval, tool, retry, and total task costs. |

## Practical principle

Optimize for the user's successful completion of a real task. Model usage, token volume, and demo quality are not product outcomes by themselves.

## License

MIT. See the root [LICENSE](LICENSE).