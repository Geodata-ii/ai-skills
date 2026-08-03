---
name: ubuntu-server
description: Guides provisioning and managing Ubuntu Server virtual machines on Azure.
version: 1.0.0
author: geodata-ii
team: cloud-infrastructure
tags: [azure, ubuntu, virtual-machine]
license: MIT
compatibility: "Azure Ubuntu Server virtual machines"
last_updated: 2026-08-03
---

# Ubuntu Server

## Overview

This Skill supports provisioning, configuring, and maintaining Ubuntu Server virtual machines on Azure.

## Purpose

Deliver secure, properly sized Ubuntu Server VMs that meet workload requirements.

## When to Use

- Provisioning a new Ubuntu Server VM in Azure
- Reviewing VM sizing, networking, or security configuration

## When NOT to Use

- For Windows-based VMs (use the windows-vm skill)
- For shared hosting environments managed through cPanel or GoDaddy

## Prerequisites

- An active Azure subscription and resource group
- Defined sizing, networking, and security requirements

## Workflow

1. Select an appropriate VM size and Ubuntu Server image
2. Configure networking, security groups, and SSH access
3. Provision the VM and validate connectivity and performance

## Best Practices

- Use SSH key authentication instead of passwords
- Enable automatic security updates and monitoring

## Common Pitfalls

- Leaving SSH open to the public internet on port 22
- Skipping regular OS and package updates

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
