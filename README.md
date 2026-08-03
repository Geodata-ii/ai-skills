# AI Skills

Community-driven repository for reusable AI skills, prompts, workflows, and best practices shared across the organization.

## Overview

This repository is the central library of **AI Skills** used across our engineering organization. A "Skill" is a self-contained, documented, and versioned unit of expertise -- a workflow, prompt pattern, script, or set of instructions -- that helps engineers and AI assistants perform a recurring task consistently and correctly.

The goal is to stop re-solving the same problems in isolated repos, chat threads, and personal notes, and instead build a shared, reviewed, and continuously improving knowledge base that any team can discover and reuse.

This project draws inspiration from Anthropic's public [skills](https://github.com/anthropics/skills) repository, adapted for a multi-team engineering organization with a formal review and contribution process.

## Goals

- Create a centralized library of reusable AI Skills.
- Encourage collaboration and knowledge-sharing across engineering teams.
- Standardize how Skills are written, structured, and documented.
- Preserve domain knowledge that would otherwise live only with individuals.
- Maintain a high bar for quality through a lightweight but real review process.

## Repository Structure

```
ai-skills/
├── .github/                # Issue templates, PR template, CODEOWNERS
├── docs/                   # Contributor and process documentation
├── templates/              # Reusable templates (e.g. SKILL_TEMPLATE.md)
├── skills/                 # The Skill library, organized by category
│   ├── ai/
│   ├── automation/
│   ├── backend/
│   ├── cloud/
│   ├── data/
│   ├── database/
│   ├── devops/
│   ├── frontend/
│   ├── security/
│   ├── support/
│   ├── testing/
│   └── web/
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── CHANGELOG.md
└── LICENSE
```

## Skill Directory Layout

Every Skill lives under `skills/<category>/<skill-name>/` and follows the same internal layout so that Skills are predictable to navigate and easy to automate against:

```
skills/<category>/<skill-name>/
├── SKILL.md         # Required. Metadata + full skill documentation
├── README.md        # Short human-facing summary and quick links
├── references/      # Supporting reference material (specs, API docs, notes)
├── examples/        # Worked examples / sample inputs and outputs
├── assets/          # Diagrams, images, or static files used by the skill
└── scripts/         # Optional automation scripts the skill relies on
```

See [`templates/SKILL_TEMPLATE.md`](templates/SKILL_TEMPLATE.md) for the canonical template and [`docs/skill-style-guide.md`](docs/skill-style-guide.md) for naming and formatting conventions.

## How to Install a Skill

Skills in this repository are plain Markdown and files, so installing one simply means bringing it into the context of the tool or assistant you are using:

1. Browse `skills/<category>/` to find the Skill you need.
2. Read the Skill's `README.md` for a quick overview, then `SKILL.md` for full detail.
3. Copy the Skill folder (or just `SKILL.md`) into the location your tooling expects, or reference it directly from a cloned copy of this repository.
4. Follow the Prerequisites and Workflow sections in `SKILL.md` before use.
5. If the Skill has a `scripts/` directory, review the scripts before running them, and confirm any required environment variables or access.

## How to Contribute

We welcome contributions from every team. Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) in full before opening a pull request -- it covers branch naming, directory standards, and the review checklist. A short summary follows.

### Contribution Workflow

1. Open an issue using the "New Skill Request" template to propose the Skill, unless one already exists.
2. Create a branch using the naming convention `skill/<category>-<skill-name>`.
3. Scaffold the Skill using [`templates/SKILL_TEMPLATE.md`](templates/SKILL_TEMPLATE.md) and the standard directory layout above.
4. Write the documentation: Overview, Purpose, When to Use, When Not to Use, Prerequisites, Workflow, Best Practices, Common Pitfalls, Debugging, Examples, and References.
5. Open a pull request using the PR template and link the originating issue.
6. Address review feedback from the relevant CODEOWNERS.
7. Merge once approved by at least one maintainer for the category.

### Skill Review Process

Every new or updated Skill goes through the same review process, documented in full in [`docs/review-process.md`](docs/review-process.md):

- Automated checks confirm the required directory structure and `SKILL.md` metadata are present.
- A category maintainer, listed in [`.github/CODEOWNERS`](.github/CODEOWNERS), reviews the pull request for accuracy, clarity, and adherence to the style guide.
- At least one approval is required before merge.
- Significant changes to an existing Skill should bump its `version` field and add an entry to [`CHANGELOG.md`](CHANGELOG.md).

### Coding Standards

- Documentation is written in Markdown and should render cleanly on GitHub.
- Scripts should be linted, include usage instructions, and never contain hard-coded secrets or credentials.
- Prefer languages and runtimes already used across the organization (Python, TypeScript/Node.js, Bash) unless the Skill specifically requires otherwise.
- Every Skill must declare its Prerequisites explicitly, including required tools, access, and environment variables.
- Keep examples runnable and minimal; link out to `references/` for deep detail instead of inlining everything into `SKILL.md`.

## Frequently Asked Questions

**Who can contribute a Skill?** Any engineer in the organization. See [`CONTRIBUTING.md`](CONTRIBUTING.md) for the workflow.

**Who approves new Skills?** The maintainers listed for each category in [`.github/CODEOWNERS`](.github/CODEOWNERS).

**What happens to Skills that become outdated?** They are deprecated and eventually archived following the process in [`docs/skill-style-guide.md`](docs/skill-style-guide.md).

**Can a Skill depend on internal or private tools?** Yes, but this must be stated clearly in the Skill's Prerequisites section so contributors without access can make an informed decision.

**Where do I ask questions?** Open a GitHub Discussion, or an issue using the "question" label.

## License

This repository is licensed under the [MIT License](LICENSE). Individual Skills may reference third-party tools or content that carry their own licenses; check a Skill's `references/` folder for details when applicable.
