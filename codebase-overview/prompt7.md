Examine all deployment-related files: Dockerfiles, docker-compose, CI/CD configs (.github/workflows, Jenkinsfile, etc.), Terraform/Pulumi/CDK files, Vercel/Netlify configs, Procfile, fly.toml, railway.json, serverless.yml, etc.

Produce TWO files:

1. `INFRA_ARCHITECTURE.mermaid` — a deployment diagram (use Mermaid flowchart) showing:
   - Where each service runs (which cloud provider, which service — e.g., "Vercel Edge", "AWS ECS", "Railway", "Cloudflare Workers")
   - How services connect to each other in production
   - Where databases are hosted
   - CDN/edge layers
   - DNS and domain routing
   - Any VPC/network boundaries

2. `DEPLOYMENT_GUIDE.md` containing:
   - How to deploy each service (the actual commands or CI triggers)
   - Branch → environment mapping (main → prod, develop → staging, etc.)
   - What the CI pipeline does step by step
   - Any manual steps or gotchas in deployment
   - How secrets/env vars are managed in production (Vercel env vars, AWS Secrets Manager, etc.)
   - Rollback strategy (if apparent)