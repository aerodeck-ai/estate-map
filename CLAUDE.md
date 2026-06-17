# CLAUDE.md — estate-map

> Repo-level guidance for Claude Code / Codex seats working in this repo.
> Inherits the estate-wide rules in ~/CLAUDE.md (AGENTS.md): identity, safety lines, credential rules, "GitHub main is the single source of truth".

## What this is
Generated, human- and machine-readable render of the Aerodeck estate topology. The Aerodeck **connection-registry remains the source of truth**; this repo is a published export of it (public repo).

## Stack & layout
Generated-artefact repo (no code, no framework). Top-level:
- `MAP.md` — the human-readable "lobby" view of the estate topology.
- `registry.json` — the machine-readable export of the registry.
- `README.md` — points at the generator.

## Build / run / test
No build — generated-docs repo. Do not hand-edit `MAP.md` / `registry.json`; they are produced by the generator `/home/henry/work/infra/aerodeck-registry/aero-topology-export`. Update the registry, then re-run the generator to refresh this repo.

## Conventions
- Default branch: `main` — single source of truth; additive commits or PRs; never force-push main.
- This repo is a downstream **render** — the connection-registry is canonical. Changes belong in the registry + generator, not in hand edits here.
- Public repo: keep it free of any secret, internal-only host detail beyond what the registry export already exposes.
