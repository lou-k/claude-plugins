---
name: write-contributions
description: Writes or updates the "Contributions" section (Owned / Led / Contributed) of a brag doc entry. Invoke when you have evidence of what the individual did on a project.
user-invocable: false
---

# Write: Contributions

## Structure

Three required subsections, each a bullet list:

- **Owned** — things the individual was directly accountable for (architecture decisions, core implementation, system design, key deliverables)
- **Led** — things driven across others (cross-team initiatives, aligning stakeholders, driving standards, unblocking dependencies)
- **Contributed** — meaningful but not primary (reviews, advisory input, supporting roles)

## What belongs here

- **Technical leadership**: architecture choices, key design decisions, tradeoffs made
- **Execution**: core implementation, migrations, performance work, data pipelines
- **Cross-team influence**: aligning stakeholders, driving standards, unblocking others
- **ML-specific work**: data strategy, modeling approach, evaluation design, deployment, monitoring, guardrails

## Exclude

- **Team accomplishments framed as individual** — "we shipped X" is not a contribution; "I designed and implemented the ranking model" is. Preserve the distinction between what the individual did vs. the team.
- **Task lists / ticket exhaust** — "fixed bug #1234" or "attended standup" are not contributions unless they prevented a major incident or unblocked a high-visibility launch

## Style

Each bullet should be **specific and action-oriented**. Start with a verb or clear ownership signal. Include the system/component/domain touched. Aim for ≤5 bullets per subsection.

Bad: "Helped with the data pipeline"
Good: "Designed and built the feature extraction pipeline processing 50M events/day on Spark, replacing a manual SQL workflow"

If evidence doesn't clearly distinguish Owned vs. Led vs. Contributed, place items in the most conservative category. If a subsection has no supported content, omit it entirely — do not insert placeholders or editorial notes.

## Output

Return only:

```markdown
## Contributions

### Owned
- <bullet>

### Led
- <bullet>

### Contributed
- <bullet>
```
