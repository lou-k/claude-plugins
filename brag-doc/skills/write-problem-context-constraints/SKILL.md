---
name: write-problem-context-constraints
description: Writes or updates the "Problem, Context, & Constraints" section of a brag doc entry. Invoke when you have new context to add to the "Problem, Context, & Constraints" section for a brag doc entry.
user-invocable: false
---

# Write: Problem, Context, & Constraints

## Sub-topics (cover each where evidence exists)

1. **Problem** — What was broken/missing/costly? Who was affected? Baseline before this work.
2. **Why now** — Trigger, urgency, deadline, competitive/regulatory/technical forcing function. Cost of inaction.
3. **Background** — Prior work, inherited systems, decisions that set the stage.
4. **Success criteria** — Definition of done: targets, SLOs, KPIs, acceptance criteria.
5. **Constraints** — Technical (latency, throughput, data, infra), operational (on-call, compatibility), compliance (privacy, regulation), resource (timeline, staffing, budget), organizational (dependencies, approval gates).

## Exclude

- **Task logs / Jira exhaust** — only *why* the project existed, not activity lists
- **Vague urgency** — "pressure to ship" is not a constraint; "Q4 launch tied to contract renewal" is
- **Implementation detail** — capture the constraint, not the design ("200ms p99 budget," not the architecture)

## Style

Write **coherent prose**, not a checklist. Be specific ("Q3 VP mandate," not "deadline pressure"). Hedge honestly when evidence is uncertain ("per the PRD draft…"). Team-level framing is fine here since this is context, not contributions.

## Output

Return only:

```markdown
## Problem, Context, & Constraints

<prose>
```
