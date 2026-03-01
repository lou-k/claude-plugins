---
name: write-one-line-summary
description: Writes or updates the "One-line Summary" section of a brag doc entry. Invoke when you have enough context to summarize what was built and why it mattered.
user-invocable: false
---

# Write: One-line Summary

## Goal

Produce 1–2 sentences that answer: **What did you build, and why did it matter?**

A good one-line summary lets a reader immediately understand the project's purpose and its most impressive result. It is the hook that makes someone want to read the rest of the entry.

## Required elements

1. **What was built / done** — the deliverable, system, or change (concrete noun, not a vague verb phrase).
2. **Why it mattered** — the business or user impact, ideally quantified.
3. **Best metric** (if available) — the single most compelling outcome number. If no metric exists yet, omit rather than fabricate.

## Exclude

- **Jargon-heavy architecture details** — save those for other sections.
- **Task lists or process descriptions** — this is a result statement, not a status update.
- **Multiple metrics** — pick the single best one; the Outcomes section holds the rest.
- **Vague impact language** — "improved performance" without a number adds no signal.

## Style

- Write in **past tense, third person implied** (omit "I" — the subject is understood).
- Keep it to **1–2 sentences, ≤ 50 words**.
- Lead with the deliverable, follow with impact.
- If a metric is from recollection rather than a verified source, note it: "(estimated)".

## Examples

Good:
> Built a real-time fraud-detection pipeline processing 12M transactions/day, reducing chargebacks by 34% in the first quarter.

Good (no metric yet):
> Designed and shipped a self-serve onboarding flow that replaced a 5-day manual provisioning process.

Bad (too vague):
> Worked on improving the platform's performance and reliability.

## Output

Return only:

```markdown
## One-line Summary

<1–2 sentences>
```
```
