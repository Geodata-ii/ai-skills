# Skill Style Guide

This is the canonical reference for naming, structure, metadata, and formatting across all Skills. When in doubt, this document wins over habit or precedent from a single existing Skill.

## Naming Convention

Skill names are lowercase, kebab-case, and descriptive of the outcome, not the tool alone, for example `zendesk-rag-export` rather than `zendesk-script`. Avoid abbreviations that are not widely understood outside the originating team.

## Folder Convention

Every Skill lives at `skills/<category>/<skill-name>/` with `SKILL.md` and `README.md` at minimum, plus optional `references/`, `examples/`, `assets/`, and `scripts/` subfolders as described in the root [README.md](../README.md#skill-directory-layout). Do not nest a Skill inside another Skill's folder.

## Metadata Convention

The YAML front matter at the top of `SKILL.md` must include `name` and `description`. Include `version`, `author`, `team`, `tags`, `license`, `compatibility`, and `last_updated` whenever known. Use ISO 8601 (`YYYY-MM-DD`) for `last_updated`, and Semantic Versioning for `version`.

## Markdown Formatting

Use ATX-style headings (`#`, `##`, `###`), start `SKILL.md` at `#` for the title and `##` for each required section in the order defined by [`templates/SKILL_TEMPLATE.md`](../templates/SKILL_TEMPLATE.md). Use fenced code blocks with a language hint for commands and code. Wrap file paths, commands, and identifiers in backticks. Keep line-level prose free of trailing whitespace.

## Documentation Expectations

Every required section from the template must be present with real content; do not leave placeholder text from the template in a merged Skill. `README.md` should be readable in under a minute and link into `SKILL.md` for full detail rather than duplicating it.

## Versioning

Skills follow Semantic Versioning independently of the repository. See [`docs/review-process.md`](review-process.md#how-to-version-skills) for the full rules on when to bump major, minor, or patch versions.

## Deprecation Policy

Mark a Skill deprecated by adding `status: deprecated` to its metadata and a short notice at the top of `SKILL.md`. Deprecated Skills are kept in place, clearly marked, for at least one quarter before being moved into an `archive/` folder that mirrors their original path. See [`docs/review-process.md`](review-process.md#how-to-archive-deprecated-skills) for the full archival process.
