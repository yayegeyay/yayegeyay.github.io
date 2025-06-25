---
layout: single
title: "Version Control for Prompt Hackers: A 5-Minute Git Workflow"
date: 2025-03-10 12:00:00 +0000
categories: engineering prompts
tags: [vibe-coder]
---

I was on a call with a frantic founder at 2 a.m. Their AI-powered customer support bot had suddenly started giving bizarre, off-brand answers. "It was working perfectly yesterday," he said. "We didn't change any code." My first question was, "Okay, but who changed the prompt?" After a long pause, he asked, "What branch was the working prompt on?"

This is a scene that plays out every day in the world of "vibe coding," where prompts are the new source code. The good news is that you don't need a fancy, expensive PromptOps platform to bring sanity to this chaos. A simple, disciplined Git workflow can handle 90% of the challenges of prompt engineering.

### The `/prompts` Contract

This is a simple but powerful convention that will save you countless hours of debugging.

1.  **Create a `/prompts` directory** at the root of your project, right next to your source code. This signals to your entire team that prompts are a first-class citizen in your application.
2.  **Every prompt lives in its own dedicated `.prompt.md` file.** The filename should be a clear, human-readable identifier for the prompt's purpose (e.g., `customer_support_triage.prompt.md`).
3.  **Define inputs and model settings in YAML front-matter.** At the top of each prompt file, include a YAML block that specifies the model, the temperature, the `top_p`, and any other important parameters. This makes your prompts self-documenting and ensures that your settings are version-controlled along with your text.

Here's what it looks like in practice:

```yaml
---
name: prospect_research_summary
model: gpt-4o
temperature: 0.2
max_tokens: 500
---
"You are a helpful assistant. Analyze the following LinkedIn profile and provide a two-sentence summary for a sales representative. Focus on their current role and recent achievements. The prospect's profile is: {{linkedin_profile}}"
```

With this structure, your `git diff` becomes a powerful tool. When the quality of your AI's responses suddenly degrades, you can see *exactly* what changed—not just the text of the prompt, but the temperature, the model version, everything.

### Feature Flags for Prompts

You wouldn't ship a major code change without testing it first. You should treat your prompts with the same respect. Use a simple environment variable, like `PROMPT_VERSION`, to act as a feature flag.

When you want to test a new variant of a prompt, you simply:
1.  Create a new branch in Git.
2.  Edit the prompt file.
3.  Set the `PROMPT_VERSION` environment variable on your staging server to point to the new Git branch.
4.  Collect performance metrics (e.g., conversion rate, user satisfaction, hallucination rate).
5.  If the new version outperforms the old one, merge the branch.

This simple process allows you to A/B test your prompts systematically, using the same tools and workflows you already use for your application code.

### Why Not Just Buy a PromptOps SaaS?

There are some great PromptOps platforms out there, and if you're a Fortune 500 company with a team of 50 prompt engineers, you should probably use one. But for the 99% of teams that are just trying to ship a product, a disciplined Git workflow is a more effective solution. It's free, it's flexible, and it integrates seamlessly with your existing development process.

Start with these two simple conventions—the `/prompts` directory and feature flags—and you'll be ahead of most of the industry.

**Coming up:** In part two of this series, I'll discuss a similar Git-based approach for snapshotting your embedding model versions, so your semantic search results don't mysteriously drift overnight. 