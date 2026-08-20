# Step 3 — Design and architecture (incl. SPR)

**Goal:** Components, API contract, SPR design **before** codegen. **Artifact:** `ARCHITECTURE.md`

**Tools:** Claude (design) → Cursor Chat: “Create ARCHITECTURE.md from this — no code yet”

Handbook template: [ARCHITECTURE.md](../ai-dev-handbook/templates/ARCHITECTURE.md)

---

## Basic

```
Design my app architecture.

[paste idea]
```

**Typical outcome:** Generic three-tier diagram, no API table, no SPR.

---

## Intermediate

```
Design MVP architecture for:

[paste PRD.md summary or full file]

Stack: Python 3.11, FastAPI, SQLite or in-memory (say which and why).

Output:
1. Mermaid diagram
2. Component table
3. REST API table (method, path, success, errors)
4. One trade-off paragraph

No code.
```

---

## Advanced

```
Role: software architect for a student MVP.

Context:
[paste PRD.md]
[paste NFR.md Security/Performance/Resiliency sections]

Constraints:
- Implement only Must stories from PRD
- depth: thorough
- No new components not in PRD

Output ARCHITECTURE.md sections:

1. Problem and users (2 sentences)
2. Mermaid: client → API → storage (+ optional cache note for v2)
3. Component table: name | responsibility | file hint
4. API contract table with 404/422 cases
5. Data flow (numbered steps)
6. Trade-offs (what we chose and why)
7. At 10x scale (bullets only — no cloud homework)
8. Security design: auth TODO, validation, secrets, threat notes (STRIDE-lite: spoofing, tampering, data exposure — 1 line each for MVP)
9. Performance design: caching strategy for MVP (even “none yet”), hot paths
10. Resiliency design: restart behavior, timeouts, retries, idempotency where needed
11. Drift guard: “Routes must match API table; NFR must map to tests in step 5”

No implementation code.
```

**Cursor handoff:**

```
@PRD.md @NFR.md
Create ARCHITECTURE.md from the spec above. Do not write implementation code.
```

---

## Design review (Claude)

```
Senior architect review.

ARCHITECTURE:
[paste ARCHITECTURE.md]

Check:
1. Drift from PRD Must stories
2. SPR: untestable claims
3. Over-engineering for 1-week MVP

Format: Critical / Medium / Nice-to-have. Max 20 lines.
```

---

## Next

[04-implementation.md](04-implementation.md)
