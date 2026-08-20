# Glossary — terms in this repo

Plain English first. Acronyms appear in prompts; use this page when you forget one.

---

## Product and planning

| Term | Meaning |
|------|---------|
| **MVP** | **M**inimum **V**iable **P**roduct — the **smallest** version you can demo (not the final app) |
| **PRD** | **P**roduct **R**equirements **D**ocument — features, user stories, scope |
| **NFR** | **N**on-**F**unctional **R**equirements — how the system behaves: security, speed, recovery (not “add login button”) |
| **User story** | “As a [user], I want [action], so that [benefit]” |
| **Acceptance criteria** | How you know a story is done — testable checks |
| **Non-goals** | What you will **not** build this week |
| **Kill criteria** | Signals to **stop or pivot** the idea (e.g. nobody will try it) |
| **MoSCoW** | **Must** / **Should** / **Could** / **Won't** — priority labels for features |
| **Given / When / Then** | Test format: **Given** setup, **When** user acts, **Then** expected result |
| **TAM** | **T**otal **A**ddressable **M**arket — “how big is the market?” (AI often invents fake numbers) |
| **VC** | **V**enture **C**apital — startup funding pitch (not needed for student MVPs) |
| **Pivot** | Change direction when kill criteria hit |

---

## Engineering and SPR

| Term | Meaning |
|------|---------|
| **SPR** | **S**ecurity, **P**erformance, **R**esiliency |
| **Security** | Secrets safe, validation, auth, privacy — who can access what |
| **Performance** | Speed and limits — response time, payload size |
| **Resiliency** | Recovery when things fail — restart, backup, clear errors, timeouts |
| **API** | **A**pplication **P**rogramming **I**nterface — how programs talk over HTTP (e.g. `GET /tasks`) |
| **REST API** | Common style: paths + methods (`GET`, `POST`) + status codes (`200`, `404`, `422`) |
| **Architecture** | Components, diagram, API table — design **before** heavy coding |
| **Codegen** | **Code generation** — AI writing code from a prompt |
| **Drift** | Code no longer matches your design document |
| **Closed loop** | Test → find issue → fix → test again |
| **Red-team** | Pretend you are an attacker; list what breaks |
| **p95** | **95th percentile** — 95% of requests faster than this (e.g. “p95 under 500 ms”) |
| **STRIDE** | Security threat types: **S**poofing, **T**ampering, **R**epudiation, **I**nformation disclosure, **D**enial of service, **E**levation of privilege |
| **AppSec** | **App**lication **Sec**urity — securing the code you write |
| **OWASP** | **O**pen **W**eb **A**pplication **S**ecurity **P**roject — common web risk lists (Top 10) |

---

## Tools and deploy (stretch)

| Term | Meaning |
|------|---------|
| **FastAPI** | Python library for building HTTP APIs (workshop stack) |
| **pytest** | Python test runner |
| **CI** | **C**ontinuous **I**ntegration — auto-run tests when you push to Git |
| **GitHub Actions** | GitHub’s CI — workflow YAML that runs tests on push |
| **DevSecOps** | Build with **security** in mind from the start (not security only at the end) |
| **Docker** | Packages app + dependencies in a container (optional later) |
| **Rollback** | Go back to a previous working version (e.g. git tag + old database file) |
| **Health check** | URL like `/health` that returns OK if the app is running |
| **Smoke test** | Quick check that main paths work after deploy |

---

## Prompting

| Term | Meaning |
|------|---------|
| **Basic / Intermediate / Advanced** | Same task, more context + constraints + output shape |
| **Depth knob** | `skim` \| `standard` \| `thorough` — how long the answer should be |
| **Context pack** | Files you paste or `@` in Cursor (`PRD.md`, `ARCHITECTURE.md`) |
| **Handoff** | Save output to a file; next step uses that file as input |

---

Back to [README.md](README.md)
