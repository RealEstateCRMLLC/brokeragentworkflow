# brokeragentworkflow

A broker/agent daily workflow app for real estate teams: 3-month look-ahead planning, daily "One-Minute Manager" style goals, feedback (praise / re-directs), habits, gamification (XP, badges, leaderboards), and an AI coach. Built for Excel Legacy Realty Group as part of the RealEstateCRM project family.

## Status

**Active development.** Version 0.49.0 (per `VERSION.md`). Last commit 2026-11-12 (forward-merge of a Jules planner feature into main). Most recent work has been done by Google Jules with human review/merges by candlestixxx.

## What's in here

- **Backend** — FastAPI + SQLAlchemy + Celery/Redis. Routers for auth, admin, goals, planner, feedback, habits, social, analytics, AI coach, and webhooks (`routers/`). Models in `models.py`; background tasks in `tasks.py`.
- **Frontend** — Vite + Tailwind app in `frontend/` (Capacitor `android/` and `ios/` shells present for a mobile build).
- **Tests** — pytest suite covering app, auth, goals, social, badges, leaderboard, e2e, and more (`test_*.py`).
- **Deploy** — `Dockerfile` and `docker-compose.yml` included; see `DEPLOY.md`.

## What's working / what's not

- The core workflow features (goals, planner, feedback, habits, gamification) are implemented across backend and frontend, per the 2026-09-28 "complete broker agent workflow implementation" commit and the changelog.
- No production deployment is documented in this repo; there is no live URL, uptime, or user evidence in the repo itself. Treat as under development, not production-proven.
- The repo root carries leftover merge-conflict artifacts (`*_ours.md` / `*_theirs.md` copies of changelog, handoff, models, roadmap, todo, version). These are stale duplicates and should be cleaned up, not read as current docs.

## Relationship to RealEstateCRM

This is a satellite component of [RealEstateCRM](https://github.com/RealEstateCRMLLC/RealEstateCRM) — the broker/agent workflow surface (planning, goals, feedback) that complements the main CRM. It is a separate service, not a folder inside the main CRM repo.

## Running it

See `DEPLOY.md` and `.env.example` for configuration. Standard flow: install Python deps from `requirements.txt`, run the FastAPI app (`main.py`), start the Celery worker, and serve the frontend from `frontend/`.

## Links

- Main CRM: https://github.com/RealEstateCRMLLC/RealEstateCRM
- Org: https://github.com/RealEstateCRMLLC
