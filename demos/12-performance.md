# 12. Performance fix with p50/p95/p99 proof

**What it shows:** Devin benchmarks a slow endpoint, profiles it, fixes the causes without changing the API, and reports p50, p95, p99 latency and RPS before and after.

**Starter repo:** [devin-demo-performance](https://github.com/thequantexplorer/devin-demo-performance)

**Needs:** GitHub only

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-performance/blob/main/DEVIN_DEMO.md).

## Prompt

```text
Customers say the dashboard in https://github.com/<you>/devin-demo-performance is painfully slow. Make it fast, with proof.

Seed the realistic dataset (`npm run seed`) and measure the baseline with the repo's benchmark (`npm run bench`, report p50/p95/p99). Profile to find where the time actually goes (show the evidence: query counts, timings, a flamegraph or --cpu-prof output). Fix the root causes without changing response shape (existing tests must pass, add one that guards against regression). Re-run the identical benchmark and open a PR with a before/after table of p50/p95/p99 and RPS plus what you changed and why.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- Root causes: an N+1 query per project, no index on `events(project_id, ts)`, and `JSON.parse` on every row.
- Baseline is roughly p50 1.9 s and p95 8.6 s. Expect a 70-190x speedup.
