---
name: windows-vm
description: Guides provisioning and managing Windows virtual machines on Azure.
version: 1.0.0
author: geodata-ii
team: cloud-infrastructure
tags: [azure, windows, virtual-machine]
license: MIT
compatibility: "Azure Windows Server virtual machines"
last_updated: 2026-08-03
---

# Windows VM

## Overview

This Skill supports provisioning, configuring, and maintaining Windows Server virtual machines on Azure.

## Purpose

Deliver secure, properly sized Windows VMs that meet workload and compliance requirements.

## When to Use

- Provisioning a new Windows Server VM in Azure
- Reviewing VM sizing, networking, or security configuration

## When NOT to Use

- For Linux-based VMs (use the ubuntu-server skill)
- For shared hosting environments managed through cPanel or GoDaddy

## Prerequisites

- An active Azure subscription and resource group
- Defined sizing, networking, and security requirements

## Workflow

1. Select an appropriate VM size and Windows Server image
2. Configure networking, security groups, and access controls
3. Provision the VM and validate connectivity and performance

## Best Practices

- Restrict RDP access using network security groups or a bastion host
- Enable automatic patching and monitoring on all production VMs

## Common Pitfalls

- Leaving RDP open to the public internet
- Oversizing VMs, leading to unnecessary cost

## References

- See docs/skill-style-guide.md and docs/best-practices.md for repository-wide conventions.
