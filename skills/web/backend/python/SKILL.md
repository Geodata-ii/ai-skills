---
name: python
description: Guides building and reviewing Python backend services and APIs following idiomatic patterns.
version: 1.0.0
author: geodata-ii
team: web-backend
tags: [python, backend, api]
license: MIT
compatibility: "Python 3.10+ backend services using frameworks such as FastAPI or Django"
last_updated: 2026-08-03
---

# Python

## Overview

This Skill supports building and reviewing Python backend services, APIs, and data processing code.

## Purpose

Deliver clean, well-tested Python services that follow PEP 8 and idiomatic conventions.

## When to Use

- Building new Python API endpoints or services
- Reviewing Python code for style, correctness, and testability

## When NOT to Use

- For frontend JavaScript or TypeScript development
- For data science notebooks unrelated to production services

## Prerequisites

- A configured Python virtual environment and dependency file
- Familiarity with the project's web framework and testing tools

## Workflow

1. Define the function or endpoint contract with type hints
2. Implement the logic following PEP 8 and project conventions
3. Write unit tests covering normal and edge-case behavior

## Best Practices

- Use type hints consistently to improve readability and tooling support
- Isolate I/O and side effects behind clear interfaces for testability

## Common Pitfalls

- Using mutable default arguments in function signatures
- Catching broad exceptions and silently swallowing errors

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
