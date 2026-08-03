---
name: wiki-doc-tester
description: Workflow for using an AI assistant to test whether wiki and documentation pages remain accurate against the current codebase and configuration.
version: 1.0.0
author: geodata-ii
team: ai-platform
tags: [ai, documentation, testing]
license: MIT
compatibility: "Works with any LLM-based assistant"
last_updated: 2026-08-03
---

# Wiki Doc Tester

## Overview

This Skill defines how to have an AI assistant check existing wiki or documentation pages against the current source code, configuration, and behavior to find stale or incorrect statements.

## Purpose

Catch documentation drift before it misleads engineers, so wiki pages stay a trustworthy source of truth.

## When to Use

- A wiki page has not been reviewed in a long time and may reference outdated commands or configuration.
- You want an automated check as part of a periodic documentation audit.

## When NOT to Use

- The documentation is brand new and was just verified manually during its own review.
- The page describes policy or process rather than technical facts that can be checked against code.

## Prerequisites

- Read access to both the wiki page and the corresponding source repository or configuration.
- An approved AI assistant with access to the relevant codebase context.

## Workflow

1. Provide the assistant with the wiki page content and the current source files or configuration it describes.
2. Ask it to flag statements that no longer match the code, along with the specific discrepancy.
3. Route flagged discrepancies to the page owner for correction.

## Best Practices

- Focus the check on verifiable technical claims rather than subjective prose.
- Re-run the check after major refactors that touch documented systems.

## Common Pitfalls

- Treating every flagged discrepancy as certain; the assistant can misread context and should be spot-checked.
- Skipping re-verification after the page owner makes corrections.

## References

- See docs/skill-style-guide.md and docs/writing-skills.md for repository-wide conventions.
