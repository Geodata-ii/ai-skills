# Worked Example: One Ticket End to End

This walks through a single fake ticket from raw Zendesk data to the two processed outputs this Skill produces: a Markdown document and a JSONL line. All names, emails, and content below are fictional.

## Input: Raw Ticket Summary

- Ticket ID: `48213`
- Subject: "Export button greyed out on the Reports page"
- Status: `solved`
- Requester: Jamie Rivera (jamie.rivera@example.com)
- Assignee: Priya Nair (Support Agent)
- Comments: one public customer comment, one public agent reply, one internal note

## Output: Markdown Document

Written to `storage/processed/markdown/Ticket_48213.md`:

```
# Ticket 48213: Export button greyed out on the Reports page

## Customer
Jamie Rivera <jamie.rivera@example.com>

## Issue
The export button on the Reports page is greyed out for a user on the Starter plan.

## Conversation
[Customer] The export button is greyed out, can you help?
[Agent] Report exports are available on the Growth plan and above; I have shared an upgrade link.

## Resolution
Explained plan gating and shared the upgrade link. Customer confirmed no further action needed.

## Categories
billing, reporting
```

## Output: JSONL Dataset Line

Appended as one line to `storage/processed/datasets/tickets.jsonl`, with the full Markdown document embedded as the `text` field (shown here truncated and formatted for readability):

```
{"ticket_id": 48213, "text": "# Ticket 48213: Export button greyed out on the Reports page..."}
```

## Notes

The internal note from this example is intentionally excluded from both outputs, since only public, customer-visible comments are included in the reconstructed conversation. The full JSON export under `storage/processed/conversations/48213.json` retains the internal note separately, with its visibility clearly marked, for audit purposes.
