# Compose

Docker Compose stack for running the services locally using prebuilt container images.

## What’s inside

This stack runs three services:

- **backend**: `ghcr.io/ltbots/backend:latest`
- **frontend**: `ghcr.io/ltbots/frontend:latest`
- **caddy**: `caddy:2.11-alpine`

Caddy routing:

- `/api/*` → `backend:8080`
- `/webhook/*` → `backend:8080`
- `/tg/*` → Telegram API (`https://api.telegram.org`)
- everything else → `frontend:8080`

## Quick start

```sh
git clone https://github.com/ltbots/compose
cd compose
docker compose up -d
```
