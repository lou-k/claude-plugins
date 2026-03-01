---
name: write-scope-complexity
description: Writes or updates the "Scope and Complexity" section of a brag doc entry. Invoke when you have evidence of a project's scale, team size, systems touched, or operational complexity.
user-invocable: false
---

# Write: Scope and Complexity

## What to capture

Scale and complexity indicators that convey seniority and breadth. Cover each where evidence exists:

- **Team size / cross-functional partners** — engineers, PMs, designers, data scientists, external vendors
- **Systems scale** — data volume, QPS, model size, region count, storage footprint
- **Integration surface** — number of services, platforms, APIs, customer segments touched
- **Operational maturity** — SLOs, incident management, runbooks, monitoring, on-call

## Exclude

- **Inflated numbers without evidence** — don't round up or estimate generously; use what the evidence states
- **Excessive technical detail** — "3 Kafka clusters, 12 topics, 47 partitions" is too granular unless the complexity itself is the point. Prefer "hundreds of millions of events/day across 3 Kafka clusters"

## Style

Bullet list or short prose, ≤6 items. Be concrete: numbers, named systems, team counts. This section should let a reader gauge the project's weight without reading the rest of the entry.

## Output

Return only:

```markdown
## Scope and Complexity

<bullets or prose>
```
