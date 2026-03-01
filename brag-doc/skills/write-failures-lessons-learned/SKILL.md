---
name: write-failures-lessons-learned
description: Writes or updates the "Failures / Lessons Learned" section of a brag doc entry. Invoke when you have evidence of things that went wrong, root causes, and what changed as a result.
user-invocable: false
---

# Write: Failures / Lessons Learned

This section is optional — omit entirely if no evidence exists.

## What each bullet must contain

A curated set of well-formed failure/lesson entries. Each should cover:

1. **What went wrong** — the failure or mistake, stated plainly
2. **Root cause** — why it happened (not just symptoms)
3. **What changed** — the measurable or structural improvement that followed (lessons turned into process, tooling, or architecture changes)

Frame as **ownership + improvement**, not blame or excuse.

## Exclude

- **Failures without lessons** — "the launch was delayed" is not useful unless you explain why and what changed
- **Blame-shifting** — "the other team didn't deliver" without your own role in the outcome
- **Minor incidents** — skip unless they led to a significant structural change or demonstrate a skill you want to highlight

## Style

Bullet list, ≤6 items. Each bullet: 2–3 sentences covering what happened → why → what improved. These should be interview-ready: concise enough to tell in 60 seconds.

## Output

Return only:

```markdown
## Failures / Lessons Learned

- <bullet>
```
