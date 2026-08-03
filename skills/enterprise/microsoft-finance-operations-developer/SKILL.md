---
name: microsoft-finance-operations-developer
description: Guides development, customization, and extension work within Microsoft Dynamics 365 Finance and Operations.
version: 1.0.0
author: geodata-ii
team: enterprise-solutions
tags: [dynamics365, finance-operations, enterprise]
license: MIT
compatibility: "Microsoft Dynamics 365 Finance and Operations (X++ and Power Platform extensions)"
last_updated: 2026-08-03
---

# Microsoft Finance Operations Developer

## Overview

This Skill supports building, extending, and integrating Microsoft Dynamics 365 Finance and Operations modules using supported extension patterns.

## Purpose

Deliver reliable Finance and Operations customizations that remain upgrade-safe and aligned with Microsoft best practices.

## When to Use

- Building a new extension or customization for D365 Finance and Operations
- Integrating F&O with external systems via APIs or data entities

## When NOT to Use

- For general Power Platform app development unrelated to F&O
- For direct database edits that bypass supported extension models

## Prerequisites

- Access to a Dynamics 365 F&O development or sandbox environment
- Familiarity with X++ and the Microsoft extension model

## Workflow

1. Analyze the business requirement and identify the correct extension point
2. Implement the change using supported extension classes and events
3. Test in a sandbox environment and validate against upgrade compatibility

## Best Practices

- Always use extension classes rather than modifying standard objects
- Document customizations to simplify future upgrades

## Common Pitfalls

- Directly overlaying standard code, breaking future upgrades
- Skipping regression testing on core finance processes

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
