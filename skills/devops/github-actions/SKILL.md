---
name: github-actions
description: Guides designing and maintaining GitHub Actions workflows for CI/CD automation.
version: 1.0.0
author: geodata-ii
team: devops
tags: [github-actions, ci-cd, automation]
license: MIT
compatibility: "GitHub Actions workflows in any GitHub-hosted repository"
last_updated: 2026-08-03
---

# GitHub Actions

## Overview

This Skill supports designing, reviewing, and maintaining GitHub Actions workflows for build, test, and deployment automation.

## Purpose

Deliver reliable, maintainable CI/CD pipelines using GitHub Actions.

## When to Use

- Creating a new GitHub Actions workflow for build, test, or deploy
- Reviewing existing workflows for reliability or security issues

## When NOT to Use

- For Bitbucket Pipelines configuration (use the bitbucket-pipelines skill)
- For general CI/CD strategy unrelated to a specific tool

## Prerequisites

- A GitHub repository with Actions enabled
- Defined build, test, and deployment steps for the project

## Workflow

1. Define the workflow triggers and required jobs
2. Implement the workflow YAML using reusable actions where possible
3. Test the workflow and confirm it behaves correctly on failures

## Best Practices

- Pin third-party actions to a specific commit or version
- Use secrets for credentials rather than hardcoding values

## Common Pitfalls

- Referencing third-party actions by a mutable tag without pinning
- Missing timeout limits, allowing stuck jobs to run indefinitely

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
