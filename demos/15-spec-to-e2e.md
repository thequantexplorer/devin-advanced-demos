# 15. Spec to a recorded end-to-end feature

**What it shows:** Turning a written spec into working, tested software. Devin implements the API and UI, writes a test for each acceptance criterion, records the real UI in a browser, and maps every criterion to a test or video timestamp in the PR.

**Starter repo:** [devin-demo-spec-to-e2e](https://github.com/thequantexplorer/devin-demo-spec-to-e2e)

**Needs:** GitHub only

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-spec-to-e2e/blob/main/DEVIN_DEMO.md).

## Prompt

```text
Implement the spec in docs/specs/wip-limits.md on https://github.com/<you>/devin-demo-spec-to-e2e end to end: per-column WIP limits enforced by the API (409 when full), editable limits in the UI, toast feedback, and persistence.

Write API tests for every acceptance criterion in the spec, then test the real UI in a browser and record it: show setting a limit, hitting it by dragging a card, the toast, and the 409 being enforced. Open a PR that maps each acceptance criterion to the test or recording timestamp that proves it.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- The spec in `docs/specs/wip-limits.md` is the source of truth. Check that the PR's criteria table covers every item in it.
