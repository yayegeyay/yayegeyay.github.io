---
layout: single
title: "Cross-Linking AI Agents: Stop Copy-Pasting Data Between Workflows"
date: 2024-12-20 14:00:00 +0000
categories: ai-agents architecture
---

Your sales agent finds a prospect, your research agent scores it, your outreach agent drafts an email—and each one stores state in its own Redis key nobody can remember.

The fix is boring: **an event bus plus a shared vector store**. Once every agent publishes the same semantic IDs, cross-agent orchestration is a JOIN, not a Slack thread.

Minimal stack that works:

* **NATS** for JSON events under 5 KB  
* **pgvector** table for any text you'll want to search later  
* One `agent_id` and `object_id` on every row/event.

CloudSale.ai moved from per-agent SQLite files to this pattern and shaved 800 lines of glue code while opening the door to ad-hoc analytics.

Rule: if two agents touch the same entity more than once a week, they deserve a contract in the bus. 