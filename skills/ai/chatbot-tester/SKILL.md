---
name: chatbot-tester
description: Validates chatbot conversational flows, response accuracy, and edge-case handling before release.
version: 1.0.0
author: geodata-ii
team: ai-platform
tags: [ai, chatbot, testing]
license: MIT
compatibility: "Works with any conversational AI platform exposing a text or API-based chat interface"
last_updated: 2026-08-03
---

# Chatbot Tester

## Overview

This Skill drives structured, repeatable testing of chatbot conversations to catch regressions, dead ends, and incorrect responses before they reach users.

## Purpose

Ensure chatbot deployments meet accuracy, tone, and reliability expectations across common and edge-case scenarios.

## When to Use

- Before releasing a new chatbot flow or intent to production
- After updating a chatbot's underlying model, prompt, or knowledge base

## When NOT to Use

- For load or performance testing of infrastructure
- For evaluating non-conversational batch AI jobs

## Prerequisites

- Access to a staging or sandbox instance of the chatbot
- A set of representative test conversations and expected outcomes

## Workflow

1. Define test scenarios covering happy paths, edge cases, and failure modes
2. Run each scenario against the chatbot and record actual responses
3. Compare actual vs expected outcomes and log discrepancies for follow-up

## Best Practices

- Include multi-turn conversations, not just single-turn prompts
- Re-run the full test suite after every prompt or model change

## Common Pitfalls

- Testing only ideal-path conversations and skipping ambiguous input
- Failing to retest previously passing scenarios after changes

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
