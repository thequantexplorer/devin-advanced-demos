# 4. Slack bug report to repro video, Linear ticket and fix PR

**What it shows:** Tag Devin on a customer bug report in Slack. It records a repro, files a Linear ticket with the video, opens a fix PR, and posts the links in the thread.

**Starter repo:** [devin-demo-slack-triage](https://github.com/thequantexplorer/devin-demo-slack-triage)

**Needs:** GitHub, Slack and Linear connected to your Devin org

Setup steps are in the starter's [DEVIN_DEMO.md](https://github.com/thequantexplorer/devin-demo-slack-triage/blob/main/DEVIN_DEMO.md).

> Post the prompt as a message in `#support` that tags `@Devin`. Don't paste it into the Devin web app.

## Prompt

```text
Customer report from Dana at Northwind: "On the Acme storefront, if I type a quantity into the cart box instead of using the + button, my cart total goes crazy — I typed 2 for the tent and it charged me for 21 tents!"

@Devin please: reproduce this on https://github.com/<you>/devin-demo-slack-triage, record a video of the repro, file a Linear ticket in team ETH with repro steps, expected vs actual, and the video, then open a fix PR with a regression test and post the ticket + PR links back in this thread.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- The typed quantity stays a string, so adding to the cart concatenates it (`"2"` plus 1 becomes `21`) instead of summing.
- The thread should end with a repro video, a Linear ticket link and a PR link.
