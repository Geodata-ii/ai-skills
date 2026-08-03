---
name: zendesk-rag-export
description: "Use this skill whenever working with Zendesk export, synchronization, or AI knowledge generation. It validates the environment, installs dependencies, tests Zendesk connectivity, exports tickets using the Incremental Export API, maintains checkpoints and manifests, reconstructs customer-agent conversations, generates Markdown and JSONL datasets for RAG systems, and supports full exports, incremental synchronization, dataset rebuilding, and project health checks without unnecessary API calls."
---
 
# Zendesk → RAG Export Pipeline Skill
 
## Purpose
 
Build and maintain a production-ready Zendesk → RAG export pipeline for
large Zendesk instances (100K--500K+ tickets).
 
## Workflow
 
When the user invokes this skill with `Run` or `Run Zendesk Export`, do
not immediately start coding or exporting.
 
### Phase 1 -- Environment Validation
 
Validate: - Python - Virtual environment - requirements.txt - .env -
storage folders - checkpoints - logs - Internet - Zendesk
authentication - Incremental Ticket API - Incremental User API -
Comments API - Audits API
 
Automatically: - Install missing dependencies
(`pip install -r requirements.txt`) - Create missing folders - Create
checkpoint.json and processed_manifest.json - Run
`python test_connection.py` - Continue only if all checks pass.
 
### Interactive Menu
 
1.  Fetch New Tickets
2.  Update Ticket Status
3.  Build Conversations
4.  Generate Markdown
5.  Generate JSONL Dataset
6.  Full Export
7.  Project Status
8.  Rebuild Training Dataset
9.  Exit
### Fetch New Tickets
 
-   Read checkpoint and processed manifest
-   Continue from saved incremental cursor
-   Download only new tickets
-   Save raw ticket data
-   Report ticket count, range and duration
### Update Ticket Status
 
-   Read local tickets
-   Find tickets not in Solved/Closed
-   Query current status
-   If changed to Solved/Closed:
    -   Update raw ticket
    -   Download comments
    -   Download audits
    -   Build conversation
    -   Generate Markdown
    -   Update JSONL
### Build Conversations
 
Use only cached raw data (no API calls).
 
### Generate Markdown
 
Generate only for Solved and Closed tickets.
 
Template:
 
# Zendesk Ticket
 
## Customer
 
-   Name
-   Email
## Ticket
 
-   Ticket Number
-   Subject
-   Category
-   Status
## Conversation
 
Customer
 
Agent
 
Customer
 
Agent
 
## Resolution
 
## Timeline
 
### Generate JSONL
 
Convert Markdown into embedding-ready JSONL.
 
### Full Export
 
Users → Tickets → Comments → Audits → Conversations → Markdown → JSONL
 
### Project Status
 
Show: - Total tickets - Solved - Closed - Open - Pending - Hold -
Markdown count - Dataset count - Last sync - Cursor - Manifest
 
## Architecture
 
-   client
-   exporters
-   processors
-   pipeline
-   models
## Engineering Rules
 
-   Never use List Tickets API for bulk export.
-   Always use Incremental Ticket Export API.
-   Cache users locally.
-   Stream pages.
-   Persist raw API responses.
-   Checkpoint after every page.
-   Use processed manifest for idempotency.
-   Respect Retry-After.
-   Build speaker identity using requester_id and submitter_id before
    global role.
-   Rebuild processed outputs from raw cache whenever possible.
## Output
 
storage/raw storage/processed logs checkpoints
 
## Commands
 
python app.py full python app.py incremental python test_connection.py
 
## Goal
 
Produce a resumable, scalable Zendesk-to-RAG pipeline with minimal API
calls and high-quality Markdown and JSONL datasets.