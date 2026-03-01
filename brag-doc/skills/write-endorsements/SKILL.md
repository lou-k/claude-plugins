---
name: write-endorsements
description: Writes or updates the "Endorsements" section of a brag doc entry. Invoke when you have quotes from stakeholders, peers, and/or managers that speak to the individual's impact on a project.
user-invocable: false
---

# Write: Endorsements

This section is optional — omit entirely if no quotes or endorsement evidence exists.

## What to capture

Direct quotes or close paraphrases from stakeholders, peers, or managers that speak to the individual's impact, judgment, or leadership on the project:

- **Stakeholder quotes** — product managers, business partners, or customers who benefited from the work
- **Peer quotes** — fellow engineers or cross-functional partners who observed contributions firsthand
- **Manager quotes** — skip-level or direct manager feedback that highlights specific impact or leadership qualities
- **Executive quotes** — VP/C-level recognition that ties the work to business outcomes

## What makes a good endorsement bullet

- **Attributed** — include who said it (name + role/relationship) when possible, or at minimum the role (e.g., "Engineering Manager," "Product Lead")
- **Specific** — references a concrete behavior, decision, or outcome rather than generic praise
- **Sourced** — note where the quote came from (e.g., performance review, Slack message, design review, promotion packet) when available

Good: "[Name]'s architecture proposal saved us 3 months of rework — he anticipated the scaling issues none of us had considered." — Jane Doe, Staff Engineer (design review)
Good: "Single-handedly unblocked the launch by driving alignment across three teams in a week." — Engineering Manager (performance review)

Bad: "Great engineer, pleasure to work with."
Bad: "Really smart and helpful."

## Exclude

- **Generic praise without specifics** — "great teammate" or "very talented" with no reference to what was done or why it mattered
- **Self-authored quotes** — do not fabricate or paraphrase your own assessment as someone else's words
- **Unattributed vague statements** — if you can't recall who said it or the context, omit it

## Style

Bullet list, ≤6 items. Each bullet: the quote (in quotation marks), attribution (name and/or role), and source context if available.

## Output

Return only:

```markdown
## Endorsements

- "<quote>" — <Name>, <Role> (<source>)
```
