---
name: tailwind
description: Guides styling web interfaces efficiently using Tailwind CSS utility classes.
version: 1.0.0
author: geodata-ii
team: web-frontend
tags: [tailwind, css, styling]
license: MIT
compatibility: "Tailwind CSS 3+ projects across any frontend framework"
last_updated: 2026-08-03
---

# Tailwind

## Overview

This Skill supports building consistent, responsive UI styling using Tailwind CSS utility classes.

## Purpose

Enable fast, consistent UI development without writing large amounts of custom CSS.

## When to Use

- Styling new components or pages with Tailwind CSS
- Refactoring custom CSS into Tailwind utility classes

## When NOT to Use

- For projects that have standardized on a different CSS methodology
- For highly complex, one-off animations better suited to custom CSS

## Prerequisites

- A project with Tailwind CSS installed and configured
- The project's design tokens or Tailwind config for spacing and color

## Workflow

1. Identify the layout and spacing requirements for the component
2. Apply utility classes consistently with the project's design tokens
3. Extract repeated utility patterns into reusable components or classes

## Best Practices

- Use the project's theme configuration instead of arbitrary values
- Extract repeated class combinations into components rather than duplicating them

## Common Pitfalls

- Overusing arbitrary value syntax instead of theme-based utilities
- Producing unreadably long class lists without componentization

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
