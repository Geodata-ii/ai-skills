---
name: vue
description: Guides development of Vue.js applications, covering composition API, components, and state management.
version: 1.0.0
author: geodata-ii
team: web-frontend
tags: [vue, javascript, frontend]
license: MIT
compatibility: "Vue 3 Composition API and Options API applications"
last_updated: 2026-08-03
---

# Vue

## Overview

This Skill supports building and reviewing Vue.js applications using the Composition API and single-file components.

## Purpose

Deliver maintainable Vue.js components with clear separation of logic, template, and style.

## When to Use

- Building new Vue components or features
- Migrating Options API components to the Composition API

## When NOT to Use

- For non-Vue frontend frameworks such as React or Angular
- For backend service logic unrelated to the Vue client

## Prerequisites

- A configured Vue project using Vite or the Vue CLI
- Familiarity with reactivity, computed properties, and lifecycle hooks

## Workflow

1. Break the UI into focused single-file components
2. Implement reactive state and computed values using the Composition API
3. Test components and verify reactivity behaves as expected

## Best Practices

- Prefer the Composition API for new, non-trivial components
- Extract reusable logic into composables

## Common Pitfalls

- Mutating props directly instead of emitting events to the parent
- Losing reactivity by destructuring reactive objects incorrectly

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
