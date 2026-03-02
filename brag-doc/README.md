# brag-doc

An agent that helps engineers write  brag docs — concise, evidence-rich records of what you built, why it mattered, and what you personally contributed.

## What's a brag doc?

A brag doc captures the story behind your work: the problem, your decisions, the outcomes, and the proof. It's not a task log — it's a curated record of impact, tradeoffs, and leadership that you can pull from for performance reviews, promotion packets, interviews, or consulting case studies.

## When to write one

- After shipping a meaningful project or initiative
- Before performance review season (while details are fresh)
- When preparing for interviews or a role change
- Anytime you want to capture work that might otherwise be forgotten

## How it works

Run `/brag-doc:write` with a project name and any supporting materials you have — design docs, PRDs, post-mortems, Slack exports, dashboards, or links. The agent ingests your artifacts, drafts an entry, identifies gaps, and **interviews you** to fill in what's missing. A quality reviewer does a final pass before saving.

You don't need to have everything upfront. If you have no artifacts at all, the agent skips straight to interviewing you.

Every entry follows a structured [spec](skills/write/spec.yaml) covering: one-line summary, problem context, contributions (owned / led / contributed), key decisions & tradeoffs, scope & complexity, outcomes, artifacts, influence beyond code, and lessons learned.

## Output

A markdown file with YAML front matter per the spec — one file per project, ready to drop into a brag doc collection. See an [example here](example_output.md).

## Installing

See the [root README.md](../README.md).