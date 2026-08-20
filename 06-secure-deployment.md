# Step 6 — Secure deployment (incl. SPR)

**Goal:** Ship demo safely on **laptop + GitHub** first. Cloud is **stretch** (optional later). **Artifact:** `DEPLOY.md` (how to run and release safely)

**Tools:** Claude (checklist) · Cursor (Dockerfile / **GitHub Actions** for **CI (Continuous Integration)** if you choose) · **Never** paste cloud keys into chat · [GLOSSARY.md](GLOSSARY.md)

Workshop default: no cloud account required. This step is **thinking + local prod-like** habits.

---

## Basic

```
How do I deploy my app?
```

**Typical outcome:** Generic Docker / **K8s (Kubernetes)** essay you cannot run.

---

## Intermediate

```
Write DEPLOY.md for a student FastAPI + static UI project.

Environment: single laptop demo + optional GitHub public repo.
Include: prerequisites, env vars by NAME only, run commands, health check URL, rollback (git tag).

No AWS. No secrets in file.
```

---

## Advanced — local / GitHub deploy

```
Role: **DevSecOps**-minded student (build with **security** from the start) preparing a demo and portfolio repo.

Context:
[paste ARCHITECTURE.md deploy-relevant sections]
[paste NFR Security + Resiliency bullets]

depth: thorough

Output DEPLOY.md sections:

1. Pre-deploy checklist (**SPR** — Security, Performance, Resiliency)
   ### Security
   - .gitignore verified; scan_repo.py clean
   - .env.example committed; .env not
   - Debug off for demo mode
   - HTTPS: local vs public (honest limits)

   ### Performance
   - Single-worker uvicorn OK for demo; when to add workers (name only)

   ### Resiliency
   - Backup sqlite/file store before demo
   - Health endpoint
   - Rollback: git tag + restore DB file

2. Runbook: install → migrate → run API → run UI → **smoke test** (quick curl check)

3. Secrets: where they live (env only); rotation if ever leaked

4. Monitoring for MVP: logs to watch; no Datadog required

5. Stretch (optional, separate section): cloud deploy risks if I get access later — checklist only, no keys

Do not paste real tokens. Use placeholders.
```

---

## Advanced — CI (stretch)

```
@DEPLOY.md @.github/workflows/ (if any)

Propose a minimal GitHub Actions workflow:
- on push: pytest only
- no secrets in YAML except GitHub-provided
- no deploy step unless I add secrets myself in GitHub UI

Show workflow file only. Explain what NOT to commit.
```

---

## Pre-demo 30-second checklist

- [ ] `scan_repo.py` clean
- [ ] `.env` not in Git
- [ ] `pytest` green
- [ ] README matches run commands
- [ ] Can explain one **SPR (Security, Performance, Resiliency)** trade-off without opening chat

---

## Done

Return to [README.md](README.md) or start a new idea at [01-market-research.md](01-market-research.md).

Portfolio line: *“I validated the idea, wrote SPR requirements, designed first, tested in a loop, and deployed with secrets hygiene.”*
