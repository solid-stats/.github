<!-- Держите profile/README.md (RU) и profile/README.en.md (EN) в синхроне: правьте оба в одном изменении. -->
<div align="center">

# Solid Stats

**Статистика игр сообщества [Solid Games](https://sg.zone) (ArmA 3).**

Solid Stats превращает записи миссий OCAP в честную статистику по игрокам за каждую
игру сообщества Solid Games.

<sub>Независимый проект игрока. Не связан с администрацией [sg.zone](https://sg.zone).</sub>

🇷🇺 **Русский** · [English](README.en.md)

[Сообщество](https://sg.zone) · [Реплеи](https://sg.zone/replays)

<!-- TODO: добавить публичный URL сайта Solid Stats, когда выйдет V2, напр. · [Статистика](https://stats.sg.zone) -->

</div>

---

## 🤖 Полностью на AI-агентах

Solid Stats от и до разрабатывают AI-агенты по пошаговому процессу **[GSD](https://github.com/open-gsd/gsd-core)** (explore, spec,
plan, execute, review, verify, ship). Люди задают направление и принимают результат, а всё
строят агенты. У каждого репозитория свой каталог `.planning/`, а общие инженерные
стандарты лежат в [`skills`](https://github.com/solid-stats/skills).

## 📊 Как это работает

Матч играется на сервере и записывается через **OCAP**. Дальше Solid Stats:

1. **Находит** новые реплеи и складывает сырые данные.
2. **Парсит** каждый реплей в компактный воспроизводимый набор статистики.
3. **Собирает** профиль каждого игрока: склеивает его никнеймы в одного человека, применяет ручные правки, считает суммарную статистику и награду за голову.
4. **Отдаёт** их в веб-интерфейс, чтобы сообщество видело, кто что сделал.

## 🧩 Репозитории

| Репозиторий | Стек | Зона ответственности |
|------------|------|----------------------|
| [`replays-fetcher`](https://github.com/solid-stats/replays-fetcher) | TypeScript | Находит OCAP-реплеи, хранит сырые объекты, пишет staging-записи ingest |
| [`replay-parser-2`](https://github.com/solid-stats/replay-parser-2) | Rust | Детерминированный OCAP → версионированные артефакты статистики |
| [`server-2`](https://github.com/solid-stats/server-2) | TypeScript · Fastify | Источник правды: API, PostgreSQL, оркестрация задач, идентичность, модерация |
| `web` | React · TanStack Start | Браузерный UI для просмотра статистики (приватный репозиторий) |
| [`infrastructure`](https://github.com/solid-stats/infrastructure) | Kubernetes | Стейджинг-рантайм, бэкапы, операционные ранбуки |
| [`plans`](https://github.com/solid-stats/plans) | планирование | Продуктовое и стратегическое планирование |
| [`skills`](https://github.com/solid-stats/skills) | стандарты | Общие инженерные стандарты для AI-агентов |

> Сейчас актуально поколение Solid Stats 2. Предыдущее
> ([`server`](https://github.com/solid-stats/server),
> [`sg-replay-parser`](https://github.com/solid-stats/sg-replay-parser),
> [`relay`](https://github.com/solid-stats/relay)) больше не поддерживается.

## 🛠️ Стек

TypeScript · Rust · React / TanStack Start · Fastify · PostgreSQL · RabbitMQ · S3 · Kubernetes

---

<div align="center">
<sub>Сопровождает <a href="https://github.com/Afgan0r">@Afgan0r</a></sub>
<br>
<sub>© 2026 Solid Stats. Лицензия <a href="https://github.com/solid-stats/.github/blob/master/LICENSE">MIT</a>: переиспользуйте с указанием авторства.</sub>
</div>
