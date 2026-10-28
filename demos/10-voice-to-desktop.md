# 10. Voice kickoff on your phone, finish on your laptop

**What it shows:** Start a feature by voice on your phone. Devin opens a draft PR, and you pick up the same session in the web app on your laptop.

**Starter repo:** [devin-demo-voice-to-desktop](https://github.com/thequantexplorer/devin-demo-voice-to-desktop)

**Needs:** GitHub and a phone

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-voice-to-desktop/blob/main/DEVIN_DEMO.md).

> On your phone, open Devin, start a voice call and say the prompt. When the draft PR is up, open the same session at app.devin.ai on your laptop to review, tweak and merge. Devin Desktop and the CLI can open it too, if you use them.

## Prompt

```text
Hey Devin — on https://github.com/<you>/devin-demo-voice-to-desktop, add a 90-day uptime bar to each component on the status page, like the ones on GitHub's status page: green/amber/red per day computed from incident history, with a hover tooltip. Get it working and push a draft PR; I'll pick it up from my laptop to review and tweak.

When the draft PR is up, stop and summarize where you left off and exactly what's left, so I can continue this session from my laptop with full context.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- `/api/history` only serves 30 days, so Devin has to extend or derive the 90-day series.
- Expect a draft PR plus a handoff summary to continue from.
