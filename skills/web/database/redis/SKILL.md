---
name: redis
description: Guides using Redis effectively for caching, session storage, and lightweight messaging.
version: 1.0.0
author: geodata-ii
team: web-database
tags: [redis, caching, database]
license: MIT
compatibility: "Redis 7+ self-hosted or managed instances"
last_updated: 2026-08-03
---

# Redis

## Overview

This Skill supports using Redis effectively for caching, session storage, and lightweight messaging patterns.

## Purpose

Improve application performance and reliability through appropriate use of Redis caching and data structures.

## When to Use

- Adding caching for expensive or frequently-read data
- Implementing session storage or rate limiting

## When NOT to Use

- As the primary system of record for critical durable data
- For complex relational queries better suited to a SQL database

## Prerequisites

- Access to the Redis instance and monitoring metrics
- Familiarity with Redis data structures and expiration policies

## Workflow

1. Identify the data or workload that would benefit from caching
2. Choose the appropriate Redis data structure and expiration policy
3. Monitor cache hit rates and memory usage after deployment

## Best Practices

- Set explicit expiration times to avoid unbounded memory growth
- Use the appropriate data structure for the access pattern

## Common Pitfalls

- Treating Redis as durable storage without appropriate persistence configuration
- Storing very large values that degrade overall performance

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
