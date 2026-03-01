---
name: write-outcomes
description: Writes or updates the "Outcomes" section (Business / Engineering / ML-Model / Adoption-Scale) of a brag doc entry. Invoke when you have evidence of measurable results from a project.
user-invocable: false
---

# Write: Outcomes

## Structure

Four subsections, each a bullet list:

- **Business** — revenue, conversion, retention, churn, cost savings, time saved
- **Engineering** — latency, throughput, availability, infra cost reduction, developer velocity
- **ML / Model** — offline metrics (accuracy, F1, AUC), online metrics (uplift, precision@k), evaluation approach, monitoring/guardrails, drift handling
- **Adoption / Scale** — users, teams onboarded, queries/day, deployments/week, rollout footprint, reliability in production

## What makes a good outcome bullet

- **Metric with baseline and timeframe** preferred: "reduced p99 latency from 800ms to 120ms over 3 months"
- **Directional if no exact metric**: "cut manual review hours by roughly half"
- **Proxy metrics** when primary unavailable: tickets reduced, on-call pages, manual steps eliminated
- **Qualitative evidence** as last resort: exec quote, customer feedback, internal adoption signal

## Exclude

- **Team outcomes claimed as individual** — if the team shipped it, say "team achieved"; reserve "I" for the Contributions section. Outcomes can be team-scoped but must not inflate individual attribution
- **Metrics without context** — "F1 = 0.92" means nothing without baseline, task, or comparison
- **Unverifiable claims** — no "significantly improved" or "dramatically reduced" without a number or at least a directional comparison

## Style

Bullet list, ≤8 bullets total across all subsections. Omit empty subsections rather than writing "None." Each bullet: metric/result first, then brief context.

## Output

Return only:

```markdown
## Outcomes

### Business
- <bullet>

### Engineering
- <bullet>

### ML / Model
- <bullet>

### Adoption / Scale
- <bullet>
```
