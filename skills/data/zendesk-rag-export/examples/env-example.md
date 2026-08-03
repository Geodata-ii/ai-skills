# Example Environment Configuration

This shows a fully filled-out `.env` file using clearly fake placeholder values. Replace every value with your own before running the Skill, and never commit a real `.env` file to any repository.

```
# Bare subdomain only -- no https:// or .zendesk.com
ZENDESK_SUBDOMAIN=example-support

# Bare email only -- no /token suffix, it is added automatically
ZENDESK_EMAIL=export-bot@example.com

# Generated under Admin Center > Apps and integrations > APIs > Zendesk API
ZENDESK_API_TOKEN=REPLACE_WITH_YOUR_OWN_TOKEN

# Comma-separated ticket statuses to process into RAG output
ALLOWED_STATUSES=solved,closed

# Concurrency and reliability tuning
THREAD_COUNT=8
REQUEST_TIMEOUT=30
MAX_RETRIES=5
PAGE_SIZE=100

# Progress reporting only, does not affect correctness
ESTIMATED_TOTAL_TICKETS=50000
PROGRESS_LOG_INTERVAL=250

# Storage locations, relative to the project root
OUTPUT_DIR=storage
LOG_DIR=logs
CHECKPOINT_DIR=checkpoints
```
