# 3. Production error to root cause to PR

**What it shows:** Checkout is returning 500 errors. Devin reproduces them by replaying production traffic locally, finds the cause in the logs, and opens a fix PR with a regression test. With Sentry connected, it starts from the live Sentry issue instead.

**Starter repo:** [devin-demo-sentry-incident](https://github.com/thequantexplorer/devin-demo-sentry-incident)

**Needs:** GitHub. Sentry is optional.

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-sentry-incident/blob/main/DEVIN_DEMO.md).

## Prompt

```text
It's 3am and checkout is throwing 500s in production. You're on call.

Clone https://github.com/<you>/devin-demo-sentry-incident, start the server, and reproduce the failure with `npm run traffic` (it replays a slice of production checkout traffic against the local server). Use the server logs and stack trace to find the root cause, then ship a PR with the fix plus a regression test that fails before and passes after. In the PR, include the blast radius (which carts/codes are affected) and a short incident summary.
```

With Sentry connected, use this prompt instead:

```text
It's 3am and checkout is throwing 500s in production. You're on call.

Use the Sentry MCP (org <your-sentry-org>, project <your-sentry-project>) to pull the top unresolved issue, its stack trace, and event breadcrumbs/tags. Then clone https://github.com/<you>/devin-demo-sentry-incident, reproduce the failure locally (`npm run traffic` replays production carts against a local server), find the root cause, and ship a PR with the fix plus a regression test that fails before and passes after. In the PR, include the Sentry issue ID, blast radius (which carts/codes are affected), and a short incident summary. Do not resolve the Sentry issue until the PR is up; then comment on it with the PR link.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- Root cause: a fully redeemed gift card (`GC-3000`) has a `null` balance, so pricing reads `amountCents` off `null` and returns a 500. `npm run traffic` shows two 500s per round.
- Never commit the DSN. It only goes in your shell environment.
