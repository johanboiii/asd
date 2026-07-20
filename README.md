# xai-cf-solver

GitHub Actions hosted Cloudflare Turnstile solver (`i.exe` + `wrapper.py` + cloudflared).

## Limits
- Public Actions jobs max **~6 hours**
- Workflow **auto-restarts every 5 hours** (`cron`) and **cancels** the previous run
- Each run gets a **new** `*.trycloudflare.com` URL → published to:
  - `current_solver.txt` (this repo)
  - Railway `TURNSTILE_SOLVER` (if secrets set)
  - Telegram (optional)

## Endpoint
```
https://raw.githubusercontent.com/hakcannrjid/xai-cf-solver/main/current_solver.txt
```
Use as `SOLVER_DISCOVERY_URL` on the bot.

## Run manually
Actions → **Solver2 (6h + auto URL publish)** → Run workflow

## Secrets
`RAILWAY_TOKEN`, `RAILWAY_PROJECT_ID`, `RAILWAY_ENV_ID`, `RAILWAY_SERVICE_ID`, optional `TELEGRAM_BOT_TOKEN`, `TELEGRAM_CHAT_ID`
