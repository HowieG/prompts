Trace the full lifecycle of an API request through this system. Pick the most representative "happy path" (e.g., user performs a core action that touches auth, API, database, and any async processing).

Produce a Mermaid sequence diagram saved as `ARCHITECTURE_REQUEST_FLOW.mermaid` showing:

- Client (browser/mobile) → API gateway/edge (if any) → backend service(s) → database(s)
- Include auth checks, middleware, any caching layers, any queue/async steps
- Label each arrow with the protocol (HTTP, WebSocket, gRPC, etc.) and the general shape of the payload
- If there are background jobs or webhooks triggered, show those as async branches

Also produce a brief `REQUEST_FLOW_NOTES.md` explaining:
- What the chosen flow represents
- Where the auth boundary is
- Where the data validation happens
- Any notable middleware in the chain
- What would be different for other major flows (list 2-3 alternatives you didn't diagram)