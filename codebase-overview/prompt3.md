Scan all .env files, .env.example files, docker-compose files, and config files across the monorepo.

Produce `ENV_CONFIG_MAP.md` containing:

1. **Environment variables inventory** — every env var referenced in code (via process.env, os.environ, etc.), grouped by service. For each var, note:
   - Which service(s) use it
   - What it configures (inferred from variable name and usage context)
   - Whether it has a default/fallback or is required

2. **Config files** — list every config file (next.config.js, tsconfig.json, tailwind.config, eslint, prettier, docker-compose, nginx, etc.) with a 1-line note on anything non-standard or notable about it

3. **Secrets & external service connections** — list every external service the app connects to (inferred from env vars like API keys, database URLs, webhook URLs). Don't include actual values — just the service name and what the connection is for.

4. **Environment tiers** — if there are separate configs for dev/staging/prod, note what differs between them.