# Setup Guide

## 1. Create infra repository
Push the workflow to `.github/workflows/docker-compose-deploy.yml`

## 2. For each project
Create `.github/workflows/deploy.yml`:
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

## 3. Requirements per project
- `docker-compose.yml` in repo root
- Self-hosted runner registered to the repo
- Runner must have Docker access

## 4. That's it
Push to main branch → automatic deployment