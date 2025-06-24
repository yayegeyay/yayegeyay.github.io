---
layout: single
title: "Systematically Improving RAG without Losing Your Weekend"
date: 2025-06-24 10:50:00 +0000
categories: rag
---

Retrieval-augmented generation sounds great until the CFO asks why vector search spends more on GPUs than the whole data warehouse.

Here's the three-checkpoint loop I use on client projects:

1. **Evidence coverage** – does every answer cite at least one doc? (Log & chart hourly.)
2. **Ground-truth eval** – weekly HITL review of 50 random queries; >90 % factual or you iterate.
3. **Cost per successful answer** – target <$0.002 including embed + context + inference.

If #3 spikes, first suspect **chunk explosion**. One team I helped had verbose Markdown FAQ files; trimming markdown tables cut spend 60 % overnight.

### Fast win checklist

- Deduplicate embeddings by SHA-1 of cleaned text.  
- Use a *title* token weight of 1.2 in BM25 hybrid search—it solves 50 % of "wrong section" errors.  
- Cache answers to top-20 queries; most dashboards ask the same thing every hour.

Implement the loop, set Grafana alerts, enjoy your weekend. 