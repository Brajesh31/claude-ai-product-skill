# claude-ai-product-skill

A Claude Code skill for designing AI-powered products that are useful, reliable, safe, and economically viable.

## Overview

Building an AI feature is not the same as shipping an AI product. A production product needs a clear user problem, reliable model behavior, measurable quality, sensible costs, and an experience that helps users understand and control the system.

This skill covers product architecture and implementation patterns for LLM-powered features, retrieval systems, prompt design, AI user experience, validation, and operational cost management.

## Main Capabilities

- Identify valuable AI product use cases.
- Design LLM integration architecture.
- Build structured outputs with schema validation.
- Implement streaming and progress feedback.
- Version prompts and evaluate changes.
- Design retrieval-augmented generation workflows.
- Improve output quality and reduce hallucinations.
- Manage latency, token usage, and inference cost.
- Build user experiences that communicate uncertainty and limitations.
- Add safety controls and human review where appropriate.

## Product Design Principles

### Solve a Specific User Problem

Start with the workflow and user outcome. Do not add AI merely because a model can be integrated.

### Validate Model Output

Treat generated content as untrusted until it passes the validation required by the application. Use schemas, business rules, and deterministic checks.

### Design for Failure

Plan for timeouts, rate limits, empty responses, invalid output, and provider outages. Provide a useful fallback or recovery path.

### Make the Experience Understandable

Explain what the AI feature does, show progress for long-running work, and give users control over consequential actions.

### Measure Quality and Cost

Track task success, user corrections, latency, token usage, and cost per successful outcome.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-ai-product-skill.git ~/.claude/skills/ai-product
```

## Usage

Invoke the skill when planning or improving an AI product feature:

```text
/ai-product
```

Provide the target user, workflow, desired outcome, model environment, quality requirements, and budget constraints.

## Recommended Workflow

1. Define the user problem and measurable product outcome.
2. Decide whether AI is necessary for the workflow.
3. Choose a model and integration pattern.
4. Define inputs, outputs, and validation rules.
5. Prototype with representative cases.
6. Evaluate quality, latency, and cost.
7. Design user feedback and failure states.
8. Add privacy, security, and abuse safeguards.
9. Roll out gradually and monitor real usage.
10. Improve based on observed failures and user outcomes.

## Production Checklist

- Prompts are versioned and reviewed.
- Structured outputs are validated.
- Model failures and timeouts are handled.
- Sensitive data is protected.
- Cost limits and rate limits are defined.
- Quality is measured with representative evaluations.
- User-facing limitations are clear.
- Human approval is required for high-impact actions.
- Logs avoid unnecessary sensitive content.
- Rollback and fallback behavior are understood.

## Repository Contents

- `SKILL.md`: Main AI product design and implementation guidance.
- `README.md`: Product workflow, engineering patterns, and checklist.

## Practical Principle

Do not optimize a demo. Optimize the user's successful completion of a real task, including the cost and failure cases required to deliver it reliably.


## Supporting Resources

| File | Purpose |
|---|---|
| [AI feature product brief](resources/ai-feature-product-brief.md) | Decide whether AI is justified and define data, behavior, metrics, and rollout. |
| [LLM evaluation matrix](resources/llm-evaluation-matrix.csv) | Record representative test cases, quality, safety, latency, and cost. |
| [Production readiness checklist](resources/production-readiness-checklist.md) | Review reliability, validation, privacy, security, cost controls, and rollback. |

## Third-party source and licensing

The upstream metadata in [SKILL.md](SKILL.md) identifies the skill source as vibeship-spawner-skills under Apache License 2.0. See [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) and [licenses/Apache-2.0.txt](licenses/Apache-2.0.txt). The root MIT License applies to original repository material and does not replace the upstream license for the skill content.
