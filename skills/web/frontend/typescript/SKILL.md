---
name: typescript
description: Guides writing and reviewing TypeScript code with strong typing and maintainable type design.
version: 1.0.0
author: geodata-ii
team: web-frontend
tags: [typescript, javascript, type-safety]
license: MIT
compatibility: "TypeScript 5+ projects across frontend and backend codebases"
last_updated: 2026-08-03
---

# TypeScript

## Overview

This Skill supports writing and reviewing TypeScript code with accurate, maintainable type definitions.

## Purpose

Catch type-related bugs at compile time and improve code clarity through explicit typing.

## When to Use

- Writing new TypeScript modules, interfaces, or types
- Migrating JavaScript code to TypeScript

## When NOT to Use

- For plain JavaScript projects with no plans to adopt TypeScript
- For runtime data validation, which should use a dedicated schema library

## Prerequisites

- A configured TypeScript compiler and tsconfig.json
- Familiarity with generics, union types, and type narrowing

## Workflow

1. Define clear interfaces or types for the data involved
2. Implement logic using strict typing and avoid unnecessary any usage
3. Run the compiler and resolve all type errors before merging

## Best Practices

- Enable strict mode in tsconfig.json for new projects
- Prefer type inference where it keeps code readable

## Common Pitfalls

- Overusing the any type, defeating the purpose of static typing
- Using type assertions to silence errors instead of fixing root causes

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
