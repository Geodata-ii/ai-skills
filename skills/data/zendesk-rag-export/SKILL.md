---
name: zendesk-rag-export
description: Streams Zendesk tickets into structured, resumable JSON/Markdown/JSONL exports ready to chunk and embed for a RAG-based support chatbot.
version: 1.0.0
author: arulselvan001
team: data-platform
tags: [data, zendesk, rag, etl, support]
license: MIT
compatibility: "Python 3.12+"
last_updated: 2026-08-03
---

# Zendesk RAG Export

## Overview

This Skill exports Zendesk support tickets into a structured dataset suitable for building a retrieval-augmented generation (RAG) support chatbot. It streams tickets via Zendesk's cursor-based incremental API, reconstructs each ticket into a clean conversation, and writes one JSON record, one Markdown document, and one line of a combined JSONL dataset per qualifying ticket.

## Purpose

Turn a large, growing Zendesk ticket history into a knowledge base an LLM can retrieve from, without holding the full ticket set in memory and without re-processing tickets that have not changed. Success looks like a `tickets.jsonl` file where each line is one ticket's full conversation, ready to chunk and embed, plus per-ticket Markdown files a human can read directly.

## When to Use

- You are building or refreshing a support knowledge base or RAG chatbot from historical Zendesk tickets.
- You need a periodic incremental sync of newly solved or closed tickets into an existing dataset.
- You need both machine-readable (JSON/JSONL) and human-readable (Markdown) output from the same export run.

## When NOT to Use

- You need real-time, per-event streaming of ticket updates; this Skill runs as a batch or scheduled job, not a webhook consumer.
- You only need a handful of tickets; the Zendesk UI or a simple API call is faster than standing up this pipeline.
- Your helpdesk platform is not Zendesk; the API client and pagination logic here are Zendesk-specific.

## Prerequisites

- Python 3.12 or newer.
- A Zendesk API token with read access to tickets, users, and ticket audits (generate under Admin Center > Apps and integrations > APIs > Zendesk API).
- Environment variables `ZENDESK_SUBDOMAIN`, `ZENDESK_EMAIL`, and `ZENDESK_API_TOKEN`, set from your own Zendesk account credentials, never committed to source control.
- Local disk space proportional to your ticket volume, for `storage/raw/`, `storage/processed/`, and `checkpoints/`.

## Workflow

1. Copy `.env.example` to `.env` and fill in `ZENDESK_SUBDOMAIN`, `ZENDESK_EMAIL`, and `ZENDESK_API_TOKEN`. See [`examples/env-example.md`](examples/env-example.md) for the full variable list.
2. Install dependencies into a virtual environment (`pip install -r requirements.txt`).
3. Run a full export with `python app.py full`. This streams every ticket via cursor pagination, filters to `ALLOWED_STATUSES` (default `solved,closed`), and writes raw and processed output.
4. If the run is interrupted, re-run `python app.py full`; it resumes from `checkpoints/checkpoint.json` instead of starting over.
5. For subsequent runs, use `python app.py incremental` to fetch only tickets that are new or changed since the last full run, and process any that are now solved or closed.
6. Confirm success by checking `storage/processed/datasets/tickets.jsonl` exists and its line count roughly matches the number of qualifying tickets reported in `logs/export.log`.

## Best Practices

- Always run `full` at least once before ever running `incremental`; incremental sync depends on a prior full run's checkpoint and user cache.
- Tune `THREAD_COUNT` and `PAGE_SIZE` conservatively at first; raising concurrency too aggressively increases the chance of hitting Zendesk rate limits.
- Keep `storage/raw/` around even after processing; it lets you rebuild `storage/processed/` if the processing logic changes without re-hitting the Zendesk API.
- Review `ALLOWED_STATUSES` before a run; only tickets in these statuses are processed into RAG output, though all tickets are still streamed and recorded in the raw export.

## Common Pitfalls

- Running `incremental` before any `full` export has completed; this fails with a clear error rather than silently producing a partial dataset.
- Expecting a ticket to reprocess after an external change when its `updated_at` timestamp did not actually change in Zendesk; the manifest keys on `updated_at`, not on downstream fields.## Common Pitfalls

 - Leaving `ZENDESK_EMAIL` with a `/token` suffix or `ZENDESK_SUBDOMAIN` with a full URL; both are sanitized on load but malformed values can still slip through in edge cases.

## Debugging

- Check `logs/export.log` first; it records the current cursor, current ticket, processed/skipped/failed counts, and ETA for every run.
- Repeated "Retrying request" warnings usually indicate Zendesk rate limiting (HTTP 429) or a transient network or 5xx error; the client backs off automatically and normally recovers on its own.
- To force a clean full re-export, delete `checkpoints/checkpoint.json` and `checkpoints/processed_manifest.json`, then run `python app.py full` again.

## Examples

See [`examples/sample-ticket-output.md`](examples/sample-ticket-output.md) for a complete, worked example showing the input environment configuration and the resulting per-ticket Markdown and JSONL output for a single sample ticket.

## References

- [`references/zendesk-api-notes.md`](references/zendesk-api-notes.md) for details on the Zendesk endpoints and pagination behavior this Skill relies on.
- [Zendesk API documentation](https://developer.zendesk.com/api-reference/) for the authoritative reference on incremental exports and rate limits.
- [`skills/data/README.md`](../README.md) for other Skills in the data category.
