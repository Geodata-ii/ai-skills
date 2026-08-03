# Writing Skills

This guide walks through writing a new Skill from scratch, from scaffolding the folder to preparing it for review. For formatting and naming rules, see [`skill-style-guide.md`](skill-style-guide.md); for what reviewers look for, see [`review-process.md`](review-process.md).

## 1. Confirm the Skill Doesn't Already Exist

Search `skills/` and open issues for similar work. If something close exists, consider improving it instead of creating a near-duplicate.

## 2. Scaffold the Folder

Create `skills/<category>/<skill-name>/` and copy [`templates/SKILL_TEMPLATE.md`](../templates/SKILL_TEMPLATE.md) into it as `SKILL.md`. Add a short `README.md`, and create `references/`, `examples/`, `assets/`, or `scripts/` only if you have content for them.

## 3. Fill In the Metadata

Set `name` and `description` at minimum. Add `version` (start at `1.0.0`), `author`, `team`, `tags`, `license`, `compatibility`, and `last_updated` whenever they apply. Accurate metadata is what makes Skills searchable and auditable at scale.

## 4. Write for Someone Who Has Never Done This Before

Write the Overview and Purpose sections assuming the reader is a competent engineer who has never touched this specific task. Spell out tool names, exact commands, and any jargon specific to your team.

## 5. Be Explicit About Scope

The When to Use and When NOT to Use sections are as important as the Workflow itself. A Skill that is unclear about its own boundaries gets misapplied. Name at least one alternative approach for the When NOT to Use case where possible.

## 6. Add a Real Example

Put a full, working example under `examples/`, using fake but realistic data. Reference it from the Examples section of `SKILL.md` rather than duplicating it inline.

## 7. Sanity-Check Before Opening a Pull Request

Re-read `SKILL.md` as if you were a new hire following it for the first time. Run through the Workflow yourself if at all possible, and confirm the Debugging section reflects failures you actually hit while testing it.
