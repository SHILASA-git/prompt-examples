# Step 2 — Requirements and planning (incl. SPR)

**Goal:** Testable scope before design. **Artifacts:** `PRD.md`, `NFR.md` (security, performance, resiliency)

**Tools:** Claude (primary) · Paste `RESEARCH.md` as context.

---

## What to save

**PRD.md:** user stories, MVP scope, acceptance criteria  
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
2. MVP feature list (must ship in 1 week)
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
- User stories (MoSCoW: Must / Should / Could)
- MVP vs v2 table
- Acceptance criteria per Must story (Given/When/Then)

## NFR.md — testable only
### Security
- Auth approach for MVP (or explicit TODO)
- Secrets handling (.env, no keys in Git)
- Input validation rules
- Data retention / delete

### Performance
- Target response time for main API (e.g. p95 under 500ms on laptop)
- Max payload size
- What we measure (not “fast enough”)

### Resiliency
- What happens on restart (persistence choice)
- Timeout values
- Error shape to client (no stack traces)
- Backup or export story for MVP

Also:
- Open questions (max 5)
- Red-team: five ways this MVP fails in a demo

No code. Tables where helpful.
```

**Handoff:** Use `PRD.md` + `NFR.md` in step 3.

---

## Critique prompt (second pass)

```
Red-team this PRD and NFR as a senior engineer.

[paste PRD.md + NFR.md]

List:
## Critical gaps (block demo)
## SPR gaps (untestable requirements)
## Scope creep to cut

Max 15 bullets. No rewrite — findings only.
```

---

## Next

[03-design-architecture.md](03-design-architecture.md)
