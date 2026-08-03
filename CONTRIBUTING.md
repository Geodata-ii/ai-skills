# Contributing to AI Skills

Thank you for contributing to the AI Skills library. This document describes the repository workflow, naming and directory conventions, and the checklists reviewers and authors use before a Skill is merged.

## Repository Workflow

1. Search open issues and existing Skills to avoid duplicating work.
2. Open an issue with the "New Skill Request" template describing the problem the Skill solves.
3. Wait for a maintainer to confirm the Skill is in scope before investing significant effort.
4. Create a branch, write the Skill following the standards below, and open a pull request early as a draft if useful.
5. Request review from the category's CODEOWNERS and address feedback.
6. A maintainer merges the pull request once it passes review and any automated checks.

## Branch Naming

Use the following prefixes for branches opened against this repository:

- `skill/<category>-<skill-name>` for a new Skill, for example `skill/data-zendesk-rag-export`.
- `update/<category>-<skill-name>` for changes to an existing Skill.
- `docs/<short-description>` for documentation-only changes outside of `skills/`.
- `fix/<short-description>` for corrections that are not tied to a single Skill.

## Naming Conventions

- Category names are lowercase, single words, matching an existing folder under `skills/` where possible (`ai`, `automation`, `backend`, `cloud`, `data`, `database`, `devops`, `frontend`, `security`, `support`, `testing`, `web`).
- Skill names are lowercase and kebab-case, for example `zendesk-rag-export` or `terraform-drift-check`.
- Skill names should be descriptive nouns or verb phrases, not internal project codenames.
- Do not reuse a Skill name within the same category, even if the old Skill is deprecated; append a version suffix instead, for example `pdf-extract-v2`.

## Skill Standards

Every Skill must:

- Start from [`templates/SKILL_TEMPLATE.md`](templates/SKILL_TEMPLATE.md) so metadata and section headings are consistent.
- Include complete YAML metadata: `name`, `description`, and, where applicable, `version`, `author`, `team`, `tags`, `license`, `compatibility`, and `last_updated`.
- Clearly state when the Skill should and should not be used.
- List concrete Prerequisites, including access, tools, and environment variables.
- Include at least one worked example under `examples/`.
- Avoid embedding secrets, tokens, or customer data anywhere in the Skill, including examples and assets.

## Directory Standards

Every Skill must live at `skills/<category>/<skill-name>/` and include, at minimum, `SKILL.md` and `README.md`. The `references/`, `examples/`, `assets/`, and `scripts/` folders are optional but, if created, should only contain files relevant to that Skill. Do not place loose files directly under `skills/` or under a category folder; everything belongs inside a named Skill folder.

## Documentation Requirements

`SKILL.md` must include, in order: Overview, Purpose, When to Use, When NOT to Use, Prerequisites, Workflow, Best Practices, Common Pitfalls, Debugging, Examples, and References. `README.md` should be a short summary (a few sentences) plus links back into `SKILL.md` and any `examples/`. See [`docs/writing-skills.md`](docs/writing-skills.md) and [`docs/skill-style-guide.md`](docs/skill-style-guide.md) for detailed guidance and formatting rules.

## Review Checklist

Reviewers confirm each of the following before approving:

- The Skill lives at the correct path and follows the standard directory layout.
- `SKILL.md` metadata is complete and accurate, including `version` and `last_updated`.
- Every required section is present and specific to this Skill, not boilerplate left over from the template.
- Examples run as written, or are clearly marked as illustrative pseudocode.
- No secrets, tokens, customer data, or internal-only URLs are present.
- Scripts, if present, are readable, documented, and free of destructive defaults.

## Pull Request Checklist

Before requesting review, confirm that:

- The pull request links the originating issue, if one exists.
- The PR description explains what the Skill does and why it belongs in the library.
- The branch follows the naming convention above.
- `CHANGELOG.md` is updated for new or materially changed Skills.
- CI checks (if configured) pass, and the PR template is fully filled out.

By contributing, you agree to license your contribution under the terms of the repository's [LICENSE](LICENSE).
