---
name: rest
description: Guides designing and reviewing RESTful APIs for consistency, versioning, and resource modeling.
version: 1.0.0
author: geodata-ii
team: web-api
tags: [rest, api, http]
license: MIT
compatibility: "Any HTTP-based REST API regardless of backend language"
last_updated: 2026-08-03
---

# REST

## Overview

This Skill guides the design and review of RESTful APIs, focusing on resource modeling, status codes, and versioning.

## Purpose

Deliver predictable, well-documented REST APIs that are easy for consumers to integrate with.

## When to Use

- Designing new REST API endpoints or resources
- Reviewing existing APIs for consistency and versioning issues

## When NOT to Use

- For GraphQL API design (use the dedicated GraphQL skill)
- For internal RPC calls that don't follow REST conventions

## Prerequisites

- A defined set of resources and consumer use cases
- Familiarity with HTTP methods, status codes, and REST conventions

## Workflow

1. Model resources and their relationships around nouns, not actions
2. Define endpoints, status codes, and request/response schemas
3. Document the API and validate it against real consumer needs

## Best Practices

- Use plural nouns for resource collections and consistent naming
- Version the API explicitly to avoid breaking existing consumers

## Common Pitfalls

- Using verbs in endpoint URLs instead of representing actions via HTTP methods
- Returning inconsistent error response formats across endpoints

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
