Read ALL of the following files that exist in this project directory: REPO_MAP.md, TECH_STACK.md, ENV_CONFIG_MAP.md, REQUEST_FLOW_NOTES.md, DATA_ARCHITECTURE.md, UI_COMPONENT_MAP.md, DEPLOYMENT_GUIDE.md, INTEGRATIONS.md, ONBOARDING.md, ARCHITECTURE_DECISIONS.md.

Also read all .mermaid files: ARCHITECTURE_REQUEST_FLOW.mermaid, DATA_MODEL.mermaid, UI_ARCHITECTURE.mermaid, INFRA_ARCHITECTURE.mermaid, INTEGRATIONS_MAP.mermaid.

Synthesize everything into a single `ARCHITECTURE_OVERVIEW.md` that a senior architect could read in 10 minutes and fully understand this system. Structure it as:

1. **Executive Summary** (3-4 sentences — what this system is, who it serves, what it does)
2. **System at a Glance** — embed or reference the key Mermaid diagrams inline (use mermaid code blocks so they render)
3. **Tech Stack Summary** — the most important technologies and WHY they were chosen (not just a list — tell the story)
4. **Architecture Patterns** — the 3-5 most important architectural decisions and their implications
5. **Data Flow** — how data moves through the system end-to-end, from user action to persisted state
6. **Key Risks & Technical Debt** — anything you noticed that looks like it could cause problems at scale, or patterns that are inconsistent across the codebase
7. **Open Questions** — things you couldn't determine from the codebase alone that an architect would want to ask the team about

Do NOT just concatenate the other docs. This should be a narrative that tells the story of the architecture. Cross-reference the detailed docs for anyone who wants to go deeper on a specific area.