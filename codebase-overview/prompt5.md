Find all database schemas, ORM models, migrations, and type definitions that represent persisted data.

Produce TWO files:

1. `DATA_MODEL.mermaid` — an ER diagram (Mermaid erDiagram) showing:
   - All major entities/tables
   - Relationships (1:1, 1:N, M:N) with labels
   - Key fields only (id, foreign keys, and 2-3 domain-significant fields per entity)
   - Do NOT include every column — focus on what communicates the domain model

2. `DATA_ARCHITECTURE.md` explaining:
   - Which database engine(s) are used and where they're hosted
   - How migrations are managed (what tool, where migration files live)
   - Any caching layers (Redis, in-memory) and what they cache
   - Any file/blob storage (S3, Cloudflare R2) and what's stored there
   - Any search indexes (Elasticsearch, Algolia, pg_trgm) and what's indexed
   - If there's a vector DB, what embeddings are stored and how they're used
   - Read vs write patterns — is there any CQRS, read replicas, or event sourcing?