# 9. Architecture consultation on a large OSS repo (Cal.com)

**What it shows:** Devin answers an architecture question about a large codebase it hasn't seen (Cal.com), using Ask Devin and DeepWiki, with a cited diagram and a ranked risk list. No code is written.

**Starter repo:** [calcom/cal.com](https://github.com/calcom/cal.com) (public)

**Needs:** Nothing; it uses the public [calcom/cal.com](https://github.com/calcom/cal.com) repo. You can point it at your own codebase instead.

## Prompt

```text
Act as an architecture consultant on an unfamiliar large codebase: https://github.com/calcom/cal.com (use DeepWiki / Ask Devin and read the code; do not write code).

Question: we want to make Cal.com fully multi-tenant (hard isolation between organizations sharing one deployment). Where would this change break?

Deliver: (1) a Mermaid architecture diagram of the request → auth → data path, (2) a ranked risk list (data model, auth/session, caching, background jobs, webhooks, integrations/credentials, billing, search) where every claim cites file paths, (3) the smallest safe first milestone and how to test it. Clearly separate what you verified in code from what you infer.
```

## Presenter notes (spoilers)

What Devin should find, so you can narrate it. Keep this out of the starter repo so Devin finds it on its own.

- Check that every risk cites file paths, and that verified facts are kept separate from inferences.
