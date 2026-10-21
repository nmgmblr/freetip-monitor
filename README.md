# FreeTip monitor

Public health-check runner for `https://freetip.me`.

This repository contains **no application code and no secrets**. It exists
because GitHub does not reliably fire scheduled workflows on new private
repositories. The workflow probes the health-only monitor proxy in
`nmgmblr/FreeTip` every 15 minutes and opens or closes a single issue here.

- Health endpoint: the monitor Worker proxies `/api/health?fresh=1` through a
  Cloudflare service binding, avoiding Bot Fight Mode challenges.
- Alerting: issue title `[Uptime] freetip.me health check failing`.
- The monitor URL is stored as the repository secret `UPTIME_HEALTH_URL` and is
  not published in this repository.
- Manual run: Actions → **Uptime and ops check** → **Run workflow**. The
  optional `health_url` input is for testing only.

Do not add application code, tokens, or customer data to this repository.
