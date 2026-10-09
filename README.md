# ai-hub-open — скиллы для рекламы в Claude

Пять скиллов, которые ведут работу маркетолога от стратегии до запуска и аудита рекламы:

| Плагин | Что делает | Репозиторий |
|---|---|---|
| `marketing-strategist` | Маркетинговая стратегия до запуска: каналы, бюджет по фазам, KPI, передача в площадочные скиллы | [ai-hub-open/marketing-strategist](https://github.com/ai-hub-open/marketing-strategist) |
| `yandex-direct-manager` | Создание кампании в Яндекс.Директе от брифа до черновика в кабинете | [ai-hub-open/yandex-direct-manager](https://github.com/ai-hub-open/yandex-direct-manager) |
| `yandex-direct-audit` | Аудит, точечные правки и недельное ведение работающих кампаний Директа | [ai-hub-open/yandex-direct-audit](https://github.com/ai-hub-open/yandex-direct-audit) |
| `vk-ads-manager` | VK Реклама от брифа до залива в кабинет и работы с активной кампанией | [ai-hub-open/vk-ads-manager](https://github.com/ai-hub-open/vk-ads-manager) |
| `yandex-metrika-manager` | Аудит, анализ и управление Яндекс Метрикой (цели и сегменты под гейтом) | [ai-hub-open/yandex-metrika-manager](https://github.com/ai-hub-open/yandex-metrika-manager) |

Ставьте только нужные — скиллы независимы. Стратег сам передаёт готовую стратегию в скиллы
Директа и VK, если они установлены.

## Какой способ установки выбрать

| Где вы работаете | Способ | Обновления |
|---|---|---|
| Claude Desktop или claude.ai — обычный чат или Cowork; платный тариф (Pro, Max, Team, Enterprise) | [1. Через интерфейс](#способ-1-claude-desktop-или-claudeai--через-интерфейс) | сами |
| Claude Code — в терминале или на вкладке **Code** в Claude Desktop | [2. Командами Claude Code](#способ-2-claude-code) | сами, после одной настройки |
| Бесплатный тариф или нужен один скилл без маркетплейса | [3. Архивом](#способ-3-архивом) | вручную; скилл сам скажет, что вышла новая версия |

**Выберите один способ.** Плагин, добавленный в аккаунт способом 1, сам появится и в Claude Code
при следующем запуске. А поставленный в Claude Code (способ 2) остаётся только на этом
компьютере и в чат не попадает. Если поставить один и тот же скилл двумя способами, он появится
дважды.

## Способ 1. Claude Desktop или claude.ai — через интерфейс

1. Откройте **Customize → Plugins** (в Claude Desktop или на claude.ai).
2. Нажмите **Add → Add marketplace**.
3. Вставьте адрес каталога и подтвердите:

   ```
   ai-hub-open/claude-plugins
   ```

   Репозиторий открытый — подключать GitHub не нужно.
4. В каталоге **ai-hub-open** установите нужные плагины.
5. Чтобы новые версии приходили сами, включите у каталога **Sync automatically**. Проверить
   обновления вручную — **Check for updates**.

Как вызвать: начните сообщение с `/` — скиллы появятся в списке с именем плагина. Или просто
попросите своими словами: «сделай аудит Директа», «нужна маркетинговая стратегия».

На тарифах Team и Enterprise владелец организации может ограничить, какие плагины можно
добавлять, — если пункта **Add marketplace** нет, обратитесь к нему.

## Способ 2. Claude Code

В сессии Claude Code (в терминале — команда `claude`):

```
/plugin marketplace add ai-hub-open/claude-plugins
/plugin install marketing-strategist@ai-hub-open
/plugin install yandex-direct-manager@ai-hub-open
/plugin install yandex-direct-audit@ai-hub-open
/plugin install vk-ads-manager@ai-hub-open
/plugin install yandex-metrika-manager@ai-hub-open
```

Один раз включите автообновление: `/plugin` → **Marketplaces** → `ai-hub-open` →
**Enable auto-update**. У сторонних каталогов оно по умолчанию выключено; без него обновляйтесь
командой `/plugin marketplace update ai-hub-open`.

Скиллы вызываются как `/marketing-strategist:marketing-strategist`,
`/yandex-direct-audit:yandex-direct-audit` и т. д. — или просьбой своими словами.

**Вкладка Code в Claude Desktop** читает те же настройки, что и терминал: плагины, поставленные
командами выше, появятся и там. Управлять ими на вкладке: кнопка **+** рядом с полем ввода →
**Plugins** → **Manage plugins**.

Если раньше скилл лежал папкой в `~/.claude/skills/`, удалите её — иначе скилл загрузится дважды.

## Способ 3. Архивом

Работает на любом тарифе, включая бесплатный.

1. Включите **Settings → Capabilities → Code execution and file creation** — без него скиллы
   не загружаются.
2. Скачайте архив нужного скилла из последнего релиза:

   | Скилл | Архив |
   |---|---|
   | `marketing-strategist` | [marketing-strategist.zip](https://github.com/ai-hub-open/marketing-strategist/releases/latest) |
   | `yandex-direct-manager` | [yandex-direct-manager.skill](https://github.com/ai-hub-open/yandex-direct-manager/releases/latest) |
   | `yandex-direct-audit` | [yandex-direct-audit.zip](https://github.com/ai-hub-open/yandex-direct-audit/releases/latest) |
   | `vk-ads-manager` | [vk-ads-manager.skill](https://github.com/ai-hub-open/vk-ads-manager/releases/latest) |
   | `yandex-metrika-manager` | [yandex-metrika-manager.zip](https://github.com/ai-hub-open/yandex-metrika-manager/releases/latest) |

   Файл `.skill` — это обычный ZIP. Если окно загрузки его не принимает, переименуйте в `.zip`.
3. Откройте **Customize → Skills** → **+** → **Create skill** → **Upload a skill** и выберите
   архив.

Обновляется вручную: в начале разговора скилл сверяет свою версию с GitHub и, если вышла новая,
скажет об этом и даст ссылку на архив. Старый скилл удалите и загрузите новый.

## Коннекторы

Скиллы работают с рекламными кабинетами через коннекторы (MCP) Click.ru — без них скилл
расскажет, что подключить, но в кабинет не попадёт. Какой коннектор нужен и где взять адрес,
написано в README каждого скилла.

- **Claude Desktop / claude.ai:** **Settings → Connectors → Add custom connector**, в поле URL —
  адрес коннектора.
- **Claude Code:** `claude mcp add --scope user --transport http <имя> "<адрес коннектора>"`.

⚠️ Адрес коннектора содержит токен и равносилен паролю от кабинета: не пересылайте его и не
вставляйте в общие чаты. При утечке отзовите токен в Click.ru.

## Если что-то не так

- **Скилла нет в списке.** Способ 1: проверьте, что плагин включён (**Customize → Plugins**).
  Способ 2: `/plugin` → **Installed**. Способ 3: проверьте переключатель в **Customize → Skills**.
- **Скилл появился дважды.** Он установлен двумя способами — оставьте один.
- **Скилл не срабатывает на просьбу своими словами.** Вызовите его через `/`. Если у вас очень
  много скиллов, Claude Code обрезает их описания; лишние можно отключить в `/skills`.

## Для авторов: как выпустить обновление

Пользователи получают новую версию, только когда меняется `version` в `.claude-plugin/plugin.json`
репозитория плагина. Поднимите её вместе с `VERSION` и `CHANGELOG.md` — CI в репозитории плагина
проверит, что все три совпадают. Этот каталог при релизе менять не нужно: он ссылается на `main`
репозитория плагина.

Новый плагин — новая запись в `plugins` в `.claude-plugin/marketplace.json` (источник — HTTPS-адрес
репозитория, не `"source": "github"`: тот ставится по SSH и падает без ключа), затем
`claude plugin validate .`. Шапка `SKILL.md` должна разбираться строгим YAML: значения с «: »
внутри — в кавычках, иначе Claude Code загрузит скилл без описания.
