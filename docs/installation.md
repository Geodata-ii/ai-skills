# Installation

Skills in this repository are documentation and optional scripts, not a package to be installed with a package manager. "Installing" a Skill means bringing its content into the context of the person or tool that will use it.

## Option 1: Clone the Repository

Clone the repository and browse `skills/` locally. This is the best option if you plan to contribute back or want the full history and all categories available offline.

```
git clone https://github.com/Geodata-ii/ai-skills.git
```

## Option 2: Copy a Single Skill

If you only need one Skill, download or copy its folder, `skills/<category>/<skill-name>/`, into wherever your tooling or assistant expects Skills to live. At minimum you need `SKILL.md`; include `references/`, `examples/`, `assets/`, and `scripts/` if the Skill has them and you plan to use those parts.

## Option 3: Reference Skills Directly from GitHub

For tools that can fetch a URL, you can point directly at the raw `SKILL.md` on the default branch instead of copying files locally. Keep in mind this always reflects the latest version, which may differ from what you tested against.

## Running Skill Scripts

If a Skill includes a `scripts/` folder, read the script and the Prerequisites section of `SKILL.md` before running it. Install any dependencies it lists, set the required environment variables using your own credentials, and never commit real credentials back into the repository. See [`SECURITY.md`](../SECURITY.md) for more on running scripts safely.

## Staying Up to Date

Check a Skill's `last_updated` and `version` fields before relying on it for anything important, and watch this repository or the specific Skill's history if you depend on it heavily.
