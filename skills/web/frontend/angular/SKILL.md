---
name: angular
description: Guides development of Angular applications, covering components, services, and module architecture.
version: 1.0.0
author: geodata-ii
team: web-frontend
tags: [angular, typescript, frontend]
license: MIT
compatibility: "Angular 15+ standalone and module-based applications"
last_updated: 2026-08-03
---

# Angular

## Overview

This Skill supports building and reviewing Angular applications, including components, services, and dependency injection.

## Purpose

Deliver maintainable Angular applications structured around clear component and service boundaries.

## When to Use

- Building new Angular components, services, or modules
- Reviewing Angular code for structure and dependency injection patterns

## When NOT to Use

- For non-Angular frontend frameworks such as React or Vue
- For backend API implementation unrelated to the Angular client

## Prerequisites

- A configured Angular CLI project
- Familiarity with Angular modules, components, and dependency injection

## Workflow

1. Define the component or service responsibility clearly
2. Implement using Angular CLI generators and idiomatic patterns
3. Test the component or service in isolation before integration

## Best Practices

- Favor standalone components for new development where appropriate
- Use reactive forms and RxJS observables for complex state and input

## Common Pitfalls

- Forgetting to unsubscribe from observables, causing memory leaks
- Overusing shared mutable state across unrelated components

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
