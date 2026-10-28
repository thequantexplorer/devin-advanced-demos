# 13. Scheduled watchdog automation

**What it shows:** Devin working on a schedule with nobody prompting it. It creates a Devin Automation that checks tests, advisories, outdated packages and bug issues every weekday and reports to Slack, opening a PR or issue when something breaks.

**Starter repo:** [devin-demo-scheduled-watchdog](https://github.com/thequantexplorer/devin-demo-scheduled-watchdog)

**Needs:** GitHub and Slack connected to your Devin org

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-scheduled-watchdog/blob/main/DEVIN_DEMO.md).

## Prompt

```text
Set up a Devin Automation for https://github.com/<you>/devin-demo-scheduled-watchdog that acts as an always-on dependency & health watchdog:

- Schedule: every weekday at 9:00 America/Chicago.
- Each run: install, run the full test suite, run `npm audit --omit=dev` and `npm outdated`, and check the repo's open issues labeled "bug".
- If anything is newly failing or a high/critical advisory appears, open a fix PR (or a GitHub issue if it needs a human) and post a short summary to Slack #engineering; if everything is green, post a one-line "all clear".

Create the automation, then trigger one run now so we can see the first report, and tell me how to view/edit it.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- Devin asks you to approve "Create automation" and "Run automation".
- The first run usually posts "all clear" (with `express` one major version behind).
- To show the failure path, open an issue labeled `bug` (for example the typed-quantity cart bug from demo 4) and trigger another run.
