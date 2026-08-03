---
name: dashboard-review
description: Reviews Power BI dashboards for clarity, accuracy, and adherence to visualization best practices.
version: 1.0.0
author: geodata-ii
team: power-platform
tags: [power-bi, dashboard, review]
license: MIT
compatibility: "Power BI Desktop and Power BI Service dashboards and reports"
last_updated: 2026-08-03
---

# Dashboard Review

## Overview

This Skill evaluates Power BI dashboards for visual clarity, data accuracy, and usability before they are shared with stakeholders.

## Purpose

Ensure dashboards communicate accurate insights clearly to their intended audience.

## When to Use

- Before publishing a new or updated dashboard to stakeholders
- When a dashboard is reported as confusing or misleading

## When NOT to Use

- For reviewing the underlying DAX measures in detail (use dax-optimization instead)
- For early-stage wireframes not yet built in Power BI

## Prerequisites

- Access to the published dashboard or the .pbix file
- Knowledge of the intended audience and business questions the dashboard should answer

## Workflow

1. Verify that visuals accurately reflect the underlying data
2. Assess layout, labeling, and chart choice for clarity
3. Provide feedback and confirm fixes before final publication

## Best Practices

- Match chart types to the message being conveyed
- Keep dashboards focused on a small number of key metrics

## Common Pitfalls

- Overloading a single dashboard page with too many visuals
- Using inconsistent color coding across related visuals

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
