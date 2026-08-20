# Step 2 — Requirements and planning (incl. SPR)

**Goal:** Testable scope before design. **Artifacts:**

- **`PRD.md`** — **P**roduct **R**equirements **D**ocument (features, stories, scope)
- **`NFR.md`** — **N**on-**F**unctional **R**equirements (security, performance, resiliency — not the feature list)

**SPR (Security, Performance, Resiliency):** write these as **testable** bullets in `NFR.md`, not “make it fast.”

**Tools:** Claude (primary) · Paste `RESEARCH.md` as context. · [GLOSSARY.md](GLOSSARY.md)

---

## What to save

**PRD.md:** user stories, **MVP (Minimum Viable Product)** scope, acceptance criteria  
**NFR.md:** non-functional requirements as **testable** bullets

---

## Basic

```
Write requirements for my app.

[paste idea]
```

**Typical outcome:** Vague feature list, no acceptance tests, no SPR.

---

## Intermediate

```
Using this research:

[paste RESEARCH.md]

Output:
1. Five user stories (As a … I want … so that …)
2. MVP (Minimum Viable Product) feature list (must ship in 1 week)
3. Non-goals (explicit)
4. Ten acceptance tests in plain English

Stack: Python FastAPI, local demo. No code.
```

---

## Advanced

```
Role: technical product manager for a student team.

Context:
[paste RESEARCH.md]

Constraints:
- MVP: 1 week, 2 developers, laptop-only deploy
- depth: thorough
- Match RESEARCH kill criteria — do not expand scope

Deliverables:

## PRD.md
- User stories (**MoSCoW**: **Must** / **Should** / **Could** / **Won't** priorities)
- MVP vs v2 table
- Acceptance criteria per Must story (**Given / When / Then** test format)

## NFR.md — testable only
### Security
- Auth approach for MVP (or explicit TODO)
- Secrets handling (`.env` file, no keys in Git)
- Input validation rules
- Data retention / delete

### Performance
- Target response time for main API (e.g. **p95** — 95% of requests under 500 ms on laptop)
- Max payload size
- What we measure (not “fast enough”)

### Resiliency
- What happens on restart (persistence choice)
- Timeout values
- Error shape to client (no stack traces)
- Backup or export story for MVP

Also:
- Open questions (max 5)
- **Red-team:** pretend you are an attacker — five ways this MVP fails in a demo

No code. Tables where helpful.
```

**Handoff:** Use `PRD.md` + `NFR.md` in step 3.

---

## Critique prompt (second pass)

```
Red-team (attack mindset) this PRD and NFR as a senior engineer.

[paste PRD.md + NFR.md]

List:
## Critical gaps (block demo)
## SPR gaps (Security, Performance, Resiliency requirements that are not testable)
## Scope creep to cut

Max 15 bullets. No rewrite — findings only.
```

---

## Next

[03-design-architecture.md](03-design-architecture.md)
