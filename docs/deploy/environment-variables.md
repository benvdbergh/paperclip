---
title: Environment Variables
summary: Full environment variable reference
---

All environment variables that Paperclip uses for server configuration.

## Server Configuration

| Variable | Default | Description |
|----------|---------|-------------|
| `PORT` | `3100` | Server port |
| `HOST` | `127.0.0.1` | Server host binding |
| `DATABASE_URL` | (embedded) | PostgreSQL connection string |
| `PAPERCLIP_HOME` | `~/.paperclip` | Base directory for all Paperclip data |
| `PAPERCLIP_INSTANCE_ID` | `default` | Instance identifier (for multiple local instances) |
| `PAPERCLIP_DEPLOYMENT_MODE` | `local_trusted` | Runtime mode override |
| `PAPERCLIP_ALLOWED_HOSTNAMES` | (none) | Comma-separated hostnames allowed in addition to the host derived from `PAPERCLIP_PUBLIC_URL` (Tailscale/LAN aliases). Passed through in Docker Compose; see `doc/DOCKER.md`. |

## Secrets

| Variable | Default | Description |
|----------|---------|-------------|
| `PAPERCLIP_AGENT_JWT_SECRET` | (none) | HS256 secret used to mint short-lived run JWTs passed to agents as `PAPERCLIP_API_KEY`. In Docker Compose, defaults to `BETTER_AUTH_SECRET` when unset. |
| `PAPERCLIP_SECRETS_MASTER_KEY` | (from file) | 32-byte encryption key (base64/hex/raw) |
| `PAPERCLIP_SECRETS_MASTER_KEY_FILE` | `~/.paperclip/.../secrets/master.key` | Path to key file |
| `PAPERCLIP_SECRETS_STRICT_MODE` | `false` | Require secret refs for sensitive env vars |

## Agent Runtime (Injected into agent processes)

These are set automatically by the server when invoking agents:

| Variable | Description |
|----------|-------------|
| `PAPERCLIP_AGENT_ID` | Agent's unique ID |
| `PAPERCLIP_COMPANY_ID` | Company ID |
| `PAPERCLIP_API_URL` | Paperclip API base URL |
| `PAPERCLIP_API_KEY` | Short-lived JWT for API auth |
| `PAPERCLIP_RUN_ID` | Current heartbeat run ID |
| `PAPERCLIP_TASK_ID` | Issue that triggered this wake |
| `PAPERCLIP_WAKE_REASON` | Wake trigger reason |
| `PAPERCLIP_WAKE_COMMENT_ID` | Comment that triggered this wake |
| `PAPERCLIP_APPROVAL_ID` | Resolved approval ID |
| `PAPERCLIP_APPROVAL_STATUS` | Approval decision |
| `PAPERCLIP_LINKED_ISSUE_IDS` | Comma-separated linked issue IDs |

## LLM Provider Keys (for adapters)

| Variable | Description |
|----------|-------------|
| `ANTHROPIC_API_KEY` | Anthropic API key (for Claude Local adapter) |
| `OPENAI_API_KEY` | OpenAI API key (for Codex Local adapter) |

## Docker Compose (full stack)

`docker/docker-compose.yml` injects the following for the `server` service. See `doc/DOCKER.md` for runnable examples.

| Variable | Default | Description |
|----------|---------|-------------|
| `GITHUB_TOKEN` | (none; **required**) | Token available inside the container for GitHub CLI (`gh`) and related tooling shipped in the Docker image. On the host you can set `GITHUB_TOKEN="$(gh auth token)"` when `gh` is authenticated, or export a PAT. |
