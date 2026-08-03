---
name: rollback-plan
description: Guides preparing and executing rollback plans for failed deployments.
version: 1.0.0
author: geodata-ii
team: devops
tags: [rollback, incident-response, devops]
license: MIT
compatibility: "Any application deployment pipeline requiring rollback capability"
last_updated: 2026-08-03
---

# Rollback Plan

## Overview

This Skill supports preparing and executing rollback plans to recover quickly from failed deployments.

## Purpose

Minimize downtime and user impact when a deployment needs to be reversed.

## When to Use

- Preparing a rollback plan before a risky deployment
- Responding to a production incident caused by a recent release

## When NOT to Use

- For designing the initial deployment strategy (use the deployment skill)
- For routine data backup planning unrelated to a specific release

## Prerequisites

- A known-good previous version to roll back to
- Clear criteria for deciding when a rollback is necessary

## Workflow

1. Define rollback triggers and criteria before deploying
2. Prepare and test the rollback procedure in advance
3. Execute the rollback and verify system stability afterward

## Best Practices

- Test the rollback procedure before it is ever needed in production
- Keep rollback steps documented and easy to follow under pressure

## Common Pitfalls

- Discovering during an incident that no rollback plan exists
- Rolling back application code without also reverting schema changes

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
