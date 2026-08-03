---
name: ci-cd-pipeline
description: Guides designing end-to-end CI/CD pipeline strategy independent of a specific tool.
version: 1.0.0
author: geodata-ii
team: devops
tags: [ci-cd, pipeline, automation]
license: MIT
compatibility: "Any CI/CD toolchain, including GitHub Actions and Bitbucket Pipelines"
last_updated: 2026-08-03
---

# CI/CD Pipeline

## Overview

This Skill guides the overall design of CI/CD pipeline strategy across build, test, and release stages.

## Purpose

Establish a consistent, reliable path from code commit to production release.

## When to Use

- Designing a new CI/CD pipeline strategy for a project
- Reviewing an existing pipeline for gaps in stages or quality gates

## When NOT to Use

- For tool-specific syntax questions (use the github-actions or bitbucket-pipelines skill)
- For one-off manual deployments with no pipeline involved

## Prerequisites

- A defined build, test, and release process for the project
- Agreement on required quality gates before release

## Workflow

1. Map out the stages from commit to production release
2. Define quality gates such as tests, linting, and approvals
3. Implement the pipeline in the chosen CI/CD tool and validate it end to end

## Best Practices

- Fail fast by running the quickest checks first
- Keep pipelines idempotent and reproducible across environments

## Common Pitfalls

- Skipping automated tests to speed up releases
- Allowing manual, undocumented steps to creep into the release process

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
