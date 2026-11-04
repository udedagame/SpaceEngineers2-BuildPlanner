# BuildPlanner RU/EN for Space Engineers 2

[Русский ↓](#русский)

Unofficial compatibility and localization update based on [Vito Pistelli's BuildPlanner](https://github.com/viligante8/SpaceEngineers2BuildPlanner), MIT licensed. Original copyright and third-party notices are retained. This is not an upstream-author release.

## Download and install

Open this repository's **Releases** section and download **BuildPlanner-1.1.0-ru-en.3.zip** from the release assets. Do not use GitHub's automatic Source code archives for installation.

Close the game, back up any existing BuildPlanner folder and extract the complete plugin folder, for example to `D:\SE2Mods\BuildPlanner`. Keep every bundled DLL together and load only one BuildPlanner version.

Steam → Space Engineers 2 → Properties → General → Launch Options:

```text
"-plugins:D:\SE2Mods\BuildPlanner\BuildPlanner.dll"
```

With AutoSorter:

```text
"-plugins:D:\SE2Mods\BuildPlanner\BuildPlanner.dll;D:\SE2Mods\AutoSorter\AutoSorter.dll"
```

Use your actual paths. Append to an existing -plugins argument rather than adding a second one. AutoSorter is optional.

## What changed

- Fixed asynchronous welder-panel handling that could disable right-click queueing.
- Excluded registered tools/weapons from Alt+N deposit, including modded tools with material flags.
- Added Russian/English notifications and nine action labels. `language.txt`: auto, ru or en; restart after changing it.

Equip a welder, aim at an unfinished block until the component panel is visible and right-click to queue. Aim at a connected container and press N to withdraw components. Alt+N deposits materials; Shift+N requests production; Shift+Alt+N clears the queue. Controls can be rebound.

The previous compatibility build was confirmed working by the user. This bilingual build passed isolated tests; live translation validation is pending. Built against Game2.Simulation 4.0.0.3165. Diagnostic logs remain English. See LANGUAGE-RU-EN.md and RELEASE-NOTES.md for details. Preserve a backup to roll back.

## Русский

Неофициальное обновление [BuildPlanner от Vito Pistelli](https://github.com/viligante8/SpaceEngineers2BuildPlanner), лицензия MIT. Это не релиз автора оригинала; авторство и лицензии сохранены.

В разделе **Releases** скачайте **BuildPlanner-1.1.0-ru-en.3.zip**. Закройте игру, сохраните копию старой папки BuildPlanner и распакуйте папку из архива с заменой файлов. Все DLL должны лежать рядом. Параметры запуска показаны выше; пути замените своими. Одновременно загружайте только одну версию BuildPlanner.

Добавлены исправление очереди сварщика, защита зарегистрированных инструментов при Alt+N и русский/английский язык. В language.txt выберите auto (язык игры), ru или en и перезапустите игру.

Со сварщиком наведитесь на недостроенный блок до появления панели компонентов и нажмите ПКМ. Затем наведитесь на подключённый контейнер и нажмите N. Alt+N выгружает материалы; Shift+N заказывает производство; Shift+Alt+N очищает очередь.

Пользователь подтвердил работу предыдущей исправленной сборки в игре. Новый перевод прошёл отдельные проверки, но его отображение ещё нужно проверить в игре. Технический лог остаётся английским. Для диагностики приложите версию игры, шаги и `%APPDATA%\SpaceEngineers2\BuildPlanner\BuildPlanner.log`.

## Other projects / Другие проекты

- [Flight calculator / Калькулятор полёта](https://udedagame.github.io/)
- [AutoSorter downloads / Скачать AutoSorter](https://github.com/udedagame/SpaceEngineers2-AutoSorter/releases)

## Building / Сборка

Requires .NET SDK 9 and your own installed copy of the game:


The repository includes the original MIT license and third-party notices. Game DLLs are not distributed. README-UPSTREAM.md preserves the original project documentation for reference.
