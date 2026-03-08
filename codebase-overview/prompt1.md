Scan this entire monorepo and produce a structured overview. Do NOT read every file — use directory listings, package.json/pyproject.toml/Cargo.toml files, Dockerfiles, CI configs, and top-level READMEs only.

Output a single markdown file called `REPO_MAP.md` with:

1. **Monorepo layout** — a tree showing every top-level package/service/app with a 1-line description of what it does (inferred from its package.json description, README first paragraph, or main entry point)
2. **Package manager & build system** — what tools orchestrate the monorepo (turborepo, nx, lerna, pnpm workspaces, cargo workspaces, etc.) and how builds are triggered
3. **Inter-package dependency graph** — which internal packages depend on which other internal packages (just the edges, not external deps)
4. **Entry points** — for each service/app, what is the main entry file and what command starts it
5. **Shared packages** — list any packages that exist purely to be consumed by other packages (shared utils, UI libraries, config packages, types packages)

6. **Repo type classification** — based on what you find, classify this repo as one of: JS/TS-heavy, Python-heavy, polyglot, or other. Note the primary and secondary languages by line count or package count. This classification should inform your language and tooling references in all subsequent prompts — e.g., if this is a Python-heavy repo, focus on pyproject.toml/Poetry/pip patterns rather than package.json/npm patterns. If it's a microservices architecture (many independently deployable services), note that integrations and inter-service communication should get extra attention later.

Keep descriptions terse. No filler. This is a reference doc for an architect.