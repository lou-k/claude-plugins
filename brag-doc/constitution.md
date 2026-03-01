Below is a practical “what to include / what not to include” for a Principal SWE with AI/ML focus.

---

## What *should* be in your storybook

### 1) A one-page “master index” (so it’s usable)
For each entry, capture quick metadata so you can filter later:
- Project/initiative name
- Dates (start/end)
- Company/org + team
- Your role/title + “hat” (tech lead, architect, IC, manager-of-work, etc.)
- Domain (ML platform, LLM apps, MLOps, inference, data eng, etc.)
- Keywords/tech stack (for searchability)
- Links (PRDs, design docs, dashboards, repos—internal is fine)

### 2) Problem + context (why it mattered)
Write the story so a future reader (including future you) understands:
- What business/user problem existed?
- Why now? What was the urgency/risk/opportunity?
- Constraints: latency, cost, privacy, regulation, data availability, team size, timeline

This is the “setup” that makes your decisions look like good judgment rather than random work.

### 3) Your specific contributions (the “I did” section)
Be explicit about what you personally owned:
- Technical leadership: architecture, key design choices, tradeoffs
- Execution: core implementation, migrations, performance work
- Cross-team influence: aligning stakeholders, driving standards, unblocking
- ML-specific work: data strategy, modeling approach, evaluation, deployment, monitoring, guardrails

A useful format is:
- **Owned:** (things you were directly accountable for)
- **Led:** (things you drove across others)
- **Contributed:** (important but not primary)

### 4) Outcomes with metrics (the “proof”)
Capture both **business impact** and **engineering impact**:
- Revenue, conversion, retention, churn, cost savings, time saved
- Model metrics (accuracy/F1/AUC), but also *product* metrics (e.g., uplift, precision at k)
- Latency, throughput, availability, infra cost reduction
- Adoption: number of teams/users, queries/day, deployments/week
- Risk reduction: incidents avoided, compliance met, security posture improved

If you don’t have metrics, include:
- Baseline vs after (even directional)
- Proxy metrics (tickets reduced, manual review hours, on-call pages)
- Qualitative evidence (exec quote, customer feedback, internal adoption)

### 5) Decisions + tradeoffs (this is what makes it “Principal”)
For each major initiative, record:
- Alternatives considered (and why rejected)
- Key tradeoffs (speed vs quality, build vs buy, cost vs latency)
- Architectural “bets” and how you de-risked them (POC, phased rollout, A/B test)
- What you would do differently now

This section becomes gold for interviews and consulting credibility.

### 6) Scope and complexity indicators
These help you convey seniority without bragging:
- Team size / cross-functional partners
- Systems scale (data volume, QPS, model size, region count)
- Integration surface (how many services, platforms, customer segments)
- Operational maturity (SLOs, incident management, runbooks)

### 7) Artifacts you can reuse quickly
Store or reference:
- 2–3 résumé-ready bullets per project
- A STAR/LARB interview story version (Situation/Task/Action/Result)
- A short consulting case-study variant (client-friendly, de-identified)
- Links to sanitized diagrams, slides, writeups

### 8) Influence beyond code (often undervalued)
Capture leadership that isn’t “feature shipped”:
- Mentoring/coaching: who/what changed (promotions, ramp time reduced)
- Hiring loops, leveling, interview rubric improvements
- Setting standards: ML evaluation guidelines, coding patterns, platform templates
- Community: talks, papers/blog posts, internal workshops
- Incident leadership: major outage response, postmortems, systemic fixes

### 9) “Failure” and “learning” entries (curated)
You want a few well-formed ones:
- What went wrong, root cause, what you changed
- The measurable or structural improvement after (lessons turned into process/tech)

These are powerful in interviews if framed as ownership + improvement.

---

## What *shouldn’t* be in your storybook

### 1) Raw task logs or Jira exhaust
Avoid:
- Daily/weekly activity lists
- Low-level tickets without narrative
If it doesn’t support impact, tradeoffs, or evidence, it’s noise.

### 2) Confidential/sensitive details you can’t reuse
Especially important for consulting and job search:
- Proprietary customer names, internal metrics that are confidential
- Security vulnerabilities, unreleased product details
Instead, record a **sanitized version**:
- “Top-3 retailer” / “Fortune 100 client”
- “Reduced infra cost ~30%” (keep exact numbers separately if needed)

### 3) Unverifiable fluff
Phrases like:
- “Worked on cutting-edge AI”
- “Helped optimize performance”
Unless you attach *what*, *how*, and *result*, it won’t help later.

### 4) One-off minor contributions (unless strategically relevant)
If you fixed a bug once, skip it—unless it:
- Prevented a major incident
- Unblocked a high-visibility launch
- Demonstrates a specialized skill you want to market

### 5) Excessive technical detail that won’t be reusable
You can keep deep notes elsewhere, but in the storybook avoid:
- Full code snippets
- Line-by-line implementation
Prefer: diagrams, key choices, performance numbers, constraints.
