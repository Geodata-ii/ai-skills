---
name: java
description: Guides building and reviewing Java backend services and APIs using Spring and related frameworks.
version: 1.0.0
author: geodata-ii
team: web-backend
tags: [java, spring, backend]
license: MIT
compatibility: "Java 17+ with Spring Boot or comparable backend frameworks"
last_updated: 2026-08-03
---

# Java

## Overview

This Skill supports building and reviewing Java backend services, including Spring Boot controllers and services.

## Purpose

Deliver robust, testable Java services that follow idiomatic Spring and object-oriented design patterns.

## When to Use

- Building new Java services, controllers, or APIs
- Reviewing Java code for design and dependency injection patterns

## When NOT to Use

- For Android mobile application development
- For frontend-only application code

## Prerequisites

- A configured Java project using Maven or Gradle
- Familiarity with the Spring dependency injection container

## Workflow

1. Define the service interface and its responsibilities
2. Implement using constructor injection and clear layering
3. Write unit and integration tests before merging

## Best Practices

- Favor constructor injection over field injection
- Keep controllers thin and push logic into service classes

## Common Pitfalls

- Overusing field injection, making testing harder
- Catching and swallowing exceptions without proper logging

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
