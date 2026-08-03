---
name: data-model-review
description: Reviews Power BI data models for proper relationships, schema design, and scalability.
version: 1.0.0
author: geodata-ii
team: power-platform
tags: [power-bi, data-model, schema-design]
license: MIT
compatibility: "Power BI Desktop and Analysis Services tabular data models"
last_updated: 2026-08-03
---

# Data Model Review

## Overview

This Skill assesses Power BI data model structure, relationships, and schema design for correctness and scalability.

## Purpose

Ensure data models follow star-schema principles and scale well as data volume grows.

## When to Use

- Designing a new data model for a Power BI solution
- Investigating unexpected or incorrect aggregation results

## When NOT to Use

- For reviewing visual layout or dashboard design
- For tuning individual DAX measure performance

## Prerequisites

- Access to the data model view in Power BI Desktop
- Understanding of the source data and reporting requirements

## Workflow

1. Review table relationships and cardinality for correctness
2. Check for star-schema alignment and unnecessary bidirectional filters
3. Recommend schema changes to improve accuracy and performance

## Best Practices

- Favor a star schema with clear fact and dimension tables
- Avoid bidirectional relationships unless explicitly required

## Common Pitfalls

- Using a flat, denormalized single-table model for complex reporting
- Creating many-to-many relationships without a bridge table

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
