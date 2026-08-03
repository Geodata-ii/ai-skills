# Zendesk API Notes

Reference notes on the specific Zendesk API endpoints and behaviors this Skill depends on. This is not a substitute for the official [Zendesk API documentation](https://developer.zendesk.com/api-reference/); it captures the details that matter most for this export pipeline.

## Ticket Streaming

Tickets are streamed from `/api/v2/incremental/tickets/cursor.json`, the cursor-based incremental export endpoint, rather than the standard List Tickets endpoint. Cursor pagination avoids the offset-based List Tickets limitations on large accounts and is safe to resume mid-stream using the cursor value from the last successful page.

## User Caching

Users are pulled once per run via `/api/v2/incremental/users.json` into a local cache keyed by user ID, storing name, email, and role. Per-comment or per-ticket calls to `/users/{id}` are avoided entirely, which is the single biggest factor in keeping large exports fast.

## Comments and Audits

Each ticket's comments and audits are fetched with their own paginated calls, controlled by `PAGE_SIZE`. Comments carry the `public` flag used to distinguish customer-visible replies from internal notes; audits carry the event timeline (assignment, status, group, trigger, and automation changes) used to build the Timeline section of each processed ticket.

## Rate Limits

Zendesk returns HTTP 429 with a `Retry-After` header when a rate limit is hit. The client honors `Retry-After` and retries with exponential backoff on 429 and 5xx responses. Lowering `THREAD_COUNT` reduces how often this happens on accounts with lower rate limit tiers.

## Authentication

Requests use HTTP Basic authentication with `{email}/token` as the username and the API token as the password. The Skill appends the `/token` suffix automatically; do not include it in `ZENDESK_EMAIL`.
