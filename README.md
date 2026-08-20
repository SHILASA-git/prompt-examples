# Prompt examples — full application lifecycle

Copy-paste prompts for **after the workshop**: validate an idea → requirements → design → build → SPR test loop → secure deploy.

**Workshop labs:** [`ai-workshop`](../ai-workshop/) · **Tool how-to:** [`ai-dev-handbook`](../ai-dev-handbook/) · **Safety:** [what-not-to-do.md](../ai-dev-handbook/what-not-to-do.md)

Same idea, three prompt levels on every page: **Basic → Intermediate → Advanced**. Change **context, format, depth, and constraints** — not just the model name.

---

## Use in order

| Step | File | You save |
|------|------|----------|
| 0 | [00-how-to-prompt.md](00-how-to-prompt.md) | Techniques + tools |
| 1 | [01-market-research.md](01-market-research.md) | `RESEARCH.md` |
| 2 | [02-requirements.md](02-requirements.md) | `PRD.md`, `NFR.md` |
| 3 | [03-design-architecture.md](03-design-architecture.md) | `ARCHITECTURE.md` |
| 4 | [04-implementation.md](04-implementation.md) | Code + tests |
| 5 | [05-spr-testing.md](05-spr-testing.md) | Findings + fixes |
| 6 | [06-secure-deployment.md](06-secure-deployment.md) | `DEPLOY.md` |

**Worked example** (same app, all six steps): [worked-example-campus-notes.md](worked-example-campus-notes.md)

---

## SPR = Security, Performance, Resiliency

From step 2 onward, every advanced prompt asks for testable SPR bullets — not “make it secure.”

---

## Rules

1. Never paste secrets — [what-not-to-do.md](../ai-dev-handbook/what-not-to-do.md)
2. One feature per implement prompt
3. AI drafts; you verify (run tests, talk to users, read docs)
4. Cloud deploy is **stretch** — laptop + GitHub is enough for students
