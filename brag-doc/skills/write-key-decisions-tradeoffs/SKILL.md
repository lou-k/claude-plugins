---
name: write-key-decisions-tradeoffs
description: Writes or updates the "Key Decisions & Tradeoffs" section of a brag doc entry. Invoke when you have evidence of architectural choices, build-vs-buy decisions, or tradeoffs made on a project.
user-invocable: false
---

# Write: Key Decisions & Tradeoffs

## What each bullet must contain

A bullet list. Each bullet should include **at least one** of:
- **Alternatives considered** — A vs B (and why one was rejected)
- **Tradeoff** — speed vs quality, build vs buy, cost vs latency, accuracy vs coverage
- **Risk and mitigation** — architectural bet + how it was de-risked (POC, phased rollout, A/B test, feature flag)
- **Rationale** — why this choice, grounded in constraints or evidence

This section demonstrates **senior-level judgment** — the reasoning behind choices, not just what was built.

## Exclude

- **Decisions without alternatives or rationale** — "chose Kafka" is not a tradeoff; "chose Kafka over SQS because we needed replay and multi-consumer fan-out" is
- **Task-level implementation choices** — "used Python 3.11" or "chose pytest" unless they were genuinely contested or consequential

## Style

Bullet list, ≤6 items. Each bullet is 1–3 sentences. Lead with the decision, follow with the reasoning. Include what you'd do differently if the evidence supports it.

## Output

Return only:

```markdown
## Key Decisions & Tradeoffs

- <bullet>
```
