Map every external service, third-party API, and webhook this system interacts with.

Produce `INTEGRATIONS_MAP.mermaid` as a flowchart showing this system at the center with all external services around it, with arrows labeled by:
- Direction (inbound webhook, outbound API call, bidirectional)
- What data flows (e.g., "sends email via API", "receives payment webhook")
- Auth method (API key, OAuth, webhook secret)

Also produce `INTEGRATIONS.md` as a table:

| Service | Integration Type | Purpose | Auth Method | Which Package Uses It | Failure Impact |
|---|---|---|---|---|---|

"Failure Impact" = what breaks if this service goes down (critical path vs degraded experience vs background job fails silently).