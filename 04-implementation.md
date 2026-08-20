# Step 4 — Implementation and validating (incl. SPR)

**Goal:** Code matches `ARCHITECTURE.md` and `NFR.md`. **Artifacts:** working repo, pytest, updated README.

**Tools:** Cursor Agent + Copilot · Claude for review only · Never paste `.env`.

Handbook: [jobs/coding.md](../ai-dev-handbook/jobs/coding.md) · [what-not-to-do.md](../ai-dev-handbook/what-not-to-do.md)

---

## Basic

```
Build my app.

[paste idea]
```

**Typical outcome:** Wrong stack, scope explosion, no tests.

---

## Intermediate

```
@ARCHITECTURE.md @main.py

Implement ONLY [one user story / one endpoint] from the API contract.
Python FastAPI. Match NFR: validate input, 422 on bad body, generic errors.
Show files you will change, then diff.
No new dependencies beyond [list].
```

---

## Advanced

```
@ARCHITECTURE.md @NFR.md @store.py @main.py

Implement ONLY: [specific Must story ID from PRD]

Constraints:
- Routes thin; storage in a class
- Type hints on public functions
- Secrets from env var names only — never hardcode
- Timeouts on outbound HTTP if any
- Persist data per ARCHITECTURE resiliency section

Also:
1. pytest tests: happy path + one failure (404 or 422) per endpoint touched
2. Update README setup to match actual commands

Show diff file-by-file. One feature only.
```

**Copilot (inline):**

```python
# POST /tasks - 201 + body; empty title -> 422; match ARCHITECTURE.md
```

---

## Validate (after Accept)

```
@ARCHITECTURE.md @tests/

Mental checklist vs NFR.md:
- Empty/invalid input
- Missing resource 404
- No stack trace in JSON error response
- Restart: does data survive per design?

List gaps only. Minimal fix suggestions. No new features.
```

**You run:** `pytest` · `uvicorn` · manual UI check.

---

## SPR implementation prompts

**Security**

```
@main.py @NFR.md
List auth and validation gaps for MVP. Fix Critical only. Minimal diff.
No new dependencies.
```

**Performance**

```
@ARCHITECTURE.md @main.py
Name the slowest path for 100 concurrent reads on laptop.
Suggest one MVP-safe improvement (e.g. index, pagination). No Redis unless NFR requires.
```

**Resiliency**

```
@store.py
On startup failure or corrupt DB file, fail with clear message — not silent empty data.
Minimal diff + one test.
```

---

## Next

[05-spr-testing.md](05-spr-testing.md)
