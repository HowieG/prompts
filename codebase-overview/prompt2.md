Scan all dependency manifests (package.json, requirements.txt, pyproject.toml, go.mod, Cargo.toml, Gemfile, etc.) across the entire monorepo.

Produce a markdown file called `TECH_STACK.md` with a table per category:

| Technology | Version | Where Used (which packages) | What We Use It For (be specific) |
|---|---|---|---|

Categories:
- **Frameworks** (Next.js, FastAPI, Express, etc.)
- **Languages & Runtimes** (Node version, Python version, etc.)
- **Databases & ORMs** (Prisma, Drizzle, SQLAlchemy, the actual DB engine)
- **Auth & Identity** (Clerk, NextAuth, Supabase Auth, etc.)
- **Cloud & Infrastructure** (AWS services, Cloudflare products — specify WHICH product, e.g. "Cloudflare Tunnels" not just "Cloudflare")
- **AI/ML** (model providers, SDKs, vector DBs, embedding models)
- **Messaging & Queues** (Redis, RabbitMQ, Kafka, etc.)
- **Observability** (Sentry, Datadog, OpenTelemetry, PostHog, etc.)
- **CI/CD & DevOps** (GitHub Actions, Docker, Terraform, etc.)
- **Testing** (Vitest, Jest, Pytest, Playwright, etc.)
- **UI & Styling** (Tailwind, shadcn, Radix, etc.)
- **Other Notable** (anything that doesn't fit above but an architect should know about)

IMPORTANT: For each technology, don't just say the name. Say what specific feature/product we use. Example: "Supabase — Realtime subscriptions + Row Level Security, NOT using Supabase Auth". Infer this from actual imports and usage in code, not just from it being in dependencies.

If a dependency appears in package.json but is never actually imported anywhere, flag it as "declared but unused (verify)".

SELF-VERIFICATION STEP: After building the initial table, go back and check every entry you flagged as "declared but unused (verify)". Actually search the codebase for imports, requires, or references to that package. If you find usage, update the entry with what it's used for. If you confirm it's truly unused, keep the flag. Do not leave any "verify" flags unresolved.