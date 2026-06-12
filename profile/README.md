<!-- Держите profile/README.md (RU) и profile/README.en.md (EN) в синхроне: правьте оба в одном изменении. -->
<div align="center">

# Solid Stats

**Инженерный дом сообщества [Solid Games](https://sg.zone) (ArmA 3).**

Это инженерная сторона сообщества Solid Games: платформа статистики матчей
и инструменты для его операций. Записи миссий OCAP превращаются в честную
пер-игровую статистику по каждой операции.

🇷🇺 **Русский** · [English](README.en.md)

[Сообщество](https://sg.zone) · [Реплеи](https://sg.zone/replays)

<!-- TODO: добавить публичный URL сайта Solid Stats, когда выйдет V2, напр. · [Статистика](https://stats.sg.zone) -->

</div>

---

## 🤖 Полностью на AI-агентах

Solid Stats от и до разрабатывают AI-агенты по пошаговому процессу **GSD** (explore, spec,
plan, execute, review, verify, ship). Люди задают направление и принимают результат, а всё
строят агенты. У каждого репозитория свой каталог `.planning/`, а общие инженерные
стандарты лежат в [`skills`](https://github.com/solid-stats/skills).

## 📊 Флагман: платформа Solid Stats 2

Матч играется на сервере и записывается через **OCAP**. Дальше Solid Stats:

1. **Находит** новые реплеи и складывает сырые данные,
2. **Парсит** каждый реплей в компактный детерминированный артефакт статистики,
3. **Продвигает** его в канонические записи игроков: идентичность, корректировки, агрегаты, очки баунти,
4. **Отдаёт** их в веб-интерфейс, чтобы сообщество видело, кто что сделал.

## 🧩 Репозитории

| Репозиторий | Стек | Зона ответственности |
|------------|------|----------------------|
| [`replays-fetcher`](https://github.com/solid-stats/replays-fetcher) | TypeScript | Находит OCAP-реплеи, хранит сырые объекты, пишет staging-записи ingest |
| [`replay-parser-2`](https://github.com/solid-stats/replay-parser-2) | Rust | Детерминированный OCAP → версионированные артефакты статистики |
| [`server-2`](https://github.com/solid-stats/server-2) | TypeScript · Fastify | Источник правды: API, PostgreSQL, оркестрация задач, идентичность, модерация |
| `web` | React · TanStack Start | Браузерный UI для просмотра статистики (приватный репозиторий) |
| [`relay`](https://github.com/solid-stats/relay) | JavaScript | SG Stats Relay: релей для `sg.zone` с токенами на пользователя и админкой за Authelia |
| [`infrastructure`](https://github.com/solid-stats/infrastructure) | Kubernetes | Стейджинг-рантайм, бэкапы, операционные ранбуки |
| [`plans`](https://github.com/solid-stats/plans) | планирование | Продуктовое и стратегическое планирование |
| [`skills`](https://github.com/solid-stats/skills) | стандарты | Общие инженерные стандарты для AI-агентов |

> Сейчас актуальна платформа Solid Stats 2. Предыдущее поколение
> ([`server`](https://github.com/solid-stats/server),
> [`sg-replay-parser`](https://github.com/solid-stats/sg-replay-parser)) больше не поддерживается.

## 🛠️ Стек

TypeScript · Rust · React / TanStack Start · Fastify · PostgreSQL · RabbitMQ · S3 · Kubernetes

---

<div align="center">
<sub>Сопровождает <a href="https://github.com/Afgan0r">@Afgan0r</a> · часть сообщества <a href="https://sg.zone">Solid Games</a></sub>
<br>
<sub>© 2026 Solid Stats. Все права защищены. Исходный код открыт для просмотра, но не для переиспользования (см. <a href="https://github.com/solid-stats/.github/blob/master/LICENSE">LICENSE</a>).</sub>
</div>
