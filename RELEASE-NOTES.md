# BuildPlanner RU/EN — Compatibility & Tool Protection

## English

Unofficial BuildPlanner update for Space Engineers 2, based on [Vito Pistelli's MIT-licensed BuildPlanner v1.1.0](https://github.com/viligante8/SpaceEngineers2BuildPlanner). This is a community patch, not an upstream author release.

### Changes

- Fixed tool-panel timing that could leave welder right-click queueing inactive: the game opens the panel asynchronously, and the plugin now reconciles its state after the client update.
- Protected registered hand tools and weapons, including modded AreaTools, from Alt+N deposit even when a mod labels them as materials/components.
- Added Russian and English plugin notifications and all nine control-action names. Language follows the game's selected culture, with an optional manual override.

### Installation

1. Download **BuildPlanner-1.1.0-ru-en.3.zip** from Assets, rather than GitHub's automatic Source code archives.
2. Close the game and back up your existing BuildPlanner folder.
3. Extract the whole BuildPlanner folder to a permanent writable location, for example `D:\SE2Mods\BuildPlanner`. Keep all bundled DLLs together. Replace existing plugin files if updating; load only one BuildPlanner version.
4. In Steam → Space Engineers 2 → Properties → General → Launch Options:

```text
"-plugins:D:\SE2Mods\BuildPlanner\BuildPlanner.dll"
```

If using AutoSorter too, use one combined argument:

```text
"-plugins:D:\SE2Mods\BuildPlanner\BuildPlanner.dll;D:\SE2Mods\AutoSorter\AutoSorter.dll"
```

Use your actual paths. Append to an existing -plugins argument with a semicolon; do not create a second one. Preserve unrelated launch options.

### Language and controls

`language.txt` next to the DLL: `auto` = game language, `ru` = Russian, `en` = English. Restart the game after changing it. Item/block names are supplied by the game/mods; diagnostic logs stay English.

- Welder equipped + visible unfinished-block panel + right-click: queue the target.
- N: withdraw queued components while aiming at a connected container.
- Alt+N: deposit materials, keeping registered tools.
- Shift+N: request production.
- Shift+Alt+N: clear the queue.

Controls can be rebound in the game's Building controls. Full instructions are in LANGUAGE-RU-EN.md.

### Verification

Built against Game2.Simulation 4.0.0.3165. The user confirmed the preceding compatibility build worked in their game. This bilingual build passed 42 language checks, 6 isolated panel/hook checks and 28 deposit-filter checks. Live validation of the new translation is pending; compatibility with every mod/game version is not guaranteed. NuGet's online dependency audit was unavailable during the build.

Report issues with the game version, steps and `%APPDATA%\SpaceEngineers2\BuildPlanner\BuildPlanner.log`. Restore your backup to roll back. This plugin is installed manually, not via Steam Workshop.

---

## Русский

Неофициальное обновление BuildPlanner для Space Engineers 2 на основе [BuildPlanner v1.1.0 от Vito Pistelli, лицензия MIT](https://github.com/viligante8/SpaceEngineers2BuildPlanner). Это патч сообщества, а не релиз автора оригинала.

### Изменения

- Исправлена обработка асинхронного открытия панели сварщика, из-за которой ПКМ мог не добавлять блоки в очередь.
- Зарегистрированные инструменты и оружие, включая модовые AreaTools, исключены из выгрузки Alt+N даже с ошибочной категорией материалов/компонентов.
- Добавлены русские и английские уведомления и названия девяти команд управления. Язык определяется по игре или задаётся вручную.

### Установка

1. Скачайте **BuildPlanner-1.1.0-ru-en.3.zip** из Assets. Автоматические архивы Source code для установки не нужны.
2. Закройте игру и сохраните копию старой папки BuildPlanner.
3. Распакуйте всю папку BuildPlanner, например в `D:\SE2Mods\BuildPlanner`, с заменой файлов при обновлении. Все DLL должны лежать вместе. Загружайте только одну сборку BuildPlanner.
4. Steam → Space Engineers 2 → Свойства → Общие → Параметры запуска:

```text
"-plugins:D:\SE2Mods\BuildPlanner\BuildPlanner.dll"
```

Совместно с AutoSorter:

```text
"-plugins:D:\SE2Mods\BuildPlanner\BuildPlanner.dll;D:\SE2Mods\AutoSorter\AutoSorter.dll"
```

Укажите свои фактические пути. Если -plugins уже есть, добавьте путь через точку с запятой внутри него. Второй параметр -plugins не нужен. Остальные параметры запуска сохраните.

### Язык и управление

В `language.txt` рядом с DLL: `auto` — язык игры, `ru` — русский, `en` — английский. После изменения перезапустите игру. Названия предметов/блоков берутся из игры и модов, технический лог остаётся английским.

- Со сварщиком наведитесь на недостроенный блок до появления панели компонентов и нажмите ПКМ — добавить в очередь.
- N у подключённого контейнера — получить компоненты.
- Alt+N — выгрузить материалы, оставив зарегистрированные инструменты.
- Shift+N — заказать производство.
- Shift+Alt+N — очистить очередь.

Команды переназначаются в настройках управления, раздел строительства. Полная инструкция — LANGUAGE-RU-EN.md.

### Проверка

Сборка для Game2.Simulation 4.0.0.3165. Пользователь подтвердил работу предыдущего compatibility fix в игре. Новая двуязычная сборка прошла 42 языковые проверки, 6 отдельных проверок панели/перехватчика и 28 проверок выгрузки. Отображение нового перевода ещё нужно проверить в игре. Онлайн-аудит зависимостей NuGet при сборке был недоступен.

При ошибке приложите версию игры, шаги и `%APPDATA%\SpaceEngineers2\BuildPlanner\BuildPlanner.log`. Для отката верните резервную копию. Плагин устанавливается вручную, не через Steam Workshop.
