---
layout: single
title: "Version Control for Prompt Hackers: A 5-Minute Git Workflow"
date: 2025-03-10 12:00:00 +0000
categories: engineering prompts
tags: [vibe-coder]
---

"What branch was the working prompt on?"—every vibe-coder ever, five minutes before demo day.

The good news: you don't need a platform migration to get determinism. One Git pattern handles 90 % of prompt-engineering chaos.

### The `prompts/` contract

1. Create a `/prompts` folder next to your code.  
2. Every prompt lives in its own `.prompt.md` file with **inputs** defined in YAML front-matter.  
3. Model settings (temperature, top-p) live beside the text.

```yaml
---
name: prospect_research
model: gpt-4o
temperature: 0.2
---
"Analyse the following prospect …"
```

Now your git diff shows *exactly* what changed when the response quality tanked at 2 a.m.

### Feature flags for prompts

Wrap your LLM call with an ENV flag `PROMPT_VERSION`. Shipping a new variant? Push a branch, set the flag on staging, collect win-rate metrics. Merge when > baseline.

### Why not PromptOps SaaS?

Use SaaS if you're at Fortune-500 scale. Until then, two Git conventions beat another dashboard.

**Coming up:** part 2 on snapshotting embedding versions so your search doesn't drift overnight. 