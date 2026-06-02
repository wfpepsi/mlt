# AGENTS.md

Guidance for AI agents working in this repository.

## Project overview

**mlt** is described in `README.md` as “AI for easy work.” As of the initial commit, the repository contains only that README—no application source, package manifests, Docker config, or CI workflows. Treat future additions (e.g. `package.json`, `pyproject.toml`, `docker-compose.yml`) as the source of truth for how to develop and run the product.

## Cursor Cloud specific instructions

### Repository state

There are **no installable project dependencies** and **no services to start** until manifests and application code land. The VM update script is intentionally a no-op so startup stays reliable.

### Toolchain available on the VM

The cloud environment includes common tooling agents can use once the project defines how to run:

- **Node.js** (via nvm, v22.x) with `npm`, `pnpm`, and `yarn`
- **Python 3.12** with `pip`
- **git**

When the repo adds a package manager lockfile, follow it (`package-lock.json` → npm, `pnpm-lock.yaml` → pnpm, `yarn.lock` → yarn, etc.) and document run/lint/test commands in `README.md` or here.

### Lint, test, build, and run

| Task   | Status (stub repo) |
|--------|--------------------|
| Lint   | Not configured     |
| Test   | Not configured     |
| Build  | Not configured     |
| Dev server | Not configured |

After code is added, update this section with exact commands (e.g. `pnpm install`, `pnpm dev`, `pytest`).

### Services

| Service | Required? | Notes |
|---------|-----------|--------|
| —       | —         | None until architecture is defined |

### Gotchas

- Do not assume monorepo layout or Docker Compose exists—verify with `ls` / manifests before running install or dev commands.
- If `package.json` (or equivalent) appears on `main` but is missing locally, run `git pull` before blaming the update script.
