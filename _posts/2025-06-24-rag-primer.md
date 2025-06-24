---
layout: single
title: "RAG 101: Retrieval-Augmented Generation for Busy Founders"
date: 2025-06-24 11:10:00 +0000
categories: rag fundamentals
---

Founders keep asking me for the *one-paragraph* explanation of RAG they can repeat to investors. Here it is:

> "RAG pairs a fast search index with a language model so the model answers only from *your* data, not its pre-training trivia."

### Why it matters

1. **Hallucination guard-rails** – model can't cite what isn't retrieved.  
2. **No re-training loop** – swap docs, get new answers.  
3. **Token efficiency** – smaller context beats bigger model.

### Acceptable first architecture

* `faiss` index of cleaned markdown or HTML  
* `MiniLM` embeddings via `sentence-transformers`  
* `gpt-4o` with a 2-shot answer format prompt  
* 3-line Python eval harness comparing answer span to ground-truth using `rouge-l`.

Ship that in a weekend, then iterate with hybrid search, rerankers, and feedback loops. 