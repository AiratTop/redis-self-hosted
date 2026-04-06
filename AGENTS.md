# AGENTS.md

## Purpose
Public self-hosted deployment template for standalone Redis cache/message broker.

## Repository Role
- Category: `*-self-hosted` (public GitHub repository).
- Related local stack: `../redis-docker`.
- Main entrypoint: `docker-compose.yml`.

## Stack Summary
- Service: `redis`.
- Exposed port: `6380` mapped to container `6379`.
- External network: `shared_network`.
- Auth enforced with `--requirepass`.

## Data and Config
- Persistent data: `./data/redis`.
- Runtime tuning set in compose `command` flags.

## Operations
- Restart stack: `./restart-docker.sh`.
- Update images and restart: `./update-docker.sh`.

## AI Working Notes
- Keep `REDIS_PWD` in `.env` only.
- Do not remove authentication flags from startup command.
- Preserve healthcheck based on `redis-cli` for orchestrator readiness.
