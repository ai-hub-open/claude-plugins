# ai-hub-open — скиллы для рекламы в Claude

Пять скиллов, которые ведут работу маркетолога от стратегии до запуска и аудита рекламы.
Ниже — установка в Claude Desktop по шагам, список скиллов — [после неё](#что-внутри).

## Установка в Claude Desktop

### Шаг 1. Установите Git

Claude Desktop скачивает плагины через Git — без него каталог не добавится. Если Git уже стоит,
переходите к шагу 2 (проверка — в конце этого шага).

**Windows**

1. Откройте [git-scm.com](https://git-scm.com/) и нажмите **Download for Windows**.
2. Скачайте установщик для своей системы — обычно **64-bit Git for Windows Setup**.
3. Запустите скачанный файл и нажимайте **Next** до конца, ничего не меняя, затем **Install**
   и **Finish**.

**macOS**

1. Откройте программу **Терминал** (Finder → Программы → Утилиты → Терминал).
2. Введите `git --version` и нажмите Enter.
3. Если Git нет, macOS предложит установить инструменты разработчика — нажмите **Установить**
   и дождитесь конца. Другие способы — на [git-scm.com/download/mac](https://git-scm.com/download/mac).

**Проверка.** Откройте **PowerShell** (Windows: Пуск → наберите «PowerShell») или **Терминал**
(macOS), введите:

```
git --version
```

Ответ вида `git version 2.…` — всё в порядке. Если пишет, что команда не найдена, переустановите
Git и откройте окно терминала заново.

После установки Git **полностью закройте Claude Desktop и откройте снова** — иначе он Git
не увидит.

### Шаг 2. Добавьте каталог

1. В Claude Desktop откройте **Settings → Plugins**.
2. Нажмите **+ → Add marketplace → Add from repository**.
3. Вставьте адрес этого репозитория и подтвердите:

   ```
   https://github.com/ai-hub-open/claude-plugins
   ```

   Репозиторий открытый — входить в GitHub и подключать его не нужно.
4. В списке каталогов появится **ai-hub-open**.

### Шаг 3. Поставьте нужные скиллы

Откройте каталог **ai-hub-open** (или вкладку **Discover**) и нажмите **Add** / **Install** у нужных
скиллов. Ставьте только нужные — они независимы. Что делает каждый — [в таблице ниже](#что-внутри).

### Шаг 4. Включите автообновление

У сторонних каталогов автообновление по умолчанию **выключено** — без него новые версии не придут.

1. В **Settings → Plugins** откройте каталог **ai-hub-open**.
2. Включите **Auto-update** (автообновление) и убедитесь, что переключатель остался включённым.

Если такого переключателя нет — включите из Claude Code: `/plugin` → **Marketplaces** →
`ai-hub-open` → **Enable auto-update**. Даже без автообновления скилл сам скажет в начале
разговора, что вышла новая версия.

### Шаг 5. Проверьте

Откройте новый разговор на вкладке **Code** и начните сообщение с `/` — скиллы появятся в списке
с именем плагина, например `/yandex-direct-audit:yandex-direct-audit`. Или просто попросите своими
словами: «сделай аудит Директа», «нужна маркетинговая стратегия».

Чтобы скилл попал в рекламный кабинет, подключите коннектор — [см. «Коннекторы»](#коннекторы).

**«Failed to add marketplace».** Проверьте, что Git установлен и Claude Desktop перезапущен после
установки (шаг 1). Если да — скорее всего, каталог `ai-hub-open` у вас уже есть, например,
добавленный раньше командой в терминале. Найдите его в списке каталогов (в **Settings → Plugins**
или командой `/plugin marketplace list`), удалите и добавьте заново — или пользуйтесь уже
добавленным.

## Что внутри

| Плагин | Что делает | Репозиторий |
|---|---|---|
| `marketing-strategist` | Маркетинговая стратегия до запуска: каналы, бюджет по фазам, KPI, передача в площадочные скиллы | [ai-hub-open/marketing-strategist](https://github.com/ai-hub-open/marketing-strategist) |
| `yandex-direct-manager` | Создание кампании в Яндекс.Директе от брифа до черновика в кабинете | [ai-hub-open/yandex-direct-manager](https://github.com/ai-hub-open/yandex-direct-manager) |
| `yandex-direct-audit` | Аудит, точечные правки и недельное ведение работающих кампаний Директа | [ai-hub-open/yandex-direct-audit](https://github.com/ai-hub-open/yandex-direct-audit) |
| `vk-ads-manager` | VK Реклама от брифа до залива в кабинет и работы с активной кампанией | [ai-hub-open/vk-ads-manager](https://github.com/ai-hub-open/vk-ads-manager) |
| `yandex-metrika-manager` | Аудит, анализ и управление Яндекс Метрикой (цели и сегменты под гейтом) | [ai-hub-open/yandex-metrika-manager](https://github.com/ai-hub-open/yandex-metrika-manager) |

Стратег сам передаёт готовую стратегию в скиллы Директа и VK, если они установлены.

## Другие способы установки

| Где вы работаете | Способ | Обновления |
|---|---|---|
| Claude Desktop | [Установка в Claude Desktop](#установка-в-claude-desktop) — выше | сами, после шага 4 |
| Claude Code в терминале | [Командами Claude Code](#claude-code-в-терминале) | сами, после одной настройки |
| claude.ai в браузере, бесплатный тариф или нужен один скилл без каталога | [Архивом](#архивом) | вручную; скилл сам скажет, что вышла новая версия |

**Выберите один способ.** Claude Desktop и Claude Code в терминале — это одни и те же настройки:
каталог, добавленный в Desktop, виден и в терминале, и наоборот. Если поставить скилл ещё и
архивом или папкой, он появится дважды — оставьте один.

## Claude Code в терминале

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

**Claude Desktop** читает те же настройки, что и терминал: плагины, поставленные командами выше,
появятся и там — в **Settings → Plugins**.

Если раньше скилл лежал папкой в `~/.claude/skills/`, удалите её — иначе скилл загрузится дважды.

## Архивом

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

- **Каталог не добавляется.** Проверьте Git и перезапуск Desktop — [шаг 1](#шаг-1-установите-git).
- **Скилла нет в списке.** Desktop и Claude Code: в **Settings → Plugins** (или `/plugin` → **Installed**) проверьте,
  что плагин добавлен и включён. Архив: проверьте переключатель в **Customize → Skills**.
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
