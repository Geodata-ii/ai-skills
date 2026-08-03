---
name: code-reviewer
description: Performs structured code review for enterprise applications, focused on maintainability, security, and standards compliance.
version: 1.0.0
author: geodata-ii
team: enterprise-solutions
tags: [code-review, enterprise, quality]
license: MIT
compatibility: "Applicable to enterprise codebases in any language following standard PR-based review workflows"
last_updated: 2026-08-03
---

# Code Reviewer

## Overview

This Skill provides a consistent framework for reviewing enterprise application code for correctness, security, and maintainability.

## Purpose

Catch defects, security risks, and standards violations before code merges into production branches.

## When to Use

- Reviewing pull requests for enterprise applications
- Auditing legacy code before a major refactor or migration

## When NOT to Use

- For automated linting that can be fully handled by static analysis tools
- For reviewing exploratory or throwaway prototype code

## Prerequisites

- Access to the pull request or codebase under review
- A documented coding standard or style guide to review against

## Workflow

1. Review the change for correctness, security, and adherence to standards
2. Leave actionable, specific comments on any issues found
3. Approve once all blocking issues are resolved

## Best Practices

- Focus comments on substance over style where linters already enforce style
- Explain the reasoning behind requested changes, not just the change itself

## Common Pitfalls

- Approving changes without verifying tests actually cover the new logic
- Nitpicking style issues while missing significant security concerns

## References

- See docs/skill-style-guide.md and docs/review-process.md for repository-wide conventions.
