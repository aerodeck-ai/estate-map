# Aerodeck Estate Map

Generated: `2026-06-23T06:27:09+00:00`
Source: `/home/henry/work/infra/aerodeck-registry/aerodeck-registry.db`

This is the registry-rendered lobby map for services, databases, MCP surfaces, agents, repositories, watchdogs, and access doors. The connection-registry remains the data of record.

## Machines

- **aerodeck** - `100.74.200.84` - dev-factory
- **aeros** - `100.64.135.5` - business-prod-canonical
- **jack-mbp** - `no tailnet IP` - client-seat
- **jiddlers** - `no tailnet IP` - client-tenant
- **mac-mini** - `100.89.244.20` - voice-compute
- **macbook** - `100.120.234.21` - transcription-compute
- **personal** - `100.99.185.36` - life-canonical

## Floors

### FACTORY

- **@Miranda_hermes_cos_bot** - `unknown` - live - CLI/comms - host=aerodeck unit=gates-bot.service, hermes-dashboard-henry.service, hermes-dashboard-jack.service, hermes-dashboard-mally.service, hermes-gateway-mally-chief-of-staff.service,...
- **mac-mini-infrassd-archive** - `unknown:/Volumes/InfraSSD` - live - Local Service/infra - ssh mac-mini ls /Volumes/InfraSSD
- **@aerodeck_gates_bot** - `aerodeck` - live - CLI/comms - host=aerodeck unit=gates-bot.service, hermes-dashboard-henry.service, hermes-dashboard-jack.service, hermes-dashboard-mally.service, hermes-gateway-mally-chief-of-staff.service,...
- **@aerodeck_voice_bot** - `aerodeck` - live - CLI/comms - host=aerodeck unit=gates-bot.service, hermes-dashboard-henry.service, hermes-dashboard-jack.service, hermes-dashboard-mally.service, hermes-gateway-mally-chief-of-staff.service,...
- **aero-write-broker** - `aerodeck:/home/henry/bin/aero-write-broker` - live - CLI/governance - aero-write-broker --scope | disk-reclaim [--execute] | pool-key [--execute] (default dry-run; unknown ops default-deny)
- **Plan-Surface** - `aerodeck:8930` - live - Dashboard/business - https://plan.aerodeck.ai (behind Cloudflare Access) or http://127.0.0.1:8930 / http://100.74.200.84:8930 on aerodeck — read-only factory dashboard (board/epics, codex verdicts,...
- **aerlock-panel** - `aerodeck:8772` - live - Dashboard/factory-audit - curl http://127.0.0.1:8772/health; curl http://127.0.0.1:8772/api/status
- **antislop-canon** - `aerodeck:/home/henry/work/business/antislop/canon/antislop-canon.json` - live - Database/comms - humanize.py / antislop.py (Vale) / build_canon.py
- **kanban-board-connector** - `aerodeck` - live - Database/infra - sqlite /home/ubuntu/apps/kanban-mcp/board.db (aerodeck :8649 kanban-mcp); read-only snapshot, sudo
- **kanban-readonly** - `aerodeck:8650` - live - MCP/infra - http://127.0.0.1:3001/mcp/kanban-readonly via Hub-Aerodeck (backend aerodeck :8650; Docker bridge allowed, off-box tailnet rejected since 2026-06-17)
- **kanban-tools** - `aerodeck:8649` - live - MCP/infra - http://127.0.0.1:8649/mcp (loopback/docker only — tailnet REJECTED since 2026-06-12)
- **obsidian-shared** - `aerodeck:3000` - idle - MCP/infra - disabled on hub
- **Hub-Aerodeck** - `aerodeck:3001` - live - MCP-Hub/business - http://127.0.0.1:3001/mcp (aerodeck-local) AND http://100.74.200.84:3001/mcp (tailnet-exposed 2026-06-14 = personal-business-shadow upstream); container aerodeck-mcphub-shadow —...
- **nightly-sweep** - `aerodeck:8772` - live - Scheduled Job/factory-audit - curl http://127.0.0.1:8772/api/status and inspect lanes.*.last_run
- **humanize-service** - `aerodeck:8466` - idle - Script/comms - POST /humanize, /score; GET /health
- **hermes-gateway-miranda-berliand** - `aerodeck` - live - agent-gateway/hermes - systemd hermes-gateway-miranda-berliand.service on aerodeck; API health http://127.0.0.1:8642/health/detailed with miranda-api-server-key; Telegram @Miranda_hermes_cos_bot; read...
- **shadow-hub-bearer-jack-tibbs-readonly** - `aerodeck:3001` - live - auth-key/mcphub-shadow - Scoped READ-ONLY: kanban-readonly, vault-search, cube-jiddlers, fetch-context, connection-registry. NO kanban-tools. Neg-tested 401 out-of-scope. verified 2026-06-11
- **aerodeck-root** - `aerodeck` - idle - infra/storage - ssh aerodeck; df -h / (device /dev/sda1 -> /, 194G)
- **claude-usage-warden** - `aerodeck:8689` - live - infra/usage-monitoring - curl -sf http://127.0.0.1:8689/status
- **aero-board-ui** - `aerodeck:8660` - live - service - DISCOVERED 2026-06-21 06:17:43Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 NEEDS-VERIFY: was auto-discovered + last_ok never — confirm live or retire.] [...
- **aero-govern-feed** - `aerodeck:8652` - live - service/infra - curl http://127.0.0.1:8652/{health,act,decisions} (loopback-only, read-only over govern.db views)
- **aero-pep-service** - `aerodeck:8951` - live - service/infra - curl http://127.0.0.1:8951/status (loopback-only); CLI: aero-pep decide/selftest/status/check
- **aeros-flight-deck** - `aerodeck:3099` - live - service/web-app - http://100.74.200.84:3099 — 'Flight Deck · AerOS' Next.js app on aerodeck
- **aeros-os-jiddlers** - `aerodeck:3014` - live - service - DISCOVERED 2026-06-20 06:17:04Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from ca...
- **cliproxy** - `aerodeck:8317` - live - service/llm-routing - http://100.74.200.84:8317 — Claude OAuth pool proxy on aerodeck (migrated off the Mac 2026-06-08; aeros :8318 sibling noted)
- **deerflow** - `aerodeck:2026` - live - service/research - http://100.74.200.84:2026 (tailnet-only via nginx; localhost NOT bound). API under /api/*
- **design-discovery-shadow** - `aerodeck:8525` - live - service/business - design-discovery shadow server; /home/ubuntu/dev/design-discovery-shadow/server.py
- **factory-review-doorman** - `aerodeck:8941` - live - service/infra - factory-review doorman gate; /srv/factory-review/bin/doorman.py [2026-06-21 RE-NAMESPACED personal->business: live-verified running on the AERODECK box, not the personal/LIFE ho...
- **factory-review-render** - `aerodeck:8942` - live - service/infra - factory review render service; /home/henry/work/factory/review/bin/render.py [2026-06-21 RE-NAMESPACED personal->business: live-verified running on the AERODECK box, not the per...
- **front-proxy** - `aerodeck:3016` - live - service - DISCOVERED 2026-06-23 00:15:58Z by registry-reconcile (proc=node); needs enrichment
- **gates-bot** - `aerodeck:8688` - live - service/comms - HTTP gate API aerodeck 0.0.0.0:8688 (X-Gates-Key); CoS approval gates mirror to Telegram + RC #aerodeck-gates
- **jambonz-aerodeck-api-server-1** - `aerodeck:3201` - live - service - DISCOVERED 2026-06-21 06:17:43Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 NEEDS-VERIFY: was auto-discovered + last_ok never — confirm live or retir...
- **jambonz-aerodeck-drachtio-1** - `aerodeck:5062` - live - service - DISCOVERED 2026-06-21 06:17:43Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 NEEDS-VERIFY: was auto-discovered + last_ok never — confirm live or retir...
- **jambonz-aerodeck-feature-server-1** - `aerodeck:3600` - live - service - DISCOVERED 2026-06-21 15:39:02Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **jambonz-aerodeck-freeswitch-1** - `aerodeck:8021` - live - service - DISCOVERED 2026-06-21 15:39:02Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **ntfy** - `aerodeck:8080` - live - service/notifications - http://100.74.200.84:8080 — ntfy push-notification relay on aerodeck (docker ntfy, container :80)
- **open-notebook-ui** - `aerodeck:8502` - live - service/research - http://100.74.200.84:8502 — Open Notebook Streamlit UI on aerodeck (docker on-app)
- **sim-realtime** - `aerodeck:3034` - live - service/workflow - http://100.74.200.84:3034 — Sim Studio realtime service on aerodeck (docker sim-realtime-1, container :3002)
- **steel-browser** - `aerodeck:9222` - live - service - DISCOVERED 2026-06-21 15:39:02Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **trigger-minio-api** - `aerodeck:9050` - live - service/storage - http://100.74.200.84:9050 — trigger.dev MinIO S3 API on aerodeck (docker trigger-minio-1, container :9000)
- **trigger-minio-console** - `aerodeck:9052` - live - service/storage - http://100.74.200.84:9052 — trigger.dev MinIO console on aerodeck (docker trigger-minio-1, container :9001)
- **trigger-registry** - `aerodeck:5050` - live - service/workflow - http://100.74.200.84:5050 — trigger.dev docker image registry on aerodeck (docker trigger-registry-1, registry:2)
- **voice-stt-router** - `aerodeck:8917` - live - service/voice - POST http://100.74.200.84:8917 — routes to whisper backends per stt_backends.json
- **@aerodeck_miranda_bot** - `aeros` - live - CLI/comms - host=aeros unit=certbot.timer, hermes-mcp.service, hermes-memory-mcp.service, snap-certbot-5604.mount, snap.certbot.renew.timer [de-staled 2026-06-20 card kt_1781951066137_fe00a...
- **aeros-gold-canonical** - `aeros:/home/ubuntu/data/sqlite/shared/aeros.db` - live - Database/business - aeros — canonical AerOS GOLD store (~659MB). Built hourly by aeros-gold-derivation.timer (aeros-medallion/scripts/aeros-derivation.py) from silver/sources incl. sqlite-local/ber...
- **antislop-canon-pg-mirror** - `aeros:aerodeck.antislop_canon` - live - Database/comms - read-only SQL; refreshed by export_to_pg.py
- **Hub-AerOS** - `aeros:3000` - live - MCP-Hub/business - http://100.64.135.5:3000/mcp (or /mcp/<server>) — aeros hub, bearer auth (fleet secret mcphub-bearer)
- **aerodeck-db-business-core** - `aeros:/home/ubuntu/data/sqlite-local/aerodeck/aerodeck.db` - live - database/business-core - sqlite3 (host-side, ro)
- **history-freshness-check** - `aeros` - live - infra/claude-history-pipeline - ssh aeros bash /home/ubuntu/bin/history-freshness-check.sh
- **annaland** - `aeros:8085` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **brain-recall-api** - `aeros:8648` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **company-brain-recall-api** - `aeros:8647` - live - service/company-brain - GET http://127.0.0.1:8647/recall?q=
- **embed-proxy** - `aeros:11435` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **grafana** - `aeros:3030` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from ca...
- **jambonz-feature-server** - `aeros:3600` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=node /home/ubun); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from...
- **loki** - `aeros:3100` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from ca...
- **node-exporter** - `aeros:9100` - live - service - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **plan-redirect** - `aeros:3032` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=node /home/ubun); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from...
- **prometheus** - `aeros:9090` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from ca...
- **rocketchat** - `aeros:3200` - idle - service/comms - https://chat.aerodeck.ai — Rocket.Chat team chat (Mally agency), aeros nginx -> localhost:3200; Mongo rs0 :27017
- **rtpengine-2224** - `aeros:2224` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=rtpengine); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categ...
- **rtpengine-2225** - `aeros:2225` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=rtpengine); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categ...
- **serve** - `aeros:9864` - live - service - DISCOVERED 2026-06-19 21:00:48Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **socks5-secondary** - `aeros:9051` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **jiddlers-os** - `jiddlers:3019` - idle - MCP/client - jiddlers box; UP, serving jiddlers.aeros-app.ai; image template-v1.0.0 since 2026-06-11 (verified 2026-06-11); still PENDING federation into Hub-Jiddlers (B3)
- **history-pipeline-mini** - `mac-mini:/Users/hberliand/customs-house/history/history.db` - live - infra/claude-history-pipeline - ssh mac-mini ~/customs-house/history/history-pipeline-runner.sh (launchd) plus ssh aeros bash /home/ubuntu/bin/history-freshness-check.sh
- **mac-mini-infrassd** - `mac-mini` - idle - infra/storage - ssh mac-mini; df -h /Volumes/InfraSSD
- **mac-mini-infrassd-tm** - `mac-mini` - idle - infra/storage - ssh mac-mini; df -h /Volumes/InfraSSD-TM
- **mac-mini-staging** - `mac-mini:/Users/hberliand/customs-house/v2/master.db` - live - service/customs-house - ssh mac-mini:/Users/hberliand/staging/ — Customs House staging area on Henry's Mac Mini (Tailscale 100.89.244.20); push-out-only quarantine inbox -> classifier -> leak-audited r...
- **macbook-internal** - `macbook` - idle - infra/storage - ssh macbook; df -h / (/Users/aerodeck) -- only when awake/online
- **@BerlosCoS_bot** - `personal` - live - CLI/comms - host=personal unit=hermes-gateway-chief-of-staff.service, hermes-litellm-tunnel.service, telegram-voice-gateway.service
- **@henry_personal_hermes_bot** - `personal` - live - CLI/comms - host=personal unit=gates-bot.service, telegram-voice-gateway.service
- **gmail-send** - `personal:3000` - idle - MCP/comms - http://100.99.185.36:3000/mcp/gmail-send (PERSONAL hub — the only working route)
- **life-kanban** - `personal:8651` - live - MCP/personal - http://127.0.0.1:8651/mcp (personal host, loopback/tailnet-only) — JSON-RPC tools/call; HTTP /health, /board.json
- **ski-finances-site** - `personal:8975` - live - Tunnel/personal - http-static
- **hermes-gateway-cos-personal** - `personal:8642` - live - agent-gateway/hermes - hermes-cos gateway http://127.0.0.1:8642 on personal (localhost-bound; auth=API_SERVER_KEY env). probe 2026-06-15T22:25:00Z: root/healthz 404 (server up, no root route).
- **history-life-drain-personal** - `personal:life.whatsapp_embeddings domain=claude_history` - live - infra/claude-history-pipeline - ssh personal sudo -n -u ubuntu python3 ~/apps/life-brain-dev/drain-history-to-lifebrain.py --verify
- **immich** - `personal:2283` - live - service/photos - http://100.99.185.36:2283/api/server/ping — Immich v2.7.5 on personal (Docker Compose at /opt/immich)

