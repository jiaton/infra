# Infrastructure Repository

Simple GitOps for Docker Compose projects.

## Usage

Every project uses the same workflow. In your project repo, create `.github/workflows/deploy.yml`:

```yaml
name: Deploy
on:
  push:
    branches: [main]
  workflow_dispatch:

jobs:
  deploy:
    uses: your-username/infra/.github/workflows/docker-compose-deploy.yml@main
```

That's it. The workflow expects:
- `docker-compose.yml` in repo root
- Self-hosted runner registered to the project repo

## What it does

1. Checkout code
2. Run `docker compose up -d --build`

That's it.