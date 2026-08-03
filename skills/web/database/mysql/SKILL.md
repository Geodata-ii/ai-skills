---
name: mysql
description: Guides designing, querying, and tuning MySQL databases and workloads.
version: 1.0.0
author: geodata-ii
team: web-database
tags: [mysql, sql, database]
license: MIT
compatibility: "MySQL 8+ self-hosted or managed instances"
last_updated: 2026-08-03
---

# MySQL

## Overview

This Skill supports designing schemas, writing queries, and tuning performance for MySQL databases.

## Purpose

Deliver well-designed, performant MySQL databases that scale with application needs.

## When to Use

- Designing a new schema or table structure in MySQL
- Diagnosing slow queries or indexing issues

## When NOT to Use

- For non-relational database technologies such as MongoDB
- For other relational engines such as Azure SQL or PostgreSQL

## Prerequisites

- Access to the MySQL instance and slow query logs
- Familiarity with SQL and MySQL-specific indexing options

## Workflow

1. Design tables and relationships to match query access patterns
2. Write and review SQL queries and indexes for performance
3. Validate using EXPLAIN and the slow query log

## Best Practices

- Use InnoDB for tables requiring transactions and foreign keys
- Review the slow query log regularly to catch regressions early

## Common Pitfalls

- Using the wrong storage engine for the workload
- Ignoring character set and collation mismatches between tables

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
