---
name: deployment
description: Guides planning and executing safe application deployments to production environments.
version: 1.0.0
author: geodata-ii
team: devops
tags: [deployment, release, devops]
license: MIT
compatibility: "Any application deployment target, including cloud and on-premises environments"
last_updated: 2026-08-03
---

# Deployment

## Overview

This Skill supports planning and executing safe, predictable application deployments to production.

## Purpose

Minimize risk and downtime when releasing new versions of an application.

## When to Use

- Planning a production release or deployment window
- Choosing a deployment strategy for a new or changed service

## When NOT to Use

- For rolling back a failed release (use the rollback-plan skill)
- For local development environment setup

## Prerequisites

- A tested, release-ready build of the application
- A defined rollback plan in case the deployment fails

## Workflow

1. Choose a deployment strategy such as blue-green or rolling updates
2. Execute the deployment following the defined runbook
3. Monitor the release and confirm system health post-deployment

## Best Practices

- Use gradual rollout strategies to limit blast radius
- Monitor key metrics closely immediately after deployment

## Common Pitfalls

- Deploying without a tested rollback plan in place
- Deploying large, risky changes all at once instead of incrementally

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
