---
name: rag-development
description: Guidance for designing, building, and evaluating retrieval-augmented generation (RAG) pipelines, from chunking and embedding strategy through retrieval tuning and grounded answer generation.
version: 1.0.0
author: geodata-ii
team: ai-platform
tags: [ai, rag, embeddings, retrieval]
license: MIT
compatibility: "Python 3.11+, Node.js 20+"
last_updated: 2026-08-03
---

# RAG Development

## Overview

This Skill captures our organization's approach to building retrieval-augmented generation systems, covering ingestion, chunking, embedding, vector storage, and retrieval evaluation so teams do not each re-derive the same strategy.

## Purpose

Help engineers design a RAG pipeline that retrieves relevant context reliably and produces grounded, verifiable answers rather than hallucinated ones.

## When to Use

- You are building a feature that answers questions using a private or proprietary corpus of documents.
- You need to evaluate or improve the retrieval quality of an existing RAG system.

## When NOT to Use

- The task only needs a small, static context that fits entirely in a single prompt.
- You need real-time transactional lookups better served by a direct API or database call.

## Prerequisites

- Access to the source corpus and an approved embedding model or API key.
- A vector store (e.g. pgvector, Pinecone, or Azure AI Search) provisioned for the project.

## Workflow

1. Inventory the source documents and choose a chunking strategy (fixed-size, semantic, or structural).
2. Generate embeddings for each chunk and load them into the vector store with source metadata.
3. Evaluate answer groundedness and retrieval precision/recall against a labeled test set before shipping.

## Best Practices

- Store the source reference alongside each chunk so answers can be cited.
- Re-evaluate retrieval quality whenever the embedding model or chunking strategy changes.

## Common Pitfalls

- Chunking too coarsely, which dilutes relevance, or too finely, which loses context.
- Skipping an evaluation set and only testing with a handful of manual prompts.

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
