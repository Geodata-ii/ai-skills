---
name: backup
description: Guides designing and validating backup strategies for applications and data.
version: 1.0.0
author: geodata-ii
team: devops
tags: [backup, disaster-recovery, devops]
license: MIT
compatibility: "Any application or database requiring a backup and recovery strategy"
last_updated: 2026-08-03
---

# Backup

## Overview

This Skill supports designing, implementing, and validating backup strategies for applications and data.

## Purpose

Ensure data and systems can be recovered reliably after loss or corruption.

## When to Use

- Designing a backup strategy for a new application or database
- Reviewing existing backup coverage and retention policies

## When NOT to Use

- For executing a rollback of a failed deployment (use the rollback-plan skill)
- For version control of application source code

## Prerequisites

- Defined recovery time and recovery point objectives
- Access to the systems and data that need to be backed up

## Workflow

1. Define recovery time and recovery point objectives
2. Implement automated, scheduled backups with appropriate retention
3. Regularly test restoring from backups to confirm they work

## Best Practices

- Store backups in a separate location or region from production
- Test restores regularly, not just backup creation

## Common Pitfalls

- Assuming backups work without ever testing a restore
- Storing backups in the same location as the primary system

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
