---
name: wiki-generator
description: Workflow for using an AI assistant to generate and keep internal wiki pages in sync with source code and documentation.
version: 1.0.0
author: geodata-ii
team: ai-platform
tags: [ai, documentation, wiki]
license: MIT
compatibility: "Works with any LLM-based assistant"
last_updated: 2026-08-03
---

# Wiki Generator

## Overview

This Skill defines how to prompt an AI assistant to draft or update wiki pages from source code, READMEs, and design docs so documentation keeps pace with the codebase.

## Purpose

Reduce the effort of keeping internal wikis current by generating a first draft that a human then reviews and publishes.

## When to Use

- A new service, module, or feature needs an onboarding or reference wiki page.
- An existing wiki page has drifted out of sync with the current code or process.

## When NOT to Use

- The content is highly sensitive strategic information that should be written and reviewed entirely by hand.
- The wiki page is mostly a change log better served by CHANGELOG.md or release notes.

## Prerequisites

- Read access to the source repository and any existing wiki content to update.
- An approved AI assistant and a wiki platform with an API or import path for publishing drafts.

## Workflow

1. Give the assistant the relevant source files, existing wiki page (if any), and target audience.
2. Ask it to draft or update the page following the organization's wiki style guide.
3. Route the draft to a subject-matter expert for review before publishing.

## Best Practices

- Always route generated drafts through a human owner before publishing.
- Link the wiki page back to the source files it was generated from.

## Common Pitfalls

- Publishing a generated draft without review, allowing subtle inaccuracies into the wiki.
- Letting generated pages go stale by not re-running the Skill after major code changes.

## References

- See docs/skill-style-guide.md and docs/writing-skills.md for repository-wide conventions.
