---
name: cpanel
description: Guides managing websites, email, and databases through cPanel hosting control panels.
version: 1.0.0
author: geodata-ii
team: cloud-infrastructure
tags: [cpanel, hosting, web-server]
license: MIT
compatibility: "cPanel and WHM-based shared or VPS hosting environments"
last_updated: 2026-08-03
---

# cPanel

## Overview

This Skill supports managing websites, email accounts, and databases through cPanel and WHM control panels.

## Purpose

Ensure shared hosting environments are configured securely and remain reliable.

## When to Use

- Setting up a new website, email account, or database in cPanel
- Troubleshooting hosting configuration or access issues

## When NOT to Use

- For domain registration or DNS-only tasks (use the godaddy skill)
- For managing cloud infrastructure hosted on Azure

## Prerequisites

- Access to the cPanel or WHM account
- A backup of the current site or database before making changes

## Workflow

1. Back up the site, database, or email configuration before changes
2. Apply the configuration change through the appropriate cPanel tool
3. Verify the site or service functions correctly after the change

## Best Practices

- Take a full backup before any significant configuration change
- Use strong, unique passwords for each cPanel and email account

## Common Pitfalls

- Making production changes without a recent backup
- Leaving unused subdomains or email accounts active and unmonitored

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