### MODELS

- **tmux-bridge** - `aerodeck:8282` - live - MCP/infra - http://127.0.0.1:8282/mcp — aerodeck loopback-only, NOT on any hub
- **humanize-benchmark** - `aerodeck:/home/henry/work/business/antislop/humanize_log.db` - live - Script/comms - humanize.py score()/fix(); SELECT producer,avg(human_score),date(ts) FROM humanize_log
- **voice-brain-mally** - `aerodeck:8929` - live - agent/voice - Mally voice-brain instance (voice-brain-mally.service) [2026-06-21 RE-NAMESPACED personal->business: live-verified running on the AERODECK box, not the personal/LIFE host.]
- **aerodeck-local-kokoro** - `aerodeck:8922` - live - service/voice - http://100.74.200.84:8922 — PRIMARY TTS backend for voice-tts-router; always-up ON-box Kokoro bm_george (~2.7s/chunk RTF~2.9x), self-heal proven; POST /tts {text,voice}->wav, GE...
- **anna-ollama** - `aerodeck:11434` - idle - service - 2026-06-20: aerodeck-local ollama models removed per No-LLM-on-servers epic (kt_1781907478205_b7ba3c). anna-relay brain now served by Mac Mini via the existing aerodeck->mac :11...
- **bge-host-proxy** - `aerodeck:11436` - live - service/infra - bge embedding host-proxy — routes embeds to the Mac GPUs (no models on Oracle boxes); /home/henry/bin/bge-host-proxy.py [2026-06-21 RE-NAMESPACED personal->business: live-verifi...
- **cliproxyapi-8318** - `aerodeck:8318` - live - service - DISCOVERED 2026-06-21 15:39:02Z by registry-reconcile (proc=cliproxyapi); needs enrichment
- **gatus** - `aerodeck:8088` - live - service/observability - http://100.74.200.84:8088 — Gatus fleet status page on aerodeck (docker gatus, container :8080)
- **jack-voice-tts-router** - `aerodeck:8924` - live - service/voice - http://0.0.0.0:8924 — tts_router.py (~/work/infra/voice-routers); routes Jack hermes RC replies to a Jessie Buckley voice clone via Voicebox
- **langfuse** - `aerodeck:3003` - live - service/observability - http://100.74.200.84:3003 — Langfuse web UI/API on aerodeck (containers langfuse-web/-worker/-db/-redis/-clickhouse/-minio)
- **litellm-aerodeck-pg** - `aerodeck:5433` - live - service - DISCOVERED 2026-06-21 06:17:43Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 NEEDS-VERIFY: was auto-discovered + last_ok never — confirm live or retir...
- **mally-voice-tts-router** - `aerodeck:8923` - live - service - Mally voice-tts-router instance — same tts_router.py as Henry (:8918), config mally-tts-backends.json. Scarlett chatterbox clone primary + kokoro baseline. Registered 2026-06-18...
- **voice-bakeoff-judge** - `aerodeck:8921` - live - service/voice - http://100.74.200.84:8921
- **voice-brain** - `aerodeck:8919` - live - service/voice - 127.0.0.1:8919 — headless claude -p daemon (loopback-only); reaches tmux via tmux-bridge :8282
- **voice-call** - `aerodeck:8920` - live - service/voice - http://100.74.200.84:8920 — live-call front-end
- **voice-capacity** - `aerodeck:8932` - live - service/voice - voice-routers capacity service; /home/henry/work/infra/voice-routers/capacity [2026-06-21 RE-NAMESPACED personal->business: live-verified running on the AERODECK box, not the pe...
- **voice-tmux-vnc** - `aerodeck:5900` - live - service/voice - x11vnc for the voice tmux display :97 (voice-tmux.service); also the Camoufox+VNC re-seal bridge [2026-06-21 RE-NAMESPACED personal->business: live-verified running on the AEROD...
- **voice-tts-router** - `aerodeck:8918` - live - service/voice - http://100.74.200.84:8918 — PRIMARY aerodeck-local-kokoro :8922 (on-box bm_george, always-up) -> failover mally/henry-kokoro :8912 (SAME voice, inaudible switch) -> Higgs :8911...
- **voicebox** - `aerodeck:8912` - live - service/voice - voice-routers voicebox (henry-kokoro fallback TTS); /home/henry/work/infra/voice-routers/voicebox [2026-06-21 RE-NAMESPACED personal->business: live-verified running on the AERO...
- **whisper-8771** - `aerodeck:8771` - live - service/voice - http://100.74.200.84:8771 — local whisper STT backend
- **voice-bot-server** - `aeros:8471` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **voice-ingest-server** - `aeros:8470` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **litellm** - `aeros:4000` - live - service/llm-routing - http://100.64.135.5:4000 — fleet LLM router on aeros (socat front to localhost litellm; SpendLogs in litellm-db :5433)
- **meetily-customs-house-ingest** - `henry-mac-mini:~/customs-house/v2/master.db (Henry Mac Mini, hberliand@100.89.244.20)` - live - Script/comms - n/a (pipeline)

### AGENTS

- **@aerodeck_alerts_bot** - `unknown` - live - CLI/comms - host=aeros unit=certbot.timer, hermes-mcp.service, hermes-memory-mcp.service, snap-certbot-5604.mount, snap.certbot.renew.timer
- **repo:agent-cockpit** - `aerodeck` - live - Repo/infra
- **repo:vectos-hermes** - `aerodeck` - live - Repo/infra
- **rc-tunnel** - `aerodeck:13200` - live - Tunnel/comms - ssh -N -L 127.0.0.1:13200 -> aeros:3200 (RocketChat) — leg of the RC<->Hermes bridge
- **jack-tibbs** - `aerodeck:9117` - live - agent/business - hermes dashboard http://127.0.0.1:9117 on aerodeck (jack-tibbs profile, runs as ubuntu) — LOOPBACK-ONLY bind (not on tailnet 100.74.200.84; verified 2026-06-14 ss -tlnp). Reach...
- **jiddlers-agent** - `aerodeck` - live - agent/client - points at Hub-Jiddlers; per-agent bearer to be minted (C1)
- **mally-chief-of-staff** - `aerodeck` - live - agent/business - points at Hub-Aerodeck; per-agent bearer to be minted (C1)
- **aerodeck-dev-design** - `aerodeck:3010` - live - service/web-app - https://dev-design.aerodeck.ai (CF Access svc-token) / http://127.0.0.1:3010 — container aeros-os-dev-design, MALLY CI (GitHub Actions runner aerodeck-dev-design), image aeros-o...
- **beszel-agent** - `aerodeck:45876` - live - service/observability - tcp://*:45876 — beszel-agent system-metrics agent on aerodeck (dedicated `beszel` system user)
- **beszel-hub** - `aerodeck:8090` - live - service/observability - http://100.74.200.84:8090 — beszel monitoring hub on aerodeck (docker beszel); NB aeros :8090 is a different service (nginx fleet.berl.ai legacy vhost)
- **sim-studio** - `aerodeck:3033` - live - service/workflow - http://100.74.200.84:3033 — Sim Studio web UI on aerodeck (docker sim-simstudio-1, container :3000)
- **trigger-webapp** - `aerodeck:8030` - live - service/workflow - http://100.74.200.84:8030 — trigger.dev v4-beta webapp on aerodeck (docker trigger-webapp-1, container :3000)
- **@mally_aerodeck_cos_bot** - `aeros` - live - CLI/comms - host=aeros unit=certbot.timer, hermes-mcp.service, hermes-memory-mcp.service, snap-certbot-5604.mount, snap.certbot.renew.timer
- **aeros-bronze-snapshots** - `aeros:/mnt/data/sqlite/bronze` - live - Database/infra - ls /mnt/data/sqlite/bronze/<alias>.db (stable symlink -> newest timestamped snapshot)
- **hermes-mcp** - `aeros:8099` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **hermes-memory** - `aeros:3000` - live - MCP/infra - http://100.64.135.5:3000/mcp/hermes-memory
- **vault-search** - `aeros:3000` - live - MCP/research - /mcp/vault-search on ALL THREE hubs (Hub-AerOS :3000, Hub-Aerodeck :3001, Hub-Personal :3000); canonical backend aeros 100.64.135.5:8439 (local hub points straight at it); secon...
- **mac-mini-internal** - `mac-mini` - idle - infra/storage - ssh mac-mini; df -h / (/Users/hberliand)
- **memory-mcp** - `personal:8542` - live - MCP/infra - http://100.99.185.36:8542/mcp — streamable-HTTP MCP on PERSONAL (Tailscale-only bind); health probe: ssh personal '~/bin/memory-mcp-status'
- **telegram-mcp** - `personal:8533` - live - MCP/comms - mcphub-personal → telegram-mcp (Telethon) ; or ssh personal docker exec telegram-mcp
- **henry-chief-of-staff** - `personal` - idle - agent/personal - CROSS-REF: LIFE agent; managed in the Miranda registry (canonical-home rule)

### DATABASES

- **documenso-postgres** - `aerodeck:5447` - live - Database - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from ca...
- **jambonz-aerodeck-mysql-1** - `aerodeck:3306` - live - Database - DISCOVERED 2026-06-21 15:39:02Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **jambonz-aerodeck-redis-1** - `aerodeck:6380` - live - Database - DISCOVERED 2026-06-21 15:39:02Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **cube-jiddlers** - `aerodeck:8440` - live - MCP/client - currently on aerodeck reaching jiddlers Cube via tunnel; SCHEDULED to move to jiddlers box (B1)
- **granola** - `aerodeck:3000` - live - MCP/comms - http://127.0.0.1:3001/mcp/granola (aerodeck shadow hub, loopback-only; OAuth access+refresh tokens in shadow-hub servers.oauth blob, auto-refresh)
- **aeros-finance-cube** - `aerodeck:4202` - live - service/analytics - http://100.74.200.84:4202 — AerOS finance Cube.js on aerodeck (docker aeros-finance-cube, container :4000)
- **aeros-finance-pg** - `aerodeck:5446` - live - service/database - postgres://100.74.200.84:5446 — AerOS finance Postgres on aerodeck (docker aeros-finance-pg, pgvector pg16)
- **aeros-os-dev-data** - `aerodeck:3012` - idle - service/business - https://dev-data.aerodeck.ai (CF Access svc-token) / http://127.0.0.1:3012 — container aeros-os-dev-data (gha-deploy CI), image aeros-os:dev-data
- **cube-jiddlers-tunnel** - `aerodeck:14200` - live - service/tunnel - tcp://127.0.0.1:14200 — aerodeck ssh -L forward to jiddlers Cube 127.0.0.1:4200
- **documenso-aerodeck** - `aerodeck:3025` - live - service/e-sign - https://sign.aerodeck.ai — Documenso e-sign (Remix), Dockerized on aerodeck (containers documenso + documenso-postgres on documenso-net), app :3025 / pg :5447
- **open-notebook-api** - `aerodeck:5055` - live - service/research - http://100.74.200.84:5055 — Open Notebook API on aerodeck (docker on-app; surrealdb sidecar unpublished)
- **sim-db** - `aerodeck:5455` - live - service/database - postgres://100.74.200.84:5455 — Sim Studio Postgres on aerodeck (docker sim-db-1, pgvector pg17)
- **trigger-clickhouse-http** - `aerodeck:9123` - live - service/database - http://100.74.200.84:9123 — trigger.dev ClickHouse HTTP on aerodeck (docker trigger-clickhouse-1, container :8123)
- **trigger-clickhouse-native** - `aerodeck:9192` - live - service/database - tcp://100.74.200.84:9192 — trigger.dev ClickHouse native protocol on aerodeck (docker trigger-clickhouse-1, container :9000)
- **trigger-postgres** - `aerodeck:5444` - live - service/database - postgres://100.74.200.84:5444 — trigger.dev Postgres on aerodeck (docker trigger-postgres-1, pg14)
- **trigger-redis** - `aerodeck:6390` - live - service/database - redis://100.74.200.84:6390 — trigger.dev Redis on aerodeck (docker trigger-redis-1, container :6379)
- **github_research** - `aeros postgres: aerodeck.embeddings WHERE source_db='github_research' (no standalone base table)` - idle - Database/research - bge-m3 semantic search (aeros :8427) + Company Brain; cross-searchable with youtube_research (same embeddings store)
- **influxd-8086** - `aeros:8086` - live - Database - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=influxd); needs enrichment
- **mariadbd-3306** - `aeros:3306` - live - Database - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=mariadbd); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from catego...
- **postgres-5432** - `aeros:5432` - live - Database - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=postgres); needs enrichment
- **redis-6379** - `aeros:6379` - live - Database - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=redis-server); needs enrichment
- **redis-6380** - `aeros:6380` - live - Database - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=redis-server); needs enrichment
- **rocketchat-mongo** - `aeros:27017` - idle - Database - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=docker-proxy); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from ca...
- **youtube_research** - `aeros:/home/ubuntu/data/sqlite/research/youtube-research.db (host: aeros)` - live - Database/research - bge-m3 semantic search (aeros :8427 history-search.py over aerodeck.embeddings source_db=youtube_research) + youtube-search MCP (business hub) + vectos-data REST (:3003 /api/dat...
- **deep-research-search** - `aeros:8440` - live - MCP/research - /mcp/deep-research-search on Hub-Aerodeck :3001 (shadow); backend aeros 100.64.135.5:8440
- **ms-query** - `aeros:3000` - live - MCP/personal - http://100.64.135.5:3000/mcp/ms-query
- **aeros-data** - `aeros` - idle - infra/storage - ssh aeros; df -h /mnt/data (device /dev/sdb -> /mnt/data, 196G). ALWAYS df -h (all), never df /
- **aeros-root** - `aeros` - idle - infra/storage - ssh aeros; df -h / (device /dev/sda1 -> /, 193G)
- **aeros-os-prod** - `aeros` - live - service/business - https://os.aerodeck.ai behind CF Access; container aeros-os on aeros (:3018). THE single canonical AerOS production site as of 2026-06-22.
- **company-brain-store** - `aeros:5441` - live - service/company-brain - docker exec brain-pg-dev psql -d company_brain
- **cube** - `aeros:4200` - live - service - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **jiddlers-live** - `jiddlers:8646` - live - MCP/client - jiddlers box; member of Hub-Jiddlers; $smart-indexed verified 2026-06-17: canonical bronze is jiddlers:/home/ubuntu/data/sqlite/shared/jiddlers/live.db on jiddlers VM 100.117.36...
- **personal-whatsapp-mcp** - `personal:3001` - live - MCP/whatsapp - MCP (Streamable HTTP) at http://100.99.185.36:3001/mcp — this is an MCP server, NOT REST. Tools incl. send_message + read_messages; read_messages takes chat_jid (NOT jid). Host-...
- **sqlite-whatsapp-mcp** - `personal:8536` - live - MCP/whatsapp - MCP read replica on personal :8536 (hub server name sqlite-whatsapp on mcphub-personal). READ-ONLY view of the golden store.
- **whatsapp-golden-store** - `personal:/var/lib/docker/volumes/miranda_whatsapp-data/_data/store.db` - live - database/whatsapp - Do NOT open with sqlite3 on the host while the bridge runs — query in-container (docker exec personal-whatsapp-mcp node + better-sqlite3 readonly) or via the MCP servers. messag...

### MCP

- **eac-mail-hub** - `127.0.0.1:8456` - live - MCP - mcp
- **camoufox-mcp** - `aerodeck:8775` - live - MCP/infra - camoufox anti-detect browser MCP backend (federated into hubs); /home/henry/apps/camoufox-mcp [2026-06-21 RE-NAMESPACED personal->business: live-verified running on the AERODECK...
- **connection-registry** - `aerodeck:8414` - live - MCP/infra - aerodeck systemd (henry); bound 172.17.0.1 (not tailnet); member of Hub-Aerodeck | 2026-06-11: now also serves the SCHEDULED-JOB class via cron_jobs table (248 jobs backfilled f...
- **cred-locate-mcp** - `aerodeck:8776` - live - MCP/infra - cred-locate cross-host secret-locator MCP backend; /home/henry/apps/cred-locate-mcp [2026-06-21 RE-NAMESPACED personal->business: live-verified running on the AERODECK box, not...
- **deep-research** - `aerodeck:8436` - idle - MCP/research - aerodeck systemd (runs as henry); member of Hub-Aerodeck
- **fetch-context** - `aerodeck:8428` - live - MCP/infra - aerodeck systemd; member of Hub-Aerodeck
- **gws-aerodeck** - `aerodeck:8541` - live - MCP/gws-docs - mcphub-aerodeck :3001 -> host.docker.internal:8541/mcp (bound 172.17.0.1:8541, runs as ubuntu)
- **notebooklm-mcp** - `aerodeck:8438` - live - MCP/research - http://172.17.0.1:8438 — host MCP federated into mcphub-aerodeck (via mcp-server-link); systemd --user notebooklm-mcp.service --profile business
- **otter** - `aerodeck:3000` - live - MCP/comms - http://127.0.0.1:3001/mcp/otter (aerodeck shadow hub, loopback-only; OAuth tokens in shadow-hub servers.oauth blob)
- **perplexity** - `aerodeck:8437` - live - MCP/research - aerodeck systemd perplexity-mcp.service (runs as henry); member of Hub-Aerodeck. mcp-proxy shim BOUND TO docker bridge 172.17.0.1 ONLY (not tailscale0 — ufw opens all tailnet po...
- **rc_mcp** - `aerodeck:8442` - live - MCP - DISCOVERED 2026-06-23 00:15:58Z by registry-reconcile (proc=python3); needs enrichment
- **serpapi** - `aerodeck:3001` - live - MCP/shopping - mcphub-aerodeck → mcp.serpapi.com (direct, bypasses aeros hub proxy which adds session management)
- **Hub-Aerodeck-Life-Shadow** - `aerodeck:3002` - live - MCP-Hub/life - http://127.0.0.1:3002/mcp (container aerodeck-life-shadow) — proxies the personal LIFE hub; bearer aerodeck-life-seat. The aerodeck seat .mcp.json mcphub-personal points HERE (n...
- **emma** - `aerodeck` - live - personal-finance/account-aggregator - mcphub-personal -> /mcp/emma -> emma_snapshot/totals/transactions/feed
- **mcp-server-link** - `aerodeck:8782` - idle - service/infra - http://172.17.0.1:8782 — mcp-server-link: federation linker exposing host MCPs (e.g. notebooklm-mcp:8438) into the mcphub-aerodeck shadow hub
- **tmux-bridge-health** - `aerodeck:8283` - live - service/infra - 127.0.0.1:8283 — second port of tmux-bridge server.py (sibling to MCP :8282)
- **award-flights-v2** - `aeros:8160` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **brain-mcp** - `aeros:8460` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **business-meetings-mcp** - `aeros:8461` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **connection_quota_ingest** - `aeros:8425` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **errors_ingest** - `aeros:8654` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **gmail-sa-mcp** - `aeros:8465` - live - MCP - DISCOVERED 2026-06-19 19:55:38Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **history-search** - `aeros:8427` - live - MCP/research - GET http://100.64.135.5:8427/history-search?q=&k= — direct on aeros, NOT behind any hub; /health for liveness
- **playwright** - `aeros:3000` - live - MCP/infra - http://100.64.135.5:3000/mcp/playwright
- **plex-mcp** - `aeros:3000` - live - MCP/personal - http://100.64.135.5:3000/mcp/plex-mcp
- **proposal-approval-server** - `aeros:8656` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **proxy-server** - `aeros:8463` - idle - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=MainThread); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from cate...
- **python-8655** - `aeros:8655` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from category...
- **rc-send-mcp** - `aeros:8462` - live - MCP - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=python3); needs enrichment
- **swr-api** - `aeros:8670` - live - MCP - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...
- **uk-transport** - `aeros:3000` - live - MCP/travel - http://100.64.135.5:3000/mcp/uk-transport
- **company-brain-mcp** - `aeros:8459` - live - service/company-brain - MCP brain_recall via mcphub-aerodeck / aeros hub
- **oracle-mcp-infra-ms-query-1** - `aeros:8480` - live - service - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **plex-mcp-vm** - `aeros:8481` - live - service - DISCOVERED 2026-06-22 06:17:09Z by registry-reconcile (proc=docker-proxy); needs enrichment
- **Hub-Jiddlers** - `jiddlers:3001` - live - MCP-Hub/client - http://127.0.0.1:3001/mcp on the jiddlers box (container mcphub-jiddlers; loopback-only — reach via ssh jiddlers; bearer auth pending)
- **linkedin** - `mac-mini:8783` - live - MCP/comms - mcphub-aerodeck -> linkedin-* (17 tools). Path: hub container -> http://host.docker.internal:8782/mcp -> aerodeck SSH tunnel (systemd --user linkedin-mcp-tunnel: 172.17.0.1:8782...
- **airbnb** - `personal` - idle - MCP/travel - mcphub-personal → http://100.99.185.36:3000/mcp — personal-hub travel MCP tool; Tailscale-only, served through the single hub door (no dedicated port)
- **amadeus-flights** - `personal` - idle - MCP/travel - mcphub-personal → http://100.99.185.36:3000/mcp — personal-hub travel MCP tool; Tailscale-only, served through the single hub door (no dedicated port)
- **amadeus-hotel** - `personal` - idle - MCP/travel - mcphub-personal → http://100.99.185.36:3000/mcp — personal-hub travel MCP tool; Tailscale-only, served through the single hub door (no dedicated port)
- **award-flights** - `personal` - idle - MCP/travel - mcphub-personal → http://100.99.185.36:3000/mcp — personal-hub travel MCP tool; Tailscale-only, served through the single hub door (no dedicated port)
- **booking-hotels** - `personal` - idle - MCP/travel - mcphub-personal → http://100.99.185.36:3000/mcp — personal-hub travel MCP tool; Tailscale-only, served through the single hub door (no dedicated port)
- **duffel** - `personal` - idle - MCP/travel - mcphub-personal → http://100.99.185.36:3000/mcp — personal-hub travel MCP tool; Tailscale-only, served through the single hub door (no dedicated port)
- **fli-flights** - `personal` - idle - MCP/travel - mcphub-personal → http://100.99.185.36:3000/mcp — personal-hub travel MCP tool; Tailscale-only, served through the single hub door (no dedicated port)
- **gmail-aerodeck** - `personal:8543` - live - MCP/comms - direct http://100.99.185.36:8543/mcp; personal hub http://100.99.185.36:3000/mcp/gmail-aerodeck; aerodeck shadow root exposes personal-gmail-aerodeck-* tools
- **google-calendar** - `personal:3000` - idle - MCP/personal - http://100.99.185.36:3000/mcp/google-calendar (PERSONAL hub — the only working route)
- **google-drive** - `personal:3000` - idle - MCP/personal - http://100.99.185.36:3000/mcp/google-drive (PERSONAL hub — the only working route)
- **google-sheets** - `personal:3000` - idle - MCP/personal - http://100.99.185.36:3000/mcp/google-sheets (PERSONAL hub — the only working route)
- **ms365** - `personal:3000` - idle - MCP/personal - http://100.99.185.36:3000/mcp/ms365 (PERSONAL hub — the only working route)
- **Hub-Personal** - `personal:3000` - idle - MCP-Hub/personal - http://100.99.185.36:3000/mcp — personal (LIFE) hub, bearer auth, Tailscale-only
- **Hub-Personal-Business-Shadow** - `personal:3002` - live - MCP-Hub/business - http://127.0.0.1:3002/mcp on the personal host (container personal-business-shadow) — proxies aerodeck business :3001 (tailnet); bearer personal-business-seat. Personal-side sea...

### GITHUB

- **repo:aerodeck-design** - `aerodeck` - live - Repo/business
- **repo:aerodeck-site** - `aerodeck` - live - Repo/business
- **repo:aerodeck-template** - `aerodeck` - live - Repo/business
- **repo:brand-assets** - `aerodeck` - live - Repo/business
- **repo:deer-flow** - `aerodeck` - live - Repo/vendor
- **repo:design-deck** - `aerodeck` - live - Repo/business
- **repo:infra** - `aerodeck` - live - Repo/infra
- **repo:jiddlers** - `aerodeck` - live - Repo/business
- **repo:life-os** - `aerodeck` - live - Repo/life
- **repo:verify** - `aerodeck` - live - Repo/infra
- **pr-preview-proxy** - `aerodeck:8790` - live - Service - Host reverse proxy for per-PR product-app previews: *.dev.aerodeck.ai pr-<N> -> localhost:31000+(N%1000). systemd --user pr-preview-proxy.service. [2026-06-21 RE-NAMESPACED pers...

### WATCHDOGS

- **changedetection-competitor-watch** - `aerodeck:8914` - live - service/marketing - HTTP API http://127.0.0.1:8914/api/v1/ (x-api-key in container datastore changedetection.json — never logged)
- **healthchecks** - `aerodeck:8000` - live - service/observability - http://100.74.200.84:8000 — Healthchecks cron-monitoring on aerodeck (docker healthchecks)
- **history-freshness-watchdog** - `aeros` - live - infra/claude-history-pipeline - ssh aeros systemctl --user is-active history-freshness-watchdog.timer && ssh aeros bash /home/ubuntu/bin/history-freshness-check.sh
- **company-brain-capture-producer** - `aeros` - live - intelligence/company-brain - ssh aeros crontab -l | grep brain; scripts under /home/ubuntu/apps/company-brain-dev/brain-capture*.py|sh write to company_brain

### ACCESS

- **aero-codex-quota-cap** - `aerodeck` - live - CLI/infra - /home/henry/bin/aero-codex-quota-cap --status (CLI; loopback, no port)
- **aerodeck-waitlist** - `aerodeck:443` - live - service/web-app - https://127.0.0.1:443 — aerodeck loopback HTTPS; 'Aerodeck Waitlist' Next.js app
- **bgutil-pot-provider** - `aerodeck:4416` - live - service/youtube-infra - http://100.74.200.84:4416 — bgutil yt-dlp PO-token provider on aerodeck (docker bgutil-pot-provider)
- **start-guide** - `aerodeck:3013` - live - service/infra - Static server for the Start-Here onboarding guide; CF tunnel start.aerodeck.ai -> 127.0.0.1:3013 (registered 2026-06-18, card kt_1781764355865_bb1538).
- **warp-svc** - `aerodeck:40000` - live - service/networking - tcp://127.0.0.1:40000 — Cloudflare WARP daemon local API on aerodeck (HTTP probe answers 502 = alive)
- **oauth_router** - `aeros:9317` - live - service - DISCOVERED 2026-06-18 07:56:32Z by registry-reconcile (proc=python3); needs enrichment [2026-06-21 CURATED from auto-discovered: live (last_ok 2026-06-21); type set from categor...

## Databases

- **antislop-canon** - `aerodeck:/home/henry/work/business/antislop/canon/antislop-canon.json` - json - canonical
- **connection-registry** - `aerodeck:/home/henry/work/infra/aerodeck-registry/aerodeck-registry.db` - sqlite - canonical
- **humanize-benchmark** - `aerodeck:/home/henry/work/business/antislop/humanize_log.db` - sqlite - canonical
- **kanban-tools** - `aerodeck:/home/ubuntu/apps/kanban-mcp/board.db` - sqlite - canonical
- **sqlite-whatsapp-mcp** - `aerodeck:/var/lib/docker/volumes/whatsapp-data/_data/store.db (read replica)` - sqlite - canonical
- **aerodeck-db-business-core** - `aeros:/home/ubuntu/data/sqlite-local/aerodeck/aerodeck.db` - sqlite - canonical
- **aeros-shared-sqlite** - `aeros:/home/ubuntu/data/sqlite/shared/aeros.db` - sqlite - canonical
- **agentic-shared-sqlite** - `aeros:/home/ubuntu/data/sqlite/shared/agentic.db` - sqlite - canonical
- **antislop-canon-pg-mirror** - `aeros:aerodeck.antislop_canon` - postgres - canonical
- **company-brain-meetings-gold** - `aeros:/home/ubuntu/apps/company-brain-dev/meetings-gold.db` - sqlite - canonical
- **jiddlers-live-sqlite** - `aeros:/home/ubuntu/data/sqlite/shared/jiddlers/live.db` - sqlite - canonical
- **life-kanban** - `personal:/home/ubuntu/apps/life-kanban/board.db` - sqlite - canonical
- **personal-whatsapp-mcp** - `personal:/var/lib/docker/volumes/miranda_whatsapp-data/_data/store.db (in-container /app/data/store.db)` - sqlite - canonical
- **whatsapp-golden-store** - `personal:/var/lib/docker/volumes/miranda_whatsapp-data/_data/store.db` - sqlite - canonical

## Watchdogs And Scheduled Jobs

- **aerodeck** - 127 scheduled jobs
- **aeros** - 139 scheduled jobs
- **jack-mbp** - 11 scheduled jobs
- **jiddlers** - 16 scheduled jobs
- **mac-mini** - 38 scheduled jobs
- **macbook** - 13 scheduled jobs
- **personal** - 71 scheduled jobs

## GitHub coverage

Source: T1 coverage manifest `github-coverage-canon/coverage.json` (generated `2026-06-18T12:07:44.853261+00:00`). 🟢 = every tracked path clean, 🔴 = drift/untracked.
- Status rollup: detached=5, missing=6, scope-only=1, tracked-clean=22, tracked-dirty=25, untracked=4, vendor=3

- 🟢 **AgriciDaniel/claude-ads** - 1/1 path(s) tracked-clean
- 🟢 **BuilderIO/agent-native** - 1/1 path(s) tracked-clean
- 🟢 **BuilderIO/skills** - 1/1 path(s) tracked-clean
- 🟢 **DietrichGebert/ponytail** - 1/1 path(s) tracked-clean
- 🟢 **NVIDIA/SkillSpector** - 1/1 path(s) tracked-clean
- 🟢 **aerodeck-ai/aerodeck-design** - 1/1 path(s) tracked-clean
- 🟢 **aerodeck-ai/aerodeck-site** - 1/1 path(s) tracked-clean
- 🔴 **aerodeck-ai/aerodeck-template** - 0/4 path(s) tracked-clean
- 🟢 **aerodeck-ai/agent-cockpit** - 1/1 path(s) tracked-clean
- 🔴 **aerodeck-ai/antislop** - 0/1 path(s) tracked-clean
- 🟢 **aerodeck-ai/banaos** - 1/1 path(s) tracked-clean
- 🔴 **aerodeck-ai/berlai-ops** - 0/1 path(s) tracked-clean
- 🟢 **aerodeck-ai/berlos** - 1/1 path(s) tracked-clean
- 🟢 **aerodeck-ai/brand-assets** - 1/1 path(s) tracked-clean
- 🟢 **aerodeck-ai/design-berlos** - 1/1 path(s) tracked-clean
- 🟢 **aerodeck-ai/design-deck** - 2/2 path(s) tracked-clean
- 🟢 **aerodeck-ai/estate-map** - 1/1 path(s) tracked-clean
- 🔴 **aerodeck-ai/factory** - 0/3 path(s) tracked-clean
- 🟢 **aerodeck-ai/factory-v1** - 1/1 path(s) tracked-clean
- 🔴 **aerodeck-ai/infra** - 0/1 path(s) tracked-clean
- 🔴 **aerodeck-ai/jiddlers** - 0/1 path(s) tracked-clean
- 🔴 **bytedance/deer-flow** - 0/1 path(s) tracked-clean
- 🟢 **cjpais/handy** - 1/1 path(s) tracked-clean
- 🔴 **drachtio/drachtio-server** - 0/1 path(s) tracked-clean
- 🔴 **freeswitch/sofia-sip** - 0/1 path(s) tracked-clean
- 🔴 **freeswitch/spandsp** - 0/1 path(s) tracked-clean
- 🟢 **helallao/perplexity-ai** - 1/1 path(s) tracked-clean
- 🔴 **iamlukethedev/Claw3D** - 0/3 path(s) tracked-clean
- 🔴 **jambonz/jambonz-api-server** - 0/1 path(s) tracked-clean
- 🔴 **jambonz/jambonz-feature-server** - 0/1 path(s) tracked-clean
- 🔴 **jambonz/sbc-inbound** - 0/1 path(s) tracked-clean
- 🔴 **jambonz/sbc-outbound** - 0/1 path(s) tracked-clean
- 🟢 **jgraph/drawio-mcp** - 1/1 path(s) tracked-clean
- 🟢 **karpathy/autoresearch** - 1/1 path(s) tracked-clean
- 🟢 **mattpocock/skills** - 1/1 path(s) tracked-clean
- 🔴 **nateherkai/AIS-OS** - 0/1 path(s) tracked-clean
- 🟢 **shadcn/improve** - 1/1 path(s) tracked-clean
- 🔴 **simstudioai/sim** - 0/1 path(s) tracked-clean
- 🔴 **teoobarca/perplexity-mcp** - 0/1 path(s) tracked-clean
- 🔴 **13 live path(s) not in GitHub** (untracked / no origin).
