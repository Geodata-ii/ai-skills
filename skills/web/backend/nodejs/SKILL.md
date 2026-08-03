---
name: nodejs
description: Guides building and reviewing Node.js backend services, covering APIs, async patterns, and performance.
version: 1.0.0
author: geodata-ii
team: web-backend
tags: [nodejs, javascript, backend]
license: MIT
compatibility: "Node.js 18+ LTS runtimes and common backend frameworks"
last_updated: 2026-08-03
---

# Node.js

## Overview

This Skill supports building and reviewing Node.js backend services, including APIs, middleware, and async workflows.

## Purpose

Deliver reliable, performant Node.js services that handle concurrency and errors correctly.

## When to Use

- Building new Node.js API endpoints or services
- Reviewing Node.js code for async correctness and error handling

## When NOT to Use

- For frontend-only JavaScript or browser code
- For backend services written in other runtimes such as .NET or Java

## Prerequisites

- A configured Node.js project with package.json
- Familiarity with async/await, streams, and the event loop

## Workflow

1. Define the endpoint or service contract clearly
2. Implement using async/await with proper error handling
3. Test under expected load and verify graceful failure behavior

## Best Practices

- Always handle promise rejections explicitly
- Avoid blocking the event loop with synchronous, CPU-heavy operations

## Common Pitfalls

- Unhandled promise rejections crashing the process
- Missing input validation on public-facing endpoints

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
