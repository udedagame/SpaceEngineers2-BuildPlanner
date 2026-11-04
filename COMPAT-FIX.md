# BuildPlanner 1.1.0-compat-fix.2 — unofficial / неофициальная сборка

## Русский

Собрано против установленной Space Engineers 2 с Game2.Simulation 4.0.0.3165.

В журнале оригинал успешно загружается, команды N/Alt+N вызываются, но очередь остаётся пустой. Установлена причина, способная блокировать добавление сварщиком: UpdateUI и UpdateAreaUI в текущей игре — async void. Оригинальные перехватчики проверяют окно до завершения его открытия. Кроме того, CloseHUD вызывается при замене окна, а плагин ошибочно забывает инструмент.

Исправление: после обновления клиентской сессии проверяется фактический _screen ранее замеченных инструментов; активная цель восстанавливается только при открытой панели. Закрытая панель не удерживает правую кнопку мыши. Кандидаты хранятся слабыми ссылками. Проверка не применяется к серверной сессии. Включена прежняя защита зарегистрированных инструментов и оружия при выгрузке Alt+N.

Это вероятное исправление наблюдаемой проблемы очереди, а не доказательство, что все функции BuildPlanner работают в текущей игре. Живой игровой тест ещё требуется. Обновление не исправляет ситуацию, когда целью выбранной команды является проекция вместо грузового контейнера: у проекции нет инвентаря.

### Установка и проверка

1. Закройте игру. Сохраните копию D:\SE2Mods\BuildPlanner.
2. Замените файлы этой папки содержимым папки BuildPlanner из архива. Загружайте только одну сборку BuildPlanner. Параметры запуска прежние.
3. В логе %APPDATA%\SpaceEngineers2\BuildPlanner\BuildPlanner.log при запуске должна быть версия 1.1.0-compat-fix.2 и строка asynchronous tool panel refresh.
4. Возьмите сварщик, наведитесь на недостроенный блок или проекцию так, чтобы появилась панель нужных компонентов, и нажмите правую кнопку мыши. Ожидается добавление в очередь и уведомление. Проверьте обычный сварщик и AreaTools по отдельности.
5. Наведитесь на подключённый контейнер с нужными компонентами и нажмите N. Проверьте перенос и очередь. Уберите сварщик: правая кнопка должна вернуться игре.
6. Проверьте Alt+N: материалы выгружаются, зарегистрированные инструменты остаются в рюкзаке.

Если очередь по-прежнему пустая, сохраните лог сразу после правого клика и сообщите, каким сварщиком и на какой блок целились. Для отката верните резервную копию папки. Автоматически установленная версия не менялась.

## English

Unofficial compatibility patch based on Vito Pistelli's MIT-licensed BuildPlanner v1.1.0, commit d611e02be3e074317631ea71878ca292658cae77. Built against the installed game (Game2.Simulation 4.0.0.3165). This is not an upstream release.

Fixes a tool-panel timing issue: the game's UpdateUI/UpdateAreaUI methods are async void, and CloseHUD also runs during screen replacement. Entry/close hooks can miss the eventual open screen and disable queue input. The patch reconciles observed panels after the client session update using weak references. Closed panels release queue input. Includes the previous registered-tool/weapon protection for Alt+N deposit.

Close the game, back up your BuildPlanner folder, and replace its files with this archive's BuildPlanner folder. Keep the existing launch argument; never load original and patched versions simultaneously. Check for 1.1.0-compat-fix.2 in the startup log.

Test right-click queueing with a welder aimed at an unfinished block/projection while the component panel is visible. Then aim at a connected cargo container and press N. Test normal and modded welders, switching away from tools, and Alt+N tool retention. Live gameplay validation is pending. This patch does not give projection entities an inventory or prove all plugin functionality works.

### Verification

- Release build: 0 errors; NuGet vulnerability audit unavailable (NU1900).
- 6 isolated checks against game types: closed entry, late open, CloseHUD replacement, real close, repeated closed update, and installation of the Session.Update hook.
- 28 regression assertions against the actual patched deposit filter passed.
- No live world was loaded or modified. Existing installed plugin files were not changed.

Upstream: https://github.com/viligante8/SpaceEngineers2BuildPlanner
