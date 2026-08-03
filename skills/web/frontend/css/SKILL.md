---
name: css
description: Guides writing maintainable, responsive CSS using modern layout techniques.
version: 1.0.0
author: geodata-ii
team: web-frontend
tags: [css, styling, responsive-design]
license: MIT
compatibility: "Modern CSS3 including Flexbox, Grid, and container queries"
last_updated: 2026-08-03
---

# CSS

## Overview

This Skill supports writing clean, maintainable CSS using modern layout tools such as Flexbox and Grid.

## Purpose

Deliver responsive, accessible layouts that are easy to maintain across browsers and screen sizes.

## When to Use

- Building new layouts or responsive components
- Debugging layout or cross-browser rendering issues

## When NOT to Use

- For projects standardized entirely on a utility-first framework like Tailwind
- For JavaScript-driven animation logic unrelated to styling

## Prerequisites

- A defined design or layout specification
- Target browser and device support requirements

## Workflow

1. Choose the appropriate layout method for the component
2. Implement styles with responsive breakpoints in mind
3. Test across target browsers and screen sizes

## Best Practices

- Use CSS Grid for two-dimensional layouts and Flexbox for one-dimensional ones
- Use relative units for sizing to support accessibility and responsiveness

## Common Pitfalls

- Overusing fixed pixel values instead of relative units
- Relying on overly specific selectors that are hard to override

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
