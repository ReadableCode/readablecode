# Hi, I'm Jason — "ReadableCode" 👋

Greetings! I'm a developer dedicated to **automation** and **modular, reusable solutions** to problems I find interesting. Everything here is a personal project — please comment, fork, and contribute as you see fit. I'm always looking for ways to improve my code and learn new things.

Most of what I build ends up running on a self-hosted homelab: a fleet of machines behind a reverse proxy, wired together with Docker, auto-deployed on push. The projects below are the things that live there.

---

## 🌐 Find me in two places

> ### 🖥️ [**site.tinkernet.me**](https://site.tinkernet.me) — my live self-hosted portfolio
> Dynamically served straight from my own homelab, complete with an **interactive in-browser terminal** and a **live FastAPI backend**. Not a static host — the uptime you see is real.
>
> ### 📄 [**readablecode.github.io**](https://readablecode.github.io) — GitHub Pages
> The same portfolio as a fast, static build.

**Fun fact:** you can read my bio straight from your terminal —

```bash
curl https://site.tinkernet.me/api/my-info
```

That's my own self-hosted API answering, live.

---

## 🚀 Projects

### Data & analytics

- **[Data Tool Pack](https://github.com/ReadableCode/Data_Tool_Pack_Py) — Python · Go · Rust**
  A batteries-included data-engineering toolkit: uniform connectors for Snowflake, Databricks, S3, Vault, DuckDB, Google Workspace, and Looker, so analytics work can start without paying the setup tax. Three language editions:
  [Python](https://github.com/ReadableCode/Data_Tool_Pack_Py) · [Go](https://github.com/ReadableCode/Data_Tool_Pack_GO) · [Rust](https://github.com/ReadableCode/Data_Tool_Pack_RS)

- **[duck_db_api](https://github.com/ReadableCode/duck_db_api)**
  A thin FastAPI service over DuckDB for ad-hoc table create / insert / query, with basic safety guards and file-upload ingestion.

### Self-hosted infrastructure

- **[Self-hosted platform (Docker)](https://github.com/ReadableCode/Docker)**
  The infrastructure everything else runs on: multi-host Docker Compose behind a SWAG reverse proxy with automatic TLS and dynamic DNS, a private container registry, self-hosted secrets, object storage, metrics, and notifications — plus a push-to-master pipeline that rebuilds only the services whose repo changed.

- **[dotfiles](https://github.com/ReadableCode/dotfiles)**
  A cross-platform config-sync and provisioning system spanning Linux, Windows, macOS, Android, a router, and a NAS. Pulls configs over SSH/SCP from devices that can't symlink into a repo, provisions with Ansible, and ships a Go `git_puller` cross-compiled for four OS/arch targets.

- **[herdstone](https://github.com/ReadableCode/herdstone)**
  A cross-platform machine-herd monitor. One Python engine with three thin presentation layers — a Typer CLI, a Textual TUI, and a NiceGUI web app — that import it in-process, no internal REST layer. It fans out concurrent ICMP pings across a host inventory, does OS-aware disk-usage, pushes SSH keys, and puts `--json` on every command so native shells can consume it as a subprocess. The inventory is a single JSON file, so adding a machine is a config edit, not code (with an Ansible-inventory importer to bootstrap it).

### Apps & services

- **[load-log](https://github.com/ReadableCode/load-log)**
  A personal health tracker (habits + workouts) with a Textual TUI and a Streamlit web UI over a shared data plane. Neither UI touches Postgres directly — both authenticate to a JWT service and read/write through PostgREST, with a per-schema Postgres role plus Row-Level Security enforcing access. Alembic migrations and two Docker Compose profiles (portable vs. self-contained).

- **[postgrest-auth](https://github.com/ReadableCode/postgrest-auth)**
  A small, app-agnostic JWT auth microservice that sits beside PostgREST: `POST /token` verifies a bcrypt hash and returns a JWT carrying the Postgres role and user id for RLS. Add once, reuse across every app.

- **[Cash Flow Commander](https://github.com/ReadableCode/Cash_Flow_Commander)**
  A personal-finance manager designed for multiple front-ends over pluggable storage backends — Postgres today, with Sheets / SQLite / Excel planned.

- **[Book-Bot](https://github.com/ReadableCode/Book-Bot)**
  An offline-first, AI-powered eBook organizer. A local LLM (no internet or accounts required) infers author, series, order, and title from messy folders and restructures libraries into clean nested trees — with a clean swap path to hosted APIs, and SQLite or Postgres backends.

- **[Terminal To-Do](https://github.com/ReadableCode/Terminal_To_Do)**
  A terminal Kanban board driven by Linux-like commands, with pluggable cloud-backed storage (self-hosted MinIO/S3 or Google Sheets).

### Web & games

- **[A Girl's Guide to Georgetown](https://github.com/ReadableCode/a_girls_guide_to_georgetown)**
  A student-led dev platform: a Go/Fiber backend dynamically serves pages so students own the HTML/CSS/JS and iterate without backend rebuilds. Deployed with Docker Compose behind SWAG.

- **[Trojan-Force](https://github.com/ReadableCode/Trojan-Force)**
  A browser tower-defense game (TypeScript + Phaser 3 + Vite): mine resources, build supply chains, and survive 20 waves. Hand-rolled pathfinding, resource manager, and event bus, with LAN multi-device play.

- **A 2D game in Unity / C#** — building this one with my wonderful wife. Not open source yet, but it's teaching me a lot about game development.

> This portfolio site itself is a project too — React 19 + FastAPI, self-hosted on the same stack described above.

---

## 🛠️ Skills & Tech

| Area | Tools |
|------|-------|
| **Languages** | Python (uv-managed), TypeScript, Go, Rust, SQL, Bash / PowerShell / AutoHotkey, C# |
| **Web / API** | FastAPI, React 19 + Vite, Streamlit, NiceGUI, Phaser 3 |
| **TUI / CLI** | Textual, Typer, custom terminal apps |
| **Data** | pandas, DuckDB, warehouse connectors (Snowflake / Databricks / Looker), OCR / PDF |
| **Databases / storage** | PostgreSQL + PostgREST, Alembic + RLS, SQLite, MinIO / S3, Vault |
| **Auth / security** | JWT (HS256), bcrypt, Postgres Row-Level Security |
| **Infra / DevOps** | Docker & multi-host Compose, SWAG reverse proxy + TLS + dynamic DNS, private registry, Ansible, k3s, Tailscale, uv, self-hosted push-to-master auto-deploy |
| **AI** | Local-LLM inference with a swappable OpenAI backend |

---

## 🤝 Let's build something

I'm always happy to collaborate. Whether you'd like to contribute, have questions, or just want to compare notes on self-hosting and automation, don't hesitate to reach out — your insights and contributions are genuinely welcome.

⭐ Poke around the repos, and drop by [**site.tinkernet.me**](https://site.tinkernet.me) to say hi from the terminal.
