# ai-hub-open — маркетплейс плагинов для Claude Code

Скиллы ai-hub-open, которые ставятся и обновляются через `/plugin`.

## Подключение

В сессии Claude Code:

```
/plugin marketplace add ai-hub-open/claude-plugins
/plugin install yandex-direct-manager@ai-hub-open
/plugin install marketing-strategist@ai-hub-open
```

Ставьте нужные: плагины независимы.

Один раз включите автообновление: `/plugin` → **Marketplaces** → `ai-hub-open` → **Enable auto-update**.
Без него обновляйтесь командой `/plugin marketplace update ai-hub-open`.

## Плагины

| Плагин | Что делает | Репозиторий |
|---|---|---|
| `yandex-direct-manager` | Создание кампании в Яндекс.Директе от брифа до DRAFT | [ai-hub-open/yandex-direct-manager](https://github.com/ai-hub-open/yandex-direct-manager) |
| `marketing-strategist` | Маркетинговая стратегия до запуска: каналы, бюджет по фазам, KPI, передача в площадочные скиллы | [ai-hub-open/marketing-strategist](https://github.com/ai-hub-open/marketing-strategist) |

## Для авторов: как выпустить обновление

Пользователи получают новую версию, только когда меняется `version` в `.claude-plugin/plugin.json`
репозитория плагина. Поднимите её вместе с `VERSION` и `CHANGELOG.md` — CI в репозитории плагина
проверит, что все три совпадают. Этот каталог при релизе менять не нужно: он ссылается на `main`
репозитория плагина.

Новый плагин — новая запись в `plugins` в `.claude-plugin/marketplace.json`, затем
`claude plugin validate .`.
