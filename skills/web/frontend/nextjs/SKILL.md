---
name: nextjs
description: Guides development of Next.js applications, covering routing, rendering strategies, and deployment.
version: 1.0.0
author: geodata-ii
team: web-frontend
tags: [nextjs, react, ssr]
license: MIT
compatibility: "Next.js 13+ App Router and Pages Router projects"
last_updated: 2026-08-03
---

# Next.js

## Overview

This Skill supports building Next.js applications, including routing, data fetching, and rendering strategy decisions.

## Purpose

Deliver fast, SEO-friendly Next.js applications using the most appropriate rendering strategy per route.

## When to Use

- Building new pages or routes in a Next.js application
- Choosing between static generation, server rendering, or client rendering

## When NOT to Use

- For plain client-side React applications without server rendering needs
- For non-JavaScript backend service development

## Prerequisites

- A Next.js project with a defined routing structure
- Familiarity with server components, client components, and data fetching patterns

## Workflow

1. Determine the appropriate rendering strategy for the route
2. Implement the page using server or client components as appropriate
3. Validate build output, performance, and SEO metadata

## Best Practices

- Default to server components unless client interactivity is required
- Use built-in image and font optimization features

## Common Pitfalls

- Marking components as client-side unnecessarily, hurting performance
- Fetching data in a way that blocks the entire page from rendering

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
