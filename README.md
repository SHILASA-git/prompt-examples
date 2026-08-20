# Prompt examples — full application lifecycle

Copy-paste prompts for **after the workshop**: validate an idea → requirements → design → build → **SPR** test loop → secure deploy.

**SPR** = **S**ecurity, **P**erformance, **R**esiliency (how safe, fast, and recoverable your app is — not just features).

**Workshop labs:** [`ai-workshop`](../ai-workshop/) · **Tool how-to:** [`ai-dev-handbook`](../ai-dev-handbook/) · **Safety:** [what-not-to-do.md](../ai-dev-handbook/what-not-to-do.md) · **Terms:** [GLOSSARY.md](GLOSSARY.md)

Same idea, three prompt levels on every page: **Basic → Intermediate → Advanced**. Change **context, format, depth, and constraints** — not just the model name.

---

## Use in order

| Step | File | You save |
|------|------|----------|
| 0 | [00-how-to-prompt.md](00-how-to-prompt.md) | Techniques + tools |
| 1 | [01-market-research.md](01-market-research.md) | `RESEARCH.md` |
| 2 | [02-requirements.md](02-requirements.md) | `PRD.md`, `NFR.md` (see [GLOSSARY.md](GLOSSARY.md)) |
| 3 | [03-design-architecture.md](03-design-architecture.md) | `ARCHITECTURE.md` |
| 4 | [04-implementation.md](04-implementation.md) | Code + tests |
| 5 | [05-spr-testing.md](05-spr-testing.md) | Findings + fixes (SPR = Security, Performance, Resiliency) |
| 6 | [06-secure-deployment.md](06-secure-deployment.md) | `DEPLOY.md` |

**Worked example** (same app, all six steps): [worked-example-campus-notes.md](worked-example-campus-notes.md)

---

## Key terms (full list: [GLOSSARY.md](GLOSSARY.md))

| Short | Full meaning |
|-------|----------------|
| **MVP** | **M**inimum **V**iable **P**roduct — smallest version you can demo |
| **PRD** | **P**roduct **R**equirements **D**ocument — what to build |
| **NFR** | **N**on-**F**unctional **R**equirements — speed, security, uptime (not feature list) |
| **SPR** | **S**ecurity, **P**erformance, **R**esiliency |
| **API** | **A**pplication **P**rogramming **I**nterface — HTTP endpoints your app exposes |

From step 2 onward, advanced prompts ask for **testable** SPR bullets — not vague “make it secure.”

---

## Rules

1. Never paste secrets — [what-not-to-do.md](../ai-dev-handbook/what-not-to-do.md)
2. One feature per implement prompt
3. AI drafts; you verify (run tests, talk to users, read docs)
4. Cloud deploy is **stretch** — laptop + GitHub is enough for students
