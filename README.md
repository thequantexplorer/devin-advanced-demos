# Advanced Devin demos

These are fifteen Devin demos. Every demo has a starter repo you can fork or use as a template, and a page in `demos/` with the prompt to give Devin and notes on what it should find.

| # | Demo | Starter repo | Needs |
| --- | --- | --- | --- |
| 1 | [Fan-out audit across six microservices](demos/01-fanout-audit.md) | [devin-demo-fanout-audit](https://github.com/thequantexplorer/devin-demo-fanout-audit) | GitHub only |
| 2 | [Java 8 to Java 17 migration with proof](demos/02-java-migration.md) | [devin-demo-java-migration](https://github.com/thequantexplorer/devin-demo-java-migration) | GitHub only (Devin installs JDK 8 and 17 itself) |
| 3 | [Sentry incident to root cause to PR](demos/03-sentry-incident.md) | [devin-demo-sentry-incident](https://github.com/thequantexplorer/devin-demo-sentry-incident) | GitHub, a Sentry account, and the Sentry MCP connected in Devin |
| 4 | [Slack bug report to repro video, Linear ticket and fix PR](demos/04-slack-triage.md) | [devin-demo-slack-triage](https://github.com/thequantexplorer/devin-demo-slack-triage) | GitHub, Slack and Linear connected to your Devin org |
| 5 | [Devin Review catches real bugs in a PR](demos/05-pr-review.md) | [devin-demo-pr-review](https://github.com/thequantexplorer/devin-demo-pr-review) | GitHub only |
| 6 | ["Only on iPhone" bug reproduced with video](demos/06-safari-bug.md) | [devin-demo-safari-bug](https://github.com/thequantexplorer/devin-demo-safari-bug) | GitHub |
| 7 | [Onboarding a cold repo: blueprint plus memory](demos/07-cold-repo-onboarding.md) | [devin-demo-cold-repo-onboarding](https://github.com/thequantexplorer/devin-demo-cold-repo-onboarding) | GitHub; you approve blueprint + Knowledge |
| 8 | [Self-improving skill](demos/08-self-improving-skill.md) | [devin-demo-self-improving-skill](https://github.com/thequantexplorer/devin-demo-self-improving-skill) | GitHub only |
| 9 | [Architecture consultation on a large OSS repo (Cal.com)](demos/09-architecture-consult.md) | [calcom/cal.com](https://github.com/calcom/cal.com) (public) | Nothing (public repo) |
| 10 | [Voice kickoff on iOS, finish in Desktop or CLI](demos/10-voice-to-desktop.md) | [devin-demo-voice-to-desktop](https://github.com/thequantexplorer/devin-demo-voice-to-desktop) | GitHub, plus the Devin iOS app and Devin Desktop or the CLI |
| 11 | [Exploit-first security remediation](demos/11-security-exploits.md) | [devin-demo-security-exploits](https://github.com/thequantexplorer/devin-demo-security-exploits) | GitHub only |
| 12 | [Performance fix with p50/p95/p99 proof](demos/12-performance.md) | [devin-demo-performance](https://github.com/thequantexplorer/devin-demo-performance) | GitHub only |
| 13 | [Scheduled watchdog automation](demos/13-scheduled-watchdog.md) | [devin-demo-scheduled-watchdog](https://github.com/thequantexplorer/devin-demo-scheduled-watchdog) | GitHub and Slack connected to your Devin org |
| 14 | [Churn investigation with an interactive report](demos/14-churn-analysis.md) | [devin-demo-churn-analysis](https://github.com/thequantexplorer/devin-demo-churn-analysis) | GitHub only |
| 15 | [Spec to a recorded end-to-end feature](demos/15-spec-to-e2e.md) | [devin-demo-spec-to-e2e](https://github.com/thequantexplorer/devin-demo-spec-to-e2e) | GitHub only |

## How to run one

1. Open the demo's page in [`demos/`](demos/) and follow its starter repo's `DEVIN_DEMO.md`. Usually that means: use the template or fork into your account, give Devin GitHub access, and paste the prompt.
2. Replace `<you>` in the prompt with your GitHub user or org.
3. Watch for approval cards. Sessions pause for you to approve things like creating an automation, saving org Knowledge, or changing an environment blueprint.

## Tips

- Run a demo once before presenting it live, and keep that finished session open as a backup.
- Slack demos only react in channels where Devin has been added with `/invite @Devin`.
- The presenter notes contain the answers. Don't copy them into the starter repos.
