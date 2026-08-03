# Security Policy

## Scope

This repository contains documentation, prompts, and automation scripts ("Skills"). While most content is plain Markdown, some Skills include scripts intended to run in engineers' own environments. This policy covers vulnerabilities in those scripts, in repository tooling, and in the documented Skills themselves.

## Reporting a Vulnerability

If you discover a security issue in a Skill's script, a documented workflow, or the repository's tooling:

1. Do not open a public issue describing the vulnerability in detail.
2. Use GitHub's private vulnerability reporting feature under the Security tab of this repository, if enabled, or contact the maintainers listed in [`.github/CODEOWNERS`](.github/CODEOWNERS) directly.
3. Include the affected Skill or file path, the potential impact, and steps to reproduce if applicable.
4. Allow maintainers a reasonable window to investigate and remediate before any public disclosure.

## Handling Secrets and Credentials

Skills and examples in this repository must never contain real credentials, API keys, tokens, customer data, or internal-only endpoints. Use clearly fake placeholder values (for example `YOUR_API_TOKEN`) in every example and script. If you discover a secret committed to this repository, report it immediately using the process above rather than opening a public issue.

## Running Skill Scripts Safely

Review any `scripts/` contents before executing them, run them with the minimum permissions required, and avoid running scripts from unmerged pull requests against production systems or with production credentials.

## Supported Content

Only Skills on the default branch (`main`) are considered current and supported. Skills marked as deprecated in their `SKILL.md` metadata (see [`docs/skill-style-guide.md`](docs/skill-style-guide.md)) may no longer receive security updates and should be used with additional caution.
