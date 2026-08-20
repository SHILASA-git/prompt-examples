# How to prompt — techniques and tools

Every step file uses the same **Basic → Intermediate → Advanced** ladder. This page explains *why* the output changes.

**Terms:** [GLOSSARY.md](GLOSSARY.md) · **Technique definitions:** [prompt-engineering-techniques.md](../ai-dev-handbook/prompt-engineering-techniques.md) · Workshop ladder: [prompting.md](../ai-dev-handbook/prompting.md) · Safety: [what-not-to-do.md](../ai-dev-handbook/what-not-to-do.md)

**Not building a product?** Job descriptions, learning concepts, exploring ideas: [ai-for-work-and-learning.md](../ai-dev-handbook/ai-for-work-and-learning.md)

---

## Anatomy (always include in Advanced)

| Part | Example |
|------|---------|
| **Role** | “You are a product analyst for a student **MVP (Minimum Viable Product)**” |
| **Context** | Users, stack, scale, files you paste |
| **Task** | One deliverable |
| **Constraints** | **SPR (Security, Performance, Resiliency)**, no secrets, no scope creep |
| **Output shape** | Markdown table / numbered sections |
| **Depth** | `skim` \| `standard` \| `thorough` |

---

## Techniques (when to use)

| Technique | What it does | Best in step | Learn more |
|-----------|--------------|--------------|------------|
| **Zero-shot** | Task with no examples | All (weak Basic prompts) | [techniques § Zero-shot](../ai-dev-handbook/prompt-engineering-techniques.md#zero-shot) |
| **Few-shot** | 1–3 examples then your task | 3, 4 | [techniques § Few-shot](../ai-dev-handbook/prompt-engineering-techniques.md#one-shot-and-few-shot) |
| **Role prompting** | “You are a …” | 1–3, 5 | [techniques § Role](../ai-dev-handbook/prompt-engineering-techniques.md#role-prompting) |
| **Quality ladder** | Weak → specific → full context | All | [prompting.md](../ai-dev-handbook/prompting.md) |
| **Structured output** | “Return only this table” | 1–3, 5 | [techniques § Structured](../ai-dev-handbook/prompt-engineering-techniques.md#structured-output) |
| **Chain-of-thought (CoT)** | Step-by-step reasoning | Debug, design | [techniques § CoT](../ai-dev-handbook/prompt-engineering-techniques.md#chain-of-thought-cot) |
| **Chain then format** | Think in bullets, table only | 1, 2, 5 | [techniques § Chain then format](../ai-dev-handbook/prompt-engineering-techniques.md#chain-then-format) |
| **Prompt chaining** | File → next file | All steps | [techniques § Chaining](../ai-dev-handbook/prompt-engineering-techniques.md#prompt-chaining) |
| **Critique / red-team** | Attack your plan | 2, 3, 5 | [techniques § Red-team](../ai-dev-handbook/prompt-engineering-techniques.md#critique--red-team) |
| **Closed loop** | Test → fix → re-test | 5 | [techniques § Closed loop](../ai-dev-handbook/prompt-engineering-techniques.md#closed-loop) |
| **Context pack** | Paste `PRD.md` + `@ARCHITECTURE.md` | 3–6 | [how-editors-work.md](../ai-dev-handbook/how-editors-work.md) |
| **Verify instruction** | “List sources I must open” | 1, 4 | [prompting.md](../ai-dev-handbook/prompting.md) |
| **Depth knob** | `skim` \| `standard` \| `thorough` | All | below |

---

## Depth knob (copy into any prompt)

```
depth: skim        → 1 screen, bullets only
depth: standard    → tables + 1 paragraph per section
depth: thorough    → SPR (Security, Performance, Resiliency) checklists, failure modes, citations to verify
```

---

## Tool map by lifecycle step

Industry uses many products; students use what the workshop taught.

| Step | First choice | Second | Avoid |
|------|--------------|--------|-------|
| **1 Research** | ChatGPT or Gemini | Claude (structure brief) | Trusting market size without talking to users |
| **2 Requirements** | Claude | — | One mega-prompt for build + deploy |
| **3 Design** | Claude | Cursor Chat (write `ARCHITECTURE.md`) | Copilot Tab for architecture |
| **4 Implement** | Cursor Agent + Copilot | Claude (snippet only) | “Build entire app” |
| **5 SPR test** | Claude (findings) | Cursor (minimal fix) | Pasting `.env` into review |
| **6 Deploy** | Claude (checklist) | Cursor (Dockerfile/CI if you choose) | Pasting cloud keys into chat |

**Model class (2024–26):** long reasoning / large context for steps 1–3 and 5; fast code + repo context for step 4. Exact model names change — pick the best available in each tool.

---

## Basic vs Advanced (same task)

**Basic:** “Is my campus notes app a good idea?”  
→ Generic hype, no **kill criteria** (when to stop or pivot).

**Advanced:** role + users + campus scale + competitor table + interview questions + **SPR (Security, Performance, Resiliency)** risks + `RESEARCH.md` schema + “list what I must verify in person.”  
→ Actionable brief you can defend in a demo.

---

## Handoff between steps

End each advanced prompt with:

```
Save output as [RESEARCH.md | PRD.md | ARCHITECTURE.md].
Next step will use this file as context — do not invent features not listed here.
```

---

## Next

[01-market-research.md](01-market-research.md)
