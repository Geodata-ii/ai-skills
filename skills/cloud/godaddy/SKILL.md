---
name: godaddy
description: Guides managing domains, DNS, and hosting configuration through GoDaddy.
version: 1.0.0
author: geodata-ii
team: cloud-infrastructure
tags: [godaddy, dns, hosting]
license: MIT
compatibility: "GoDaddy domain, DNS, and hosting management console"
last_updated: 2026-08-03
---

# GoDaddy

## Overview

This Skill supports managing domains, DNS records, and hosting configuration through the GoDaddy platform.

## Purpose

Ensure domains and DNS records are configured correctly and safely for production use.

## When to Use

- Configuring or updating DNS records for a domain
- Setting up or renewing domain and hosting services

## When NOT to Use

- For managing infrastructure hosted on Azure or other cloud providers
- For cPanel-specific hosting management (use the cpanel skill)

## Prerequisites

- Access to the GoDaddy account and domain management console
- Awareness of DNS propagation timing and rollback plans

## Workflow

1. Document the current DNS configuration before making changes
2. Apply the required DNS or domain changes carefully
3. Verify propagation and confirm the service is reachable

## Best Practices

- Record the previous DNS state before any change for easy rollback
- Use low TTL values temporarily when planning a DNS cutover

## Common Pitfalls

- Changing DNS records without a documented rollback path
- Forgetting that domain renewals can lapse and cause outages

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
