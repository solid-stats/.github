<!-- Keep profile/README.md (RU) and profile/README.en.md (EN) in sync: edit both in the same change. -->
<div align="center">

# Solid Stats

**The engineering home of the [Solid Games](https://sg.zone) ArmA 3 community.**

Solid Stats is the engineering side of the Solid Games community: a match-statistics
platform and the tooling the community's operations run on. It turns OCAP mission
replays into clean, fair, per-player statistics — for every operation.

[Русский](README.md) · 🇬🇧 **English**

[Community](https://sg.zone) · [Replays](https://sg.zone/replays)

<!-- TODO: add the public Solid Stats site URL once V2 ships, e.g. · [Statistics](https://stats.sg.zone) -->

</div>

---

## 🤖 Built entirely by AI agents

Solid Stats is developed **end to end by AI agents** running the **GSD workflow** — a
structured, phase-based process (explore → spec → plan → execute → review → verify → ship).
Humans set direction and approve; agents do the building. Every repository carries its own
`.planning/` state, and shared engineering standards live in
[`skills`](https://github.com/solid-stats/skills).

## 📊 Flagship — the Solid Stats 2 platform

A mission is played on the server and recorded by **OCAP**. Solid Stats then:

1. **Discovers** new replays and stores the raw data,
2. **Parses** each replay into a compact, deterministic statistics artifact,
3. **Promotes** it into canonical player records — identity, corrections, aggregates, bounty points,
4. **Serves** it to the web UI so the community can explore who did what.

## 🧩 Repositories

| Repository | Stack | Responsibility |
|------------|-------|----------------|
| [`replays-fetcher`](https://github.com/solid-stats/replays-fetcher) | TypeScript | Discovers OCAP replays, stores raw objects, writes ingest staging records |
| [`replay-parser-2`](https://github.com/solid-stats/replay-parser-2) | Rust | Deterministic OCAP → versioned statistics artifacts |
| [`server-2`](https://github.com/solid-stats/server-2) | TypeScript · Fastify | Source of truth: API, PostgreSQL, job orchestration, identity, moderation |
| `web` | React · TanStack Start | Browser UI for exploring statistics (private repository) |
| [`relay`](https://github.com/solid-stats/relay) | JavaScript | SG Stats Relay: relay for `sg.zone` with per-user tokens and an admin panel behind Authelia |
| [`infrastructure`](https://github.com/solid-stats/infrastructure) | Kubernetes | Staging runtime, backups, operational runbooks |
| [`plans`](https://github.com/solid-stats/plans) | — | Product-level and strategic planning |
| [`skills`](https://github.com/solid-stats/skills) | — | Shared AI-agent engineering standards |

> The current platform is Solid Stats 2, succeeding the original generation
> ([`server`](https://github.com/solid-stats/server),
> [`sg-replay-parser`](https://github.com/solid-stats/sg-replay-parser)), which is no longer maintained.

## 🛠️ Built with

TypeScript · Rust · React / TanStack Start · Fastify · PostgreSQL · RabbitMQ · S3 · Kubernetes

---

<div align="center">
<sub>Maintained by <a href="https://github.com/Afgan0r">@Afgan0r</a> · part of the <a href="https://sg.zone">Solid Games</a> community</sub>
<br>
<sub>© 2026 Solid Stats. All rights reserved. Source-available for viewing, not for reuse — see <a href="https://github.com/solid-stats/.github/blob/master/LICENSE">LICENSE</a>.</sub>
</div>
