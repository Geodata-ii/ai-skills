---
name: mongodb
description: Guides designing document schemas and queries for MongoDB collections.
version: 1.0.0
author: geodata-ii
team: web-database
tags: [mongodb, nosql, database]
license: MIT
compatibility: "MongoDB 6+ self-hosted or Atlas-managed clusters"
last_updated: 2026-08-03
---

# MongoDB

## Overview

This Skill supports designing document schemas and writing efficient queries for MongoDB collections.

## Purpose

Deliver well-modeled, performant MongoDB collections suited to their access patterns.

## When to Use

- Designing a new document schema or collection structure
- Diagnosing slow queries or missing indexes

## When NOT to Use

- For relational database technologies such as PostgreSQL or MySQL
- For simple key-value caching needs (use the Redis skill instead)

## Prerequisites

- Access to the MongoDB cluster and query profiler
- Familiarity with the application's read and write access patterns

## Workflow

1. Model documents around how the application queries the data
2. Define indexes to support the most frequent query patterns
3. Validate performance using the query profiler and explain plans

## Best Practices

- Embed related data that is always read together
- Reference data that grows unbounded or is shared across documents

## Common Pitfalls

- Creating unbounded arrays within a single document
- Running queries without supporting indexes on large collections

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
