---
name: react
description: Guides building and reviewing React components and applications following modern best practices.
version: 1.0.0
author: geodata-ii
team: web-frontend
tags: [react, javascript, frontend]
license: MIT
compatibility: "React 18+ function component and hooks-based codebases"
last_updated: 2026-08-03
---

# React

## Overview

This Skill supports building, reviewing, and refactoring React components using modern hooks-based patterns.

## Purpose

Deliver maintainable, performant React components that follow current community best practices.

## When to Use

- Building new React components or features
- Refactoring class components to functional components with hooks

## When NOT to Use

- For non-React frontend frameworks such as Angular or Vue
- For backend or server-only logic unrelated to the UI layer

## Prerequisites

- A working React development environment and build toolchain
- Familiarity with hooks, component composition, and state management

## Workflow

1. Break the UI into small, reusable components
2. Implement state and side effects using appropriate hooks
3. Test components and verify accessibility and performance

## Best Practices

- Keep components small and focused on a single responsibility
- Memoize expensive computations and avoid unnecessary re-renders

## Common Pitfalls

- Missing or incorrect dependency arrays in useEffect
- Overusing global state for values that could remain local

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
