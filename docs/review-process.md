# Review Process

This document describes how Skills move from proposal to merged, how maintainers approve them, and how they are later archived or versioned.

## How Skills Are Reviewed

Every pull request that adds or changes a Skill is reviewed against the checklist in [`CONTRIBUTING.md`](../CONTRIBUTING.md#review-checklist). Reviewers check that the directory structure and metadata are correct, that every required section of `SKILL.md` is present and specific to the Skill, that examples work as written, and that no secrets or customer data are included. Reviewers may ask for changes, leave suggestions, or approve outright.

## How Maintainers Approve Skills

Each Skill category has one or more maintainers listed in [`.github/CODEOWNERS`](../.github/CODEOWNERS). GitHub automatically requests review from the relevant maintainers based on the files changed in a pull request. At least one approval from a maintainer of the affected category is required before merge; larger or cross-cutting changes may require sign-off from more than one category.

## How to Version Skills

Skills use their own `version` field, independent of the repository's overall history. A new Skill starts at `1.0.0`. Bump the patch number for corrections that do not change behavior, the minor number for backward-compatible improvements, and the major number for changes that break how the Skill is used. Always update `last_updated` alongside a version bump.

## How to Archive Deprecated Skills

When a Skill is superseded or no longer applicable, add a `status: deprecated` field to its metadata and a short notice at the top of `SKILL.md` pointing to its replacement, if any. Deprecated Skills remain in place for at least one full quarter before being moved to an `archive/` folder mirroring their original category path, so existing links do not immediately break. Record the deprecation and archival in [`CHANGELOG.md`](../CHANGELOG.md).

## How to Report Issues

Use the "Bug report" issue template for problems with an existing Skill, and the "New Skill request" template to propose new work. Security issues should follow the process in [`SECURITY.md`](../SECURITY.md) instead of a public issue.
