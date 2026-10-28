# 1. Fan-out audit across six microservices

**What it shows:** A Dynamic Workflow runs one child session per repo, checks for the deprecated `request` package and missing rate limits, ranks the findings with file:line evidence, and opens fix PRs only for confirmed ones.

**Starter repo:** [devin-demo-fanout-audit](https://github.com/thequantexplorer/devin-demo-fanout-audit)

**Needs:** GitHub only

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-fanout-audit/blob/main/DEVIN_DEMO.md).

## Prompt

```text
Audit all six Acme microservices for two risks, using a Dynamic Workflow: fan out one child session per repo, collect structured findings, then rank them.

Repos: https://github.com/<you>/acme-svc-payments https://github.com/<you>/acme-svc-orders https://github.com/<you>/acme-svc-users https://github.com/<you>/acme-svc-notifications https://github.com/<you>/acme-svc-search https://github.com/<you>/acme-svc-inventory

Check each repo for:
1. Use of the deprecated `request` npm package (a real runtime dependency/import, not a comment).
2. Write endpoints (POST/PUT/PATCH/DELETE), especially auth and money-moving ones, that have no rate limiting.

Each child must cite file:line evidence and run the repo's tests. Return a ranked table (severity, repo, finding, evidence, confirmed yes/no). Open a fix PR (with tests passing) ONLY for confirmed findings; explicitly list repos you checked and found clean or false positives, and explain why.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- `request` is a real dependency in **payments** and **notifications**. **inventory** only mentions it in a comment, so it is the false positive.
- Missing rate limits: **payments** `POST /charges` and `POST /refunds`, **users** `POST /login` and `POST /password-reset`, **orders** `POST /orders/:id/cancel`.
- **search** is read-only and **inventory** is clean, so expect 4 fix PRs and 2 repos reported clean.
