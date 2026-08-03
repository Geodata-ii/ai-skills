---
name: zendesk
description: Guides managing tickets, macros, and workflows in Zendesk for customer support teams.
version: 1.0.0
author: geodata-ii
team: customer-service
tags: [zendesk, customer-support, ticketing]
license: MIT
compatibility: "Zendesk Support ticketing, macros, and workflow automation"
last_updated: 2026-08-03
---

# Zendesk

## Overview

This Skill supports managing tickets, macros, triggers, and automations within Zendesk for customer support teams.

## Purpose

Improve support team efficiency and customer experience through well-organized Zendesk workflows.

## When to Use

- Setting up or refining Zendesk macros, triggers, or automations
- Reviewing ticket workflows for efficiency or consistency

## When NOT to Use

- For exporting Zendesk data for RAG pipelines (use the zendesk-rag-export skill)
- For general customer service strategy unrelated to the Zendesk platform

## Prerequisites

- Admin or agent access to the Zendesk instance
- An understanding of the team's existing ticket workflows

## Workflow

1. Identify repetitive or inconsistent steps in the ticket workflow
2. Implement macros, triggers, or automations to address them
3. Test changes on sample tickets before rolling out to the full team

## Best Practices

- Use clear, consistent naming conventions for macros and triggers
- Regularly review and retire unused or outdated automations

## Common Pitfalls

- Creating overlapping triggers that produce conflicting ticket updates
- Allowing macros to become outdated as processes change

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
