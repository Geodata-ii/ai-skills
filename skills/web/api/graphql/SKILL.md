---
name: graphql
description: Guides designing and reviewing GraphQL schemas, resolvers, and query performance.
version: 1.0.0
author: geodata-ii
team: web-api
tags: [graphql, api, schema-design]
license: MIT
compatibility: "Any GraphQL server implementation regardless of backend language"
last_updated: 2026-08-03
---

# GraphQL

## Overview

This Skill guides the design and review of GraphQL schemas, resolvers, and query efficiency.

## Purpose

Deliver flexible, well-typed GraphQL APIs that avoid common performance pitfalls.

## When to Use

- Designing a new GraphQL schema or type
- Reviewing resolvers for N+1 query issues

## When NOT to Use

- For REST API design (use the dedicated REST skill)
- For simple internal services that don't need flexible querying

## Prerequisites

- A defined data model and the queries consumers need to run
- Familiarity with GraphQL types, resolvers, and the N+1 problem

## Workflow

1. Design the schema types and relationships around consumer needs
2. Implement resolvers using batching to avoid N+1 query patterns
3. Test query performance under realistic nested query patterns

## Best Practices

- Use a data loader pattern to batch and cache related lookups
- Set query complexity or depth limits to prevent abuse

## Common Pitfalls

- Allowing unbounded nested queries that degrade performance
- Resolving related fields with naive per-item database calls

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
