# Zendesk RAG Export

Exports Zendesk tickets into structured JSON, Markdown, and JSONL output ready to power a retrieval-augmented generation (RAG) support chatbot. Supports resumable full exports and incremental syncs.

## Quick Start

```
cp .env.example .env   # then fill in your Zendesk credentials
pip install -r requirements.txt
python app.py full
```

See [`SKILL.md`](SKILL.md) for full documentation, including Prerequisites, the complete Workflow, Best Practices, Common Pitfalls, and Debugging.

## Contents

- [`SKILL.md`](SKILL.md) -- full Skill documentation.
- [`references/zendesk-api-notes.md`](references/zendesk-api-notes.md) -- notes on the Zendesk API endpoints this Skill uses.
- [`examples/env-example.md`](examples/env-example.md) -- annotated environment variable reference.
- [`examples/sample-ticket-output.md`](examples/sample-ticket-output.md) -- a worked example from input to output.
