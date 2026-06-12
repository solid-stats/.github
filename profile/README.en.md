<!-- Keep profile/README.md (RU) and profile/README.en.md (EN) in sync: edit both in the same change. -->
<div align="center">

# Solid Stats

**Match statistics for the [Solid Games](https://sg.zone) ArmA 3 community.**

Solid Stats turns OCAP mission replays into fair, per-player statistics for every operation
the Solid Games community plays.

<sub>An independent, player-made project. Not affiliated with the sg.zone administration.</sub>

[Русский](README.md) · 🇬🇧 **English**

[Community](https://sg.zone) · [Replays](https://sg.zone/replays)

<!-- TODO: add the public Solid Stats site URL once V2 ships, e.g. · [Statistics](https://stats.sg.zone) -->

</div>

---

## 🤖 Built entirely by AI agents

Solid Stats is built end to end by AI agents running the **GSD workflow**: a phased process
of explore, spec, plan, execute, review, verify, ship. Humans set direction and approve;
agents do the building. Every repository carries its own `.planning/` state, and shared
engineering standards live in [`skills`](https://github.com/solid-stats/skills).

## 📊 How it works

A mission is played on the server and recorded by **OCAP**. Solid Stats then:

1. **Discovers** new replays and stores the raw data.
2. **Parses** each replay into a compact, reproducible set of statistics.
3. **Builds** each player's profile: merges their aliases into one identity, applies manual corrections, and tallies career totals and bounty.
4. **Serves** it to the web UI so the community can explore who did what.

## 🧩 Repositories

| Repository | Stack | Responsibility |
|------------|-------|----------------|
| [`replays-fetcher`](https://github.com/solid-stats/replays-fetcher) | TypeScript | Discovers OCAP replays, stores raw objects, writes ingest staging records |
| [`replay-parser-2`](https://github.com/solid-stats/replay-parser-2) | Rust | Deterministic OCAP → versioned statistics artifacts |
| [`server-2`](https://github.com/solid-stats/server-2) | TypeScript · Fastify | Source of truth: API, PostgreSQL, job orchestration, identity, moderation |
| `web` | React · TanStack Start | Browser UI for exploring statistics (private repository) |
| [`infrastructure`](https://github.com/solid-stats/infrastructure) | Kubernetes | Staging runtime, backups, operational runbooks |
| [`plans`](https://github.com/solid-stats/plans) | planning | Product-level and strategic planning |
| [`skills`](https://github.com/solid-stats/skills) | standards | Shared AI-agent engineering standards |

> The current generation is Solid Stats 2. The previous one
> ([`server`](https://github.com/solid-stats/server),
> [`sg-replay-parser`](https://github.com/solid-stats/sg-replay-parser),
> [`relay`](https://github.com/solid-stats/relay)) is no longer maintained.

## 🛠️ Built with

TypeScript · Rust · React / TanStack Start · Fastify · PostgreSQL · RabbitMQ · S3 · Kubernetes

---

<div align="center">
<sub>Maintained by <a href="https://github.com/Afgan0r">@Afgan0r</a></sub>
<br>
<sub>© 2026 Solid Stats. Licensed under <a href="https://github.com/solid-stats/.github/blob/master/LICENSE">MIT</a>: reuse freely, with attribution.</sub>
</div>
