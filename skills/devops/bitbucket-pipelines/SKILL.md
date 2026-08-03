---
name: bitbucket-pipelines
description: Guides designing and maintaining Bitbucket Pipelines configurations for CI/CD automation.
version: 1.0.0
author: geodata-ii
team: devops
tags: [bitbucket, ci-cd, automation]
license: MIT
compatibility: "Bitbucket Pipelines in any Bitbucket Cloud repository"
last_updated: 2026-08-03
---

# Bitbucket Pipelines

## Overview

This Skill supports designing, reviewing, and maintaining Bitbucket Pipelines configurations for CI/CD automation.

## Purpose

Deliver reliable, maintainable CI/CD pipelines using Bitbucket Pipelines.

## When to Use

- Creating a new Bitbucket Pipelines configuration for build, test, or deploy
- Reviewing existing pipelines for reliability or security issues

## When NOT to Use

- For GitHub Actions workflows (use the github-actions skill)
- For general CI/CD strategy unrelated to a specific tool

## Prerequisites

- A Bitbucket Cloud repository with Pipelines enabled
- Defined build, test, and deployment steps for the project

## Workflow

1. Define the pipeline steps and trigger conditions
2. Implement the bitbucket-pipelines.yml configuration
3. Test the pipeline and confirm it behaves correctly on failures

## Best Practices

- Use pipeline caches to speed up repeated dependency installs
- Store credentials in repository or workspace variables, not in code

## Common Pitfalls

- Hardcoding secrets directly in the pipeline configuration
- Running unnecessarily large or slow steps on every commit

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
