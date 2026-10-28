# 14. Churn investigation with an interactive report

**What it shows:** Devin as a data analyst. It quantifies and segments a churn spike, tests competing hypotheses against release notes and support tickets, and delivers an interactive HTML report with the SQL behind every number.

**Starter repo:** [devin-demo-churn-analysis](https://github.com/thequantexplorer/devin-demo-churn-analysis)

**Needs:** GitHub only

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-churn-analysis/blob/main/DEVIN_DEMO.md).

## Prompt

```text
Our CFO noticed churn roughly tripled in September 2026 and needs to know why before the board meeting. The data is in https://github.com/<you>/devin-demo-churn-analysis (SQLite warehouse snapshot, see README).

Investigate like a senior analyst: quantify the spike, segment it (region, plan, channel, payment method, cancel reason), test competing hypotheses against the release notes and support tickets, and separate correlation from causation. Deliver an interactive HTML report (charts, filterable tables, the SQL behind every number) with an executive summary up top, a root-cause conclusion with confidence level, the size of the revenue impact, and 3 concrete recommendations. Commit the report and the queries to the repo in a PR.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- The cause is involuntary churn: EU card payments started failing after the 4.7.0 payment-processor/SCA migration (cancel reason `payment_failed`).
- The red herring is the Team plan price change in 4.8.0.
