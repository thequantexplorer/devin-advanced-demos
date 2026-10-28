# 5. Devin Review catches real bugs in a PR

**What it shows:** Devin Review on a PR that looks reasonable but has money-handling and security bugs. Review leaves ranked inline comments with suggested fixes.

**Starter repo:** [devin-demo-pr-review](https://github.com/thequantexplorer/devin-demo-pr-review)

**Needs:** GitHub only

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-pr-review/blob/main/DEVIN_DEMO.md).

## Prompt

```text
Run Devin Review on https://github.com/<you>/devin-demo-pr-review/pull/1 ("refunds and webhooks"). I want a security- and correctness-focused review: money handling, webhook authentication, timing attacks, and anything that could let someone refund more than they paid. Post the findings as review comments on the PR with suggested fixes, ranked by severity, and summarize the top issues here. Don't merge.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- Planted issues:
  - Refunds have no over-refund check.
  - The full card number (PAN) is logged.
  - The webhook signature is optional and is compared with a non-constant-time `===`.
  - Webhooks are mounted after `express.json()`, so the signature is checked against `JSON.stringify(body)` instead of the raw body.
- The README lists the PCI rules the PR breaks.
- Hands-on variant: let attendees open their own PR on this repo and run Review on it.
