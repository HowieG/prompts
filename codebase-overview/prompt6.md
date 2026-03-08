Map the frontend application structure.

Produce TWO files:

1. `UI_ARCHITECTURE.mermaid` — a flowchart showing:
   - All routes/pages (inferred from file-based routing or router config)
   - Group them by feature area
   - Show which pages are authenticated vs public
   - Show major shared layouts and where they wrap

2. `UI_COMPONENT_MAP.md` containing:
   - **Page inventory** — every route with its component file path and a 1-line description
   - **Shared component library** — if there's a shared UI package or component directory, list the major components with a 1-liner each
   - **State management** — what state management approach is used (React Context, Zustand, Redux, server state via React Query/SWR, URL state, etc.) and where global state lives
   - **Data fetching patterns** — how do pages get their data? (SSR, SSG, client-side fetch, React Server Components, tRPC, REST, GraphQL)
   - **Form handling** — what library/pattern handles forms and validation
   - **Notable UI patterns** — optimistic updates, infinite scroll, real-time subscriptions, drag-and-drop, or other non-trivial UI behaviors present in the codebase