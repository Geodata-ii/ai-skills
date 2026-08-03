---
name: ai-code-reviewer
description: Standardized prompt and workflow for using an AI assistant to perform a first-pass code review on pull requests before human review.
version: 1.0.0
author: geodata-ii
team: ai-platform
tags: [ai, code-review, quality]
license: MIT
compatibility: "Works with any LLM-based coding assistant"
last_updated: 2026-08-03
---

# AI Code Reviewer

## Overview

This Skill defines a consistent way to ask an AI assistant to review a pull request's diff for correctness, style, security, and test coverage issues before a human reviewer looks at it.

## Purpose

Catch obvious defects, missing tests, and style violations early so human reviewers can focus on design and business logic.

## When to Use

- A pull request is opened or updated and needs an automated first pass before human review.
- You want a consistent review checklist applied across many repositories.

## When NOT to Use

- The change is trivial (e.g. a version bump or typo fix) where a review adds no value.
- The diff contains secrets or highly sensitive logic that should not be sent to a third-party model.

## Prerequisites

- Read access to the pull request diff and repository context.
- An approved AI coding assistant with an organization-sanctioned data-handling agreement.

## Workflow

1. Provide the assistant with the full diff, the PR description, and any linked issue.
2. Ask it to check correctness, security, test coverage, and style against the repository's conventions.
3. Post the findings as PR comments, clearly labeled as AI-generated and requiring human confirmation.

## Best Practices

- Always label AI review comments as such so authors know to weigh them accordingly.
- Feed the assistant the repository's actual lint and style configuration rather than generic conventions.

## Common Pitfalls

- Treating AI review output as a substitute for human approval rather than a supplement.
- Sending an incomplete diff, which produces false positives about missing code that exists elsewhere.

## References

- See docs/skill-style-guide.md and docs/review-process.md for repository-wide conventions.
