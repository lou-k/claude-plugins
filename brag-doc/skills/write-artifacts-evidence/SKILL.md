---
name: write-artifacts-evidence
description: Writes or updates the "Artifacts / Evidence" section of a brag doc entry. Invoke when you have references to design docs, dashboards, PRs, slides, or other supporting evidence for a project.
user-invocable: false
---

# Write: Artifacts / Evidence

This section is optional — omit entirely if no artifacts exist.

## What to capture

A list of evidence supporting claims elsewhere in the entry. Each item has:
- **label** (required) — short description of the artifact
- **url** (optional) — link (internal links are fine; this is a private brag doc)
- **notes** (optional) — 1 sentence of context on relevance

## Prioritize

- Artifacts that **back key outcomes or decisions** (dashboards, A/B test results, design docs)
- Résumé-ready materials (sanitized slides, writeups, blog posts)
- STAR/LARB interview story versions if they exist

## Exclude

- **Artifacts without relevance** — don't list every PR or doc; only those that support key claims
- **Full code snippets** — link to the repo, don't paste code

## Style

Bullet list, ≤10 items.

## Output

Return only:

```markdown
## Artifacts / Evidence

* **[label](url)** - notes
```

If an artifact has no url, omit the link:

```markdown
* **label** - notes
```
