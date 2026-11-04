# BuildPlanner 1.1.0-ru-en.3 — Русский / English

## Русский

Неофициальное обновление BuildPlanner на основе v1.1.0 Vito Pistelli (MIT), с исправлениями compat-fix.2 и tools-fix.1. Пользователь подтвердил, что предыдущая compat-fix.2 заработала в его игре. Эта сборка добавляет перевод; её отображение ещё нужно проверить в игре.

Переведены уведомления очереди, получения/нехватки компонентов, производства, выгрузки и ошибок, а также названия девяти действий в меню управления. Названия предметов и блоков берутся из игры/модов. Нативные элементы панели терминала переводятся самой игрой. Технический журнал остаётся на английском.

По умолчанию язык выбирается по текущей культуре игры: ru/ru-RU — русский, остальные — английский. Язык системы Windows не используется. Для принудительного выбора откройте language.txt рядом с BuildPlanner.dll:

- auto — язык игры;
- ru — русский;
- en — английский.

После смены языка или language.txt перезапустите игру: названия действий регистрируются при запуске, а уведомления в auto читают текущий язык игры.

### Установка

1. Закройте игру и сохраните копию папки D:\SE2Mods\BuildPlanner.
2. Замените её файлы содержимым папки BuildPlanner из архива. Должна загружаться только одна версия BuildPlanner. Параметры запуска прежние.
3. В language.txt оставьте auto либо впишите ru. Запустите игру.
4. Проверьте русские названия в Настройки → Управление → Строительство. Нажмите N при пустой очереди: ожидается «Планировщик: очередь пуста».
5. Проверьте добавление блока ПКМ со сварщиком, получение компонентов по N, производство и выгрузку Alt+N. Зарегистрированные инструменты должны оставаться у персонажа.

Для отката верните резервную копию. Сохранения и установленные файлы игры эта поставка не меняет.

## English

Unofficial bilingual update based on Vito Pistelli's MIT-licensed BuildPlanner v1.1.0. Includes the asynchronous tool-panel compatibility fix and registered-tool protection for Alt+N. The user confirmed the previous compatibility build works in their game; live display of this translation update still needs validation.

Translated plugin notifications and all nine control-action labels. Item/block names remain supplied by the game or their mods. Native terminal labels retain the game's localization. Diagnostic logs stay in English.

The bundled language.txt defaults to auto: Russian for ru cultures, English otherwise. To force a language, use ru or en. Restart the game after changing language to refresh registered control labels.

Close the game, back up your BuildPlanner folder, and replace it with the archive's BuildPlanner files. Keep your existing launch argument and load only one version. Test queueing, withdrawal, production, tool retention and the chosen language. Restore the backup to roll back.

This is not an upstream-author release. Original license and attribution are included. Built against Game2.Simulation 4.0.0.3165. Upstream: https://github.com/viligante8/SpaceEngineers2BuildPlanner

Validation / Проверки: 21 checks in forced Russian and 21 in forced English passed; 6 panel/hook checks and 28 actual deposit-filter checks passed. Release build succeeded, 0 errors; online NuGet audit unavailable (NU1900). No live-world translation test performed. Source build: dotnet build BuildPlanner/BuildPlanner.csproj -c Release -p:GameDir=YOUR_GAME2_FOLDER -p:Version=1.1.0-ru-en.3.
