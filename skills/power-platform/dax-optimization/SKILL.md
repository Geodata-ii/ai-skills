---
name: dax-optimization
description: Improves the performance of DAX measures and calculated columns in Power BI data models.
version: 1.0.0
author: geodata-ii
team: power-platform
tags: [power-bi, dax, performance]
license: MIT
compatibility: "Power BI Desktop, Power BI Service, and Analysis Services tabular models"
last_updated: 2026-08-03
---

# DAX Optimization

## Overview

This Skill identifies and resolves slow-performing DAX measures and calculated columns in Power BI data models.

## Purpose

Reduce report load times and improve responsiveness by optimizing inefficient DAX logic.

## When to Use

- A report or dashboard is loading or refreshing slowly
- Performance Analyzer identifies a specific measure as a bottleneck

## When NOT to Use

- For visual design or layout issues unrelated to calculation speed
- When the bottleneck is confirmed to be data source or gateway latency

## Prerequisites

- Access to the .pbix file and its data model
- DAX Studio or Performance Analyzer for profiling query performance

## Workflow

1. Profile the report to identify the slowest-running measures
2. Rewrite the DAX using more efficient functions or variables
3. Re-test performance to confirm measurable improvement

## Best Practices

- Use variables to avoid recalculating the same expression multiple times
- Prefer simple filter contexts over nested iterators where possible

## Common Pitfalls

- Overusing calculated columns instead of measures
- Nesting multiple iterator functions without checking for simpler alternatives

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
