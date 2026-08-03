---
name: odata
description: Guides implementing and consuming OData services, covering query options and metadata design.
version: 1.0.0
author: geodata-ii
team: web-api
tags: [odata, api, query]
license: MIT
compatibility: "OData v4 services and consumers across supported backend platforms"
last_updated: 2026-08-03
---

# OData

## Overview

This Skill supports implementing and consuming OData services, including query options and metadata design.

## Purpose

Deliver standards-compliant OData services that support flexible querying for consumers.

## When to Use

- Implementing a new OData endpoint or entity set
- Integrating with an existing OData service such as Dynamics 365

## When NOT to Use

- For services that only need simple REST semantics
- For GraphQL API design

## Prerequisites

- A defined entity data model for the service
- Familiarity with OData query options such as $filter and $expand

## Workflow

1. Define the entity data model and relationships
2. Implement the service to support required query options
3. Test common query patterns against the live service

## Best Practices

- Limit which query options are exposed based on actual consumer needs
- Paginate large result sets by default

## Common Pitfalls

- Allowing unrestricted $expand depth that causes performance issues
- Exposing internal fields that were never meant to be queryable

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
