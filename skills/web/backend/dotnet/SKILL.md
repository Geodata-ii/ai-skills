---
name: dotnet
description: Guides building and reviewing .NET backend services and APIs using C# and ASP.NET Core.
version: 1.0.0
author: geodata-ii
team: web-backend
tags: [dotnet, csharp, backend]
license: MIT
compatibility: ".NET 8+ and ASP.NET Core web API projects"
last_updated: 2026-08-03
---

# .NET

## Overview

This Skill supports building and reviewing ASP.NET Core services, including controllers, dependency injection, and middleware.

## Purpose

Deliver robust, well-tested .NET backend services following idiomatic C# and ASP.NET Core patterns.

## When to Use

- Building new .NET controllers, services, or APIs
- Reviewing C# code for correctness and dependency injection patterns

## When NOT to Use

- For Microsoft Dynamics 365 F&O development (use the dedicated enterprise skill)
- For frontend-only application code

## Prerequisites

- A configured .NET SDK and solution
- Familiarity with dependency injection and the ASP.NET Core pipeline

## Workflow

1. Define the service contract and register dependencies
2. Implement controllers or services following SOLID principles
3. Write unit and integration tests before merging

## Best Practices

- Use constructor injection for dependencies rather than service locators
- Return appropriate HTTP status codes and problem details on errors

## Common Pitfalls

- Registering services with an incorrect dependency injection lifetime
- Catching exceptions too broadly and hiding real errors

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
