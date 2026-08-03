---
name: postgresql
description: Guides designing, querying, and tuning PostgreSQL databases and workloads.
version: 1.0.0
author: geodata-ii
team: web-database
tags: [postgresql, sql, database]
license: MIT
compatibility: "PostgreSQL 14+ self-hosted or managed instances"
last_updated: 2026-08-03
---

# PostgreSQL

## Overview

This Skill supports designing schemas, writing queries, and tuning performance for PostgreSQL databases.

## Purpose

Deliver well-designed, performant PostgreSQL databases that scale with application needs.

## When to Use

- Designing a new schema or table structure in PostgreSQL
- Diagnosing slow queries or indexing issues

## When NOT to Use

- For non-relational database technologies such as MongoDB
- For other relational engines such as Azure SQL or MySQL

## Prerequisites

- Access to the PostgreSQL instance and query performance tools
- Familiarity with SQL and PostgreSQL-specific indexing options

## Workflow

1. Design tables and relationships to match query access patterns
2. Write and review SQL queries and indexes for performance
3. Validate using EXPLAIN ANALYZE and performance metrics

## Best Practices

- Use EXPLAIN ANALYZE to validate query plans before deploying
- Use appropriate data types and constraints to enforce integrity

## Common Pitfalls

- Missing indexes on frequently filtered or joined columns
- Letting table or index bloat go unmonitored over time

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
