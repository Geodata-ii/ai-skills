---
name: power-bi-performance
description: Diagnoses and resolves end-to-end Power BI performance issues spanning data load, model, and report layers.
version: 1.0.0
author: geodata-ii
team: power-platform
tags: [power-bi, performance, optimization]
license: MIT
compatibility: "Power BI Desktop and Power BI Service reports and dataflows"
last_updated: 2026-08-03
---

# Power BI Performance

## Overview

This Skill diagnoses Power BI performance bottlenecks across data refresh, model design, and report rendering.

## Purpose

Deliver responsive Power BI solutions that meet acceptable load and refresh time targets.

## When to Use

- Users report a Power BI report or dataset is slow
- Scheduled dataset refreshes are exceeding time limits

## When NOT to Use

- For a single, already-isolated DAX measure issue (use dax-optimization instead)
- For visual design or aesthetic feedback unrelated to speed

## Prerequisites

- Access to Performance Analyzer and refresh history logs
- Defined performance targets for load and refresh times

## Workflow

1. Isolate whether the bottleneck is in data load, model, or visuals
2. Apply targeted fixes such as query folding, aggregations, or visual reduction
3. Measure results against the defined performance targets

## Best Practices

- Use incremental refresh for large, slowly-changing datasets
- Limit the number of visuals per report page

## Common Pitfalls

- Importing far more data than the report actually needs
- Ignoring query folding, forcing transformations to run client-side

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
