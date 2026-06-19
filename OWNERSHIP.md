# Intelligence Stack + Company Brain — ownership / access

_Generated from registry.json (2026-06-19T06:27:39+00:00). The handover contract: what Mally co-owns vs what stays Henry-only._

**Model:** Mally has **co-ownership / operational parity** on the **business legs** (`aerodeck` + `aeros`). The **LIFE legs** (`personal` host) stay Henry-only. There is **one Chief of Staff — `hermes-chief-of-staff`** — and Mally is a **profile** on it; the profile/passport is the estate boundary (never a separate agent).

| Layer | Service | Host:Port | Owner |
| --- | --- | --- | --- |
| PURPOSE | mtp.yaml policy | aerodeck:file | Mally co-owns |
| PURPOSE | agent-registry | aerodeck:file | Mally co-owns |
| GOVERN | aero-pep broker | aerodeck:8951 | Mally co-owns |
| GOVERN | aero-govern-feed | aerodeck:8652 | Mally co-owns |
| GOVERN | govern.db ledger | aerodeck:file | Mally co-owns |
| GOVERN | aero-pep broker (LIFE) | personal:8951 | Henry-only (LIFE) |
| SENSE | SENSE bridges | aerodeck:cron | Mally co-owns |
| SENSE | reservoir.db | aerodeck:file | Mally co-owns |
| INTERPRET | aero-interpret | aerodeck:cron | Mally co-owns |
| INTERPRET | interpret.db | aerodeck:file | Mally co-owns |
| DECIDE | DECIDE desk | aerodeck:8688 | Mally co-owns |
| DECIDE | decisions (govern.db) | aerodeck:file | Mally co-owns |
| ORCHESTRATE | aero-dispatch | aerodeck:cron | Mally co-owns |
| ORCHESTRATE | aero-lifecycle | aerodeck:cron | Mally co-owns |
| LEARN | aero-learn / graders | aerodeck:cron | Mally co-owns |
| COMPANY BRAIN | brain store (pgvector) | aeros:5441 | Mally co-owns |
| COMPANY BRAIN | recall API | aeros:8647 | Mally co-owns |
| COMPANY BRAIN | brain MCP | aeros:8459 | Mally co-owns |
| COMPANY BRAIN | capture producers | aeros:cron | Mally co-owns |
| COMPANY BRAIN | SessionStart inject | aerodeck:hook | Mally co-owns |
| VISIBILITY | connection-registry | aerodeck:8414 | Mally co-owns |
| VISIBILITY | estate-map repo (GitHub) | github:repo | Mally co-owns |
| VISIBILITY | plan.aerodeck.ai | aerodeck:web | Mally co-owns |
| VISIBILITY | kanban board | aerodeck:8649 | Mally co-owns |
| VISIBILITY | kanban read-only | aerodeck:8650 | Mally co-owns |
| VISIBILITY | life-kanban (LIFE) | personal:8651 | Henry-only (LIFE) |

## What Mally can do (business legs)
- **See it all:** estate-map repo (GitHub), plan.aerodeck.ai, the boards, `aero-who/what/where`.
- **Operate it:** full govern-spine operate grants on `hermes-chief-of-staff` (ship-code/fire-build, deploy/provision-config, system-of-record) + run-research + send-external.
- **Run the brain:** read recall; business capture producers.

## What stays Henry-only (LIFE legs, greyed in the diagram)
- The `personal`-host `aero-pep` broker + LIFE CoS send gating.
- `life-kanban` (:8651) and any LIFE brain twin.
- The `personal` seat / Henry's LIFE estate.
