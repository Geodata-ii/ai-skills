---
name: php
description: Guides building and reviewing PHP backend applications, covering modern frameworks and secure coding.
version: 1.0.0
author: geodata-ii
team: web-backend
tags: [php, backend, web]
license: MIT
compatibility: "PHP 8+ applications using frameworks such as Laravel or Symfony"
last_updated: 2026-08-03
---

# PHP

## Overview

This Skill supports building and reviewing PHP backend applications using modern frameworks and secure coding practices.

## Purpose

Deliver secure, maintainable PHP applications following current framework conventions.

## When to Use

- Building new PHP application features or endpoints
- Reviewing legacy PHP code for security or modernization opportunities

## When NOT to Use

- For non-PHP backend services
- For frontend-only application code

## Prerequisites

- A configured PHP environment with Composer dependencies
- Familiarity with the project's framework, such as Laravel or Symfony

## Workflow

1. Define the feature or endpoint contract
2. Implement using the framework's conventions for routing and validation
3. Test thoroughly, including input validation and edge cases

## Best Practices

- Use parameterized queries to prevent SQL injection
- Validate and sanitize all user input at the framework boundary

## Common Pitfalls

- Concatenating raw user input directly into SQL queries
- Mixing business logic directly into view templates

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
