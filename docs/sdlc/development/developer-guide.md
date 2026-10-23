# Developer Guide

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start status -->
_Up to date._
<!-- sdlc:auto:end status -->

<!-- sdlc:auto:start source -->
Generated from commit `d663151` · model `claude-sonnet-5`
<!-- sdlc:auto:end source -->

<!-- sdlc:auto:start overview -->
Simple addition is a Quorq-generated SDLC scaffold containing two independent apps in one repo: a Vite + React 19 SPA (frontend/) whose screens were approved and currently render seeded sample data, and a FastAPI service (backend/) that has no approved architecture yet beyond a health check. The backend uses SQLAlchemy against SQLite by default (swappable via DATABASE_URL, e.g. to the Postgres container defined in docker-compose.yml), and every future route will follow the generated stub pattern already used for scaffolding. The frontend talks to the API through a shared fetch wrapper (src/lib/api.ts) but no screen is wired to it yet.
<!-- sdlc:auto:end overview -->

<!-- sdlc:auto:start prerequisites -->
- Node.js (for Vite 6 / React 19 / npm scripts)
- Python 3.12
- pip
- Docker and Docker Compose (optional, for the Postgres service in docker-compose.yml)
<!-- sdlc:auto:end prerequisites -->

<!-- sdlc:auto:start setup -->
1. git clone <repo> && cd <repo>
2. cd frontend && npm install
3. cd backend && pip install -r requirements.txt
4. (optional) docker compose up -d to start the Postgres database defined in docker-compose.yml, then set DATABASE_URL to point at it
5. (optional) set ALLOWED_ORIGINS, VITE_API_BASE_URL, VITE_API_SECRET_KEY as needed for your environment
<!-- sdlc:auto:end setup -->

<!-- sdlc:auto:start run -->
| Name | Command | Description |
|---|---|---|
| frontend dev | `cd frontend && npm run dev` | Starts the Vite dev server for the SPA |
| frontend build | `cd frontend && npm run build` | Bundles the app with Vite (does not typecheck) |
| frontend preview | `cd frontend && npm run preview` | Serves the production build locally |
| backend dev | `cd backend && uvicorn app.main:app --reload` | Runs the FastAPI service locally with auto-reload; creates SQLite tables on startup |
| db up | `docker compose up -d` | Starts the Postgres 16 container defined in docker-compose.yml |
<!-- sdlc:auto:end run -->

<!-- sdlc:auto:start structure -->
| Path | Purpose |
|---|---|
| `frontend/` | Vite + React 19 SPA; approved screens rendering seeded sample data |
| `frontend/src` | App source: main.tsx entrypoint, lib/ (api client, UI/icon vocabulary, navigation), index.css brand tokens |
| `frontend/e2e` | Playwright acceptance tests, run against a locally built app or a deployed URL via E2E_BASE_URL |
| `backend/` | FastAPI service; health check implemented, all other routes are generated stubs |
| `backend/app` | App package: main.py entrypoint, database.py (engine/session), models.py (SQLAlchemy models), schemas.py (Pydantic models), routers/ (per-component routers) |
| `backend/tests` | Pytest test suite (e.g. test_health.py) |
| `.quorq/` | Platform metadata (handoff.json) used by the Quorq SDLC platform |
<!-- sdlc:auto:end structure -->

<!-- sdlc:auto:start conventions -->
- Backend: one router per architecture component owning endpoints; every unimplemented route returns a typed StubResponse (schemas.py) rather than failing, so the service and its OpenAPI doc stay complete
- Backend models inherit app.database.Base; models.py is imported in main.py before Base.metadata.create_all so tables register
- Backend config via environment variables with safe local defaults: DATABASE_URL defaults to local SQLite, ALLOWED_ORIGINS defaults to the Vite dev origins
- Frontend screens live under src/screens/ (per README) and are built against the shared UI/icon vocabulary in src/lib/ui.tsx and src/lib/icons.tsx, with brand tokens in index.css
- Frontend API calls go through the single apiFetch wrapper in src/lib/api.ts, which injects the bearer token from VITE_API_SECRET_KEY
- Frontend component tests (Vitest) live beside the components they cover under src/, separate from Playwright specs in e2e/
- Linting/formatting: ESLint + Prettier on the frontend, Ruff (check and format) on the backend
<!-- sdlc:auto:end conventions -->

<!-- sdlc:auto:start testing -->
| Name | Command | Description |
|---|---|---|
| frontend unit tests | `cd frontend && npm test` | Runs Vitest component tests under src/ |
| frontend lint | `cd frontend && npm run lint` | ESLint over the whole frontend app |
| frontend typecheck | `cd frontend && npm run typecheck` | Runs tsc --noEmit (not run by build) |
| frontend format check | `cd frontend && npm run format:check` | Checks formatting with Prettier |
| frontend e2e | `cd frontend && npm run test:e2e` | Runs Playwright acceptance tests from e2e/; builds/serves the app locally unless E2E_BASE_URL is set |
| frontend e2e browser install | `cd frontend && npm run test:e2e:install` | Installs the Chromium browser Playwright needs |
| backend tests | `cd backend && pytest` | Runs the pytest suite (e.g. health check test) |
| backend lint | `cd backend && ruff check .` | Lints the backend with Ruff |
| backend format | `cd backend && ruff format .` | Formats the backend with Ruff |
<!-- sdlc:auto:end testing -->

<!-- sdlc:auto:start troubleshooting -->
| Problem | Solution |
|---|---|
| Frontend cannot reach the backend / CORS errors in the browser | Ensure the backend is running and set ALLOWED_ORIGINS on the backend (or rely on its default dev origins http://localhost:5173 / 127.0.0.1:5173) and VITE_API_BASE_URL on the frontend to match the backend's actual URL |
| `pytest` fails to import `app` when run from backend/ | Run pytest from the backend/ directory so pytest.ini's `pythonpath = .` applies, or run `cd backend && pytest` |
| `npm run build` succeeds but `tsc` fails later | Run `npm run typecheck` (tsc --noEmit) explicitly, since build does not typecheck |
| Playwright e2e tests fail with a missing browser | Run `npm run test:e2e:install` first to fetch Chromium |
| Backend has no data / tables for new features | Add SQLAlchemy models to backend/app/models.py (Base is already wired) and corresponding Pydantic schemas to schemas.py; tables are created automatically on startup via Base.metadata.create_all |
<!-- sdlc:auto:end troubleshooting -->
