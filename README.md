# Hi, I'm Jason (ReadableCode)

I build automation and reusable tools for problems I find interesting. Everything on this account is a personal project. Most of it runs on my homelab: a handful of machines behind a reverse proxy, wired together with Docker, redeployed on push. Comments, forks, and PRs are welcome.

## Where to find me

- [site.tinkernet.me](https://site.tinkernet.me) - my portfolio, served live from the homelab. React frontend, FastAPI backend, and an in-browser terminal. The uptime you see is real.
- [readablecode.github.io](https://readablecode.github.io) - the same site as a static build on GitHub Pages.

The bio also works from a terminal:

```bash
curl https://site.tinkernet.me/api/my-info
```

## Projects

### Data and analytics

- **[Data Tool Pack](https://github.com/ReadableCode/Data_Tool_Pack_Py)** - Uniform connectors for Snowflake, Databricks, S3, Vault, DuckDB, Google Workspace, and Looker, so analytics work doesn't start with a day of setup. Editions in [Python](https://github.com/ReadableCode/Data_Tool_Pack_Py), [Go](https://github.com/ReadableCode/Data_Tool_Pack_GO), and [Rust](https://github.com/ReadableCode/Data_Tool_Pack_RS).

- **[duck_db_api](https://github.com/ReadableCode/duck_db_api)** - A thin FastAPI service over DuckDB for ad-hoc table create/insert/query, with basic safety guards and file upload ingestion.

### Self-hosted infrastructure

- **[Self-hosted platform (Docker)](https://github.com/ReadableCode/Docker)** - The infrastructure everything else runs on: multi-host Docker Compose behind a SWAG reverse proxy with TLS and dynamic DNS, a private registry, self-hosted secrets, object storage, metrics, and notifications. Pushing to master rebuilds only the services whose repo changed.

- **[dotfiles](https://github.com/ReadableCode/dotfiles)** - Config sync and provisioning across Linux, Windows, macOS, Android, a router, and a NAS. Pulls configs over SSH/SCP from devices that can't symlink into a repo, provisions with Ansible, and includes a Go `git_puller` cross-compiled for four OS/arch targets.

- **[herdstone](https://github.com/ReadableCode/herdstone)** - A machine-herd monitor. One Python engine with three thin UIs (Typer CLI, Textual TUI, NiceGUI web) that import it in-process, no internal REST layer. It fans out concurrent pings across a host inventory, does OS-aware disk usage checks, pushes SSH keys, and puts `--json` on every command so shells can consume it as a subprocess. The inventory is a single JSON file, so adding a machine is a config edit, not code, and there's an Ansible-inventory importer to bootstrap it.

### Apps and services

- **[load-log](https://github.com/ReadableCode/load-log)** - A health tracker (habits + workouts) with a Textual TUI and a Streamlit web UI over shared storage. Neither UI touches Postgres directly: both go through PostgREST with JWT auth and row-level security, using a per-schema Postgres role. Alembic migrations and two Docker Compose profiles (portable vs. self-contained).

- **[postgrest-auth](https://github.com/ReadableCode/postgrest-auth)** - A small JWT auth service that sits next to PostgREST: `POST /token` checks a bcrypt hash and returns a JWT carrying the Postgres role and user id for RLS. Written once, used by my other apps.

- **[Cash Flow Commander](https://github.com/ReadableCode/Cash_Flow_Commander)** - A personal finance manager built for multiple frontends over pluggable storage backends. Postgres today; Sheets, SQLite, and Excel planned.

- **[Book-Bot](https://github.com/ReadableCode/Book-Bot)** - An offline eBook organizer. A local LLM (no internet or accounts required) works out author, series, order, and title from messy folders and rebuilds the library into clean nested folders. Can be pointed at hosted APIs instead, with SQLite or Postgres backends.

- **[Terminal To-Do](https://github.com/ReadableCode/Terminal_To_Do)** - A terminal Kanban board driven by Linux-like commands, with pluggable storage (self-hosted MinIO/S3 or Google Sheets).

### Web and games

- **[A Girl's Guide to Georgetown](https://github.com/ReadableCode/a_girls_guide_to_georgetown)** - A Go/Fiber backend that serves pages dynamically for a student-run site, so the students own the HTML/CSS/JS and can iterate without backend rebuilds. Deployed with Docker Compose behind SWAG.

- **[Trojan-Force](https://github.com/ReadableCode/Trojan-Force)** - A browser tower-defense game (TypeScript, Phaser 3, Vite): mine resources, build supply chains, survive 20 waves. Custom pathfinding, resource manager, and event bus, plus LAN multi-device play.

- **A 2D game in Unity / C#** - building this one with my wife. Not open source yet.

The portfolio site itself is a project too: React 19 + FastAPI, self-hosted on the same stack.

## Skills

| Area | Tools |
|------|-------|
| **Languages** | Python (uv), TypeScript, Go, Rust, SQL, Bash / PowerShell / AutoHotkey, C# |
| **Web / API** | FastAPI, React 19 + Vite, Streamlit, NiceGUI, Phaser 3 |
| **TUI / CLI** | Textual, Typer, custom terminal apps |
| **Data** | pandas, DuckDB, warehouse connectors (Snowflake / Databricks / Looker), OCR / PDF |
| **Databases / storage** | PostgreSQL + PostgREST, Alembic + RLS, SQLite, MinIO / S3, Vault |
| **Auth / security** | JWT (HS256), bcrypt, Postgres Row-Level Security |
| **Infra / DevOps** | Docker & multi-host Compose, SWAG reverse proxy + TLS + dynamic DNS, private registry, Ansible, k3s, Tailscale, uv, push-to-master auto-deploy |
| **AI** | Local-LLM inference with a swappable OpenAI backend |

## Contact

Open an issue or PR on any repo, or say hi from the terminal at [site.tinkernet.me](https://site.tinkernet.me).
