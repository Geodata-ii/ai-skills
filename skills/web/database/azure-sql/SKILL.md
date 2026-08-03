---
name: azure-sql
description: Guides designing, querying, and tuning Azure SQL Database schemas and workloads.
version: 1.0.0
author: geodata-ii
team: web-database
tags: [azure-sql, sql, database]
license: MIT
compatibility: "Azure SQL Database and Azure SQL Managed Instance"
last_updated: 2026-08-03
---

# Azure SQL

## Overview

This Skill supports designing schemas, writing queries, and tuning performance for Azure SQL Database.

## Purpose

Deliver well-designed, performant Azure SQL databases that scale with application needs.

## When to Use

- Designing a new schema or table structure in Azure SQL
- Diagnosing slow queries or indexing issues

## When NOT to Use

- For non-relational database technologies such as MongoDB
- For other relational engines such as PostgreSQL or MySQL

## Prerequisites

- Access to the Azure SQL Database and query performance insights
- Familiarity with T-SQL and indexing strategies

## Workflow

1. Design tables and relationships to match query access patterns
2. Write and review T-SQL queries and indexes for performance
3. Validate using execution plans and performance metrics

## Best Practices

- Index columns used frequently in WHERE and JOIN clauses
- Use parameterized queries to enable plan reuse and prevent injection

## Common Pitfalls

- Over-indexing tables, slowing down writes
- Writing queries that force full table scans on large tables

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
