# Hee Status

Live uptime & status page for Hee (https://hee.la) — published to [status.hee.la](https://status.hee.la).

Powered by [Upptime](https://upptime.js.org). Every 5 minutes a GitHub Actions cron hits each tracked URL and commits the result to `history/`; a nightly job regenerates `status-page/` (static site) and deploys it to GitHub Pages.

## Tracked endpoints

| Site          | URL                        |
| ------------- | -------------------------- |
| Marketing     | https://hee.la             |
| Portal        | https://app.hee.la         |
| Control Plane | https://api.hee.la/healthz |
| Edge          | https://edge.hee.la        |

## Setup (one-time)

1. Push this repo to `github.com/shekhardtu/hee-status`.
2. Settings → Actions → General → Workflow permissions: **Read and write**.
3. Settings → Pages → Source: **GitHub Actions**.
4. Settings → Secrets and variables → Actions → New secret `GH_PAT` = a fine-grained PAT with `contents:write` + `pages:write` on this repo.
5. DNS: add `status.hee.la CNAME shekhardtu.github.io.` in Cloudflare.
6. Trigger the first run: Actions → "Uptime CI" → Run workflow.

After the first successful run, the dashboard appears at https://status.hee.la.
