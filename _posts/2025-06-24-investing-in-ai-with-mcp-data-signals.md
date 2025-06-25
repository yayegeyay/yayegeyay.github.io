---
layout: single
title: "Investing in AI: Modular Context Protocols & Data Signals"
date: 2025-05-30 09:30:00 +0000
categories: strategy architecture
---

I was in a board meeting with a promising Series A company, and the VP of Product was proudly presenting their AI roadmap. It was a beautiful slide, full of ambitious projects: a proprietary fine-tuned LLM, a state-of-the-art recommendation engine, a generative AI feature for their design tool. The board was impressed. I was terrified.

"Which of these projects," I asked, "is based on a clear, quantifiable signal from your users?" The room went quiet. They were planning to spend a year of runway and half their engineering capacity on bets that were based on intuition, not evidence.

There is a better way. Instead of making massive, high-risk bets on which AI feature will be a hit, you can make a single, low-risk investment that enables a dozen small ones. I call it installing a **Modular Context Protocol (MCP)**.

### The MCP: Your AI Nervous System

An MCP is not a product; it's a thin, internal layer of infrastructure that allows you to rapidly prototype and deploy simple, chat-based AI interfaces for any new idea. It's a standardized way to feed context to a language model and, more importantly, to log the interactions. This creates a powerful feedback loop where every user query becomes a data signal that informs your next move.

The investment strategy then becomes a simple, three-tiered process:

1.  **Level 1: Chat-based Discovery (48-hour prototype):** Have a new idea for an AI feature? Don't write a PRD. Build a simple chatbot interface for it using your MCP. Expose it to a small group of users. Your goal is not to build a perfect product; it's to **log real user intent**. What questions are they asking? What problems are they trying to solve?
2.  **Level 2: Agentic Workflow (2-week sprint):** Analyze the logs from your chatbot. You'll inevitably find that 80% of the queries fall into a few common patterns. Now, you have a clear mandate. Automate the most high-volume patterns by building a dedicated agentic workflow. This is no longer a guess; it's a data-driven decision.
3.  **Level 3: Custom UI (Full-quarter investment):** Only after an agent has proven its value and you can clearly see a positive impact on your key business metrics (and the ARR to justify it) should you invest in building a full-blown custom user interface.

At **CloudSale.ai**, we used this exact model. We started with a general-purpose "sales assistant" chatbot. After a week, we looked at the logs and found that **40% of all queries were related to prospect research**. That single, powerful data signal gave us the confidence to build an autonomous research agent that now runs 24/7, feeding our human BDRs a steady stream of highly qualified leads. We didn't have to guess; our users told us exactly what to build.

### Data First, Models Later

The most valuable asset in the age of AI is not your model; it's your data. Your evaluation suite is only as good as the production logs that feed it. Your fine-tuning efforts are worthless without a clean, representative dataset.

This is why your first move should always be to **treat your logs, evaluation datasets, and user feedback loops as a shared, first-class asset**, just like you would a central data warehouse. Every team that creates its own ad-hoc logging and evaluation system is creating a silo that burns future engineering time.

If your CTO's roadmap still has "fine-tune a proprietary LLM" listed before "standardize our data logging and evaluation framework," you need to reverse them. Immediately.

### A Simple Framework for Prioritization

To make this even more concrete, here's the simple formula I use with my clients to rank their AI initiatives:

`Value Score = (Volume of Interactions) × (Success Rate) × (Revenue per Successful Interaction)`

Rank your workflows using this formula every single week. The ones that rise to the top are your next big bets. It's the closest thing to an AI crystal ball I've found, and it's built on a foundation of real user data, not wishful thinking. 