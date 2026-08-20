# Step 5 — SPR testing and closed loop

**Goal:** Find Critical issues → fix → re-test until demo-safe. **Artifacts:** `TESTING.md` or findings in `LEARNING.md`

**Tools:** Claude (findings) → Cursor (minimal patch) · Your scanner from Day 2 AppSec lab

**Loop:** test → findings → fix Critical only → re-run → update `ARCHITECTURE.md` if drift

---

## Basic

```
Test my app for bugs.
```

**Typical outcome:** Random list, no prioritization, no re-test plan.

---

## Intermediate

```
Senior engineer test review.

ARCHITECTURE:
[paste API table]

CODE:
[paste main.py, store.py]

List test cases we should have (name | input | expected status).
Mark top 3 for MVP. No code yet.
```

---

## Advanced — security

```
AppSec review for student FastAPI on localhost.

ARCHITECTURE + NFR Security:
[paste — redact any real secrets]

CODE:
[paste routes and auth-related code]

Format:
## Critical (demo blockers)
## Medium
## Nice-to-have
## Drift from ARCHITECTURE/NFR

Also: secrets in repo? verbose errors? open admin routes?

No cloud vendor list. Prioritize fixes for 30-minute timebox.
```

---

## Advanced — performance

```
Performance review for MVP.

NFR Performance:
[paste]

Describe:
1. Likely bottleneck at 100 users on one laptop
2. Three cheap measurements I should run (commands or pytest)
3. One fix if p95 exceeds NFR target

No load-test framework unless I already installed it.
```

---

## Advanced — resiliency

```
Resiliency review.

NFR Resiliency + ARCHITECTURE:
[paste]

Chaos-lite scenarios for manual test:
| Scenario | Steps | Expected | Likely bug |

Include: kill server mid-request, bad JSON body, disk full simulation (describe only), restart app.

Max 8 scenarios.
```

---

## Closed loop (Cursor after Claude)

```
@ARCHITECTURE.md @main.py @tests/

Apply ONLY this Critical fix from review:
[paste one item]

Add or update one test that would have caught it.
Minimal diff. Then list command to re-run tests.
```

**Repeat** until Critical is empty or timeboxed.

---

## Regression prompt

```
@tests/ @ARCHITECTURE.md

Before demo: do tests cover every Must API row?
List missing cases as pytest stubs only — implement top 2.
```

---

## Next

[06-secure-deployment.md](06-secure-deployment.md)
