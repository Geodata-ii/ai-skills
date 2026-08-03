# Changelog

All notable changes to this repository are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and repository-level releases follow [Semantic Versioning](https://semver.org/). Individual Skills track their own `version` field in `SKILL.md`; significant Skill-level changes should be noted here as well as in the Skill's own documentation.

## [Unreleased]

### Added

- Initial repository scaffolding: README, CONTRIBUTING, CODE_OF_CONDUCT, SECURITY, LICENSE, issue and pull request templates, CODEOWNERS, and contributor documentation under `docs/`.
- Skill category folders under `skills/` for ai, automation, backend, cloud, data, database, devops, frontend, security, support, testing, and web.
- Reusable Skill template at `templates/SKILL_TEMPLATE.md`.
- First example Skill: `skills/data/zendesk-rag-export`.

## How to Update This File

When your pull request adds a new Skill, removes one, or makes a change significant enough to affect existing users, add an entry under `[Unreleased]` in the appropriate category (Added, Changed, Deprecated, Removed, Fixed, or Security). Maintainers move `[Unreleased]` entries into a dated, versioned section at release time.
