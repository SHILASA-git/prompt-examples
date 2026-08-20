# Step 1 — Market research and idea validation

**Goal:** Decide if the problem is real **before** you build. **Artifact:** `RESEARCH.md` (your research notes file)

**Tools:** ChatGPT or Gemini (scan) → Claude (structure) · **Verify:** talk to 3–5 real users; don’t trust invented **TAM (Total Addressable Market)** numbers from AI.

**SPR (Security, Performance, Resiliency)** here means **product risk**: what data you must not collect, what breaks trust, what fails under load later.

Terms: [GLOSSARY.md](GLOSSARY.md)

---

## What to save in `RESEARCH.md`

- Problem (1 sentence)
- Users and rough count (campus honest, not fake billions)
- Alternatives today
- Why you vs them (1 paragraph)
- **Kill criteria** — signals to stop or pivot (“stop if …”)
- 5 interview questions
- SPR risks (privacy, abuse, downtime impact)

---

## Basic

```
Is my app idea good?

Idea: [one sentence]
```

**Typical outcome:** Generic encouragement. No competitors, no kill criteria.

---

## Intermediate

```
I'm a 4th-year CSE student in Mysuru.

Idea: [app in one sentence]
Users: [who]

1. Five clarifying questions I should answer
2. Three existing alternatives (apps or habits)
3. **MVP (Minimum Viable Product)** I could demo in one week vs non-goals
4. Three reasons this might fail on campus

No code. Bullet format.
```

**Typical outcome:** Usable questions; market numbers may still be invented.

---

## Advanced

```
Role: product analyst for a student MVP (Minimum Viable Product — not a VC / venture capital pitch).

Context:
- Idea: [one sentence]
- Users: [e.g. CSE batch ~120, later whole college]
- Constraints: Python/FastAPI later; no paid cloud for MVP; solo or pair
- depth: standard

Tasks:
1. Problem statement + who hurts today
2. Table: Alternative | How users solve it today | Gap
3. Honest scope: campus N users, not national TAM (Total Addressable Market) fiction
4. Five user interview questions (open-ended)
5. Kill criteria: three signals to abandon or pivot the idea
6. SPR (Security, Performance, Resiliency) as product risk:
   - Security: data we must NOT collect
   - Performance: what feels slow to users
   - Resiliency: what happens if server or Wi-Fi dies
7. Output as markdown sections matching RESEARCH.md (list headings only first, then fill)

Verify: list three things I must check with real people or official sources — not AI guesses.

No implementation code. No invented download statistics.
```

**Handoff:** Paste `RESEARCH.md` into step 2.

---

## Verify loop

| AI said | You must |
|---------|----------|
| “Huge market” | Count users you can actually reach |
| Competitor names | Open their site / Play Store |
| “Students need this” | Ask 3 classmates; note exact quotes |

---

## Next

[02-requirements.md](02-requirements.md)
