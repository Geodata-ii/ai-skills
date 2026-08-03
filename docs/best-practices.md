# Best Practices for Skill Authors

These practices go beyond the minimum requirements in [`CONTRIBUTING.md`](../CONTRIBUTING.md) and reflect lessons learned from Skills that have aged well versus those that quickly became unreliable.

## Write for Reuse, Not for a Single Incident

A Skill should generalize past the specific ticket or incident that inspired it. Remove references to internal ticket numbers, specific dates, or one-off circumstances, and describe the underlying, repeatable task instead.

## Keep Scope Narrow

A Skill that tries to cover too many related tasks becomes hard to follow and hard to review. Prefer several small, focused Skills that link to each other over one large Skill that tries to do everything.

## Prefer Idempotent, Reversible Steps

Where a Skill involves changing state, such as modifying infrastructure or data, favor steps that are safe to re-run and easy to undo. Call out clearly which steps are destructive or hard to reverse.

## Show, Don't Just Tell

A worked example under `examples/` is more valuable than another paragraph of prose. Include real (but fake) input and the exact expected output, not just a description of what should happen.

## Design for Skimming

Most readers will scan headings before reading in full. Keep section headings exactly as defined in the template so readers and tooling can rely on them, and put the most important warning or caveat in the first sentence of a section, not the last.

## Revisit Skills You Own

Skill authorship does not end at merge. When tools change, APIs are deprecated, or a Skill stops working as documented, update `last_updated`, bump the `version`, and note the change in [`CHANGELOG.md`](../CHANGELOG.md).
