# 7. Onboarding a cold repo: blueprint plus memory

**What it shows:** The tests fail on a fresh clone and the README is nearly empty. Devin works out the services and env vars the repo needs, writes an environment blueprint and Knowledge notes, and shows a fresh session reaching green tests with one command.

**Starter repo:** [devin-demo-cold-repo-onboarding](https://github.com/thequantexplorer/devin-demo-cold-repo-onboarding)

**Needs:** GitHub. Devin will ask you to approve the environment (blueprint) and org Knowledge changes.

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-cold-repo-onboarding/blob/main/DEVIN_DEMO.md).

## Prompt

```text
Onboard yourself to https://github.com/<you>/devin-demo-cold-repo-onboarding like a new engineer on day one.

First, try to run the tests cold and show me exactly what fails. Then figure out what this repo really needs (Postgres, Redis, migrations, seed data, required env vars like DATABASE_URL / REDIS_URL / LEDGER_SIGNING_KEY) and make it reproducible: write a repo-level environment blueprint so future sessions boot with services running and deps installed, and add Knowledge/Memory notes for the non-obvious rules of this codebase (how postings must balance, how to run migrations, where config lives). Finish by proving a fresh setup goes from clone to green tests with one command, and list everything you saved so the next engineer (or Devin) starts productive in seconds.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- Needs pnpm (via corepack), Postgres and Redis from `docker-compose.yml` on ports 5433 and 6380, `DATABASE_URL`, `REDIS_URL` and `LEDGER_SIGNING_KEY`, and `pnpm db:migrate` before the tests.
- Gotcha: running services aren't saved in the machine image, so the usual end state is a bootstrap command that starts them on demand.
- Sessions pause on approval cards for blueprint and Knowledge changes, so watch for them.
