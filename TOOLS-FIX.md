# BuildPlanner 1.1.0 — tools-fix.1 (unofficial patch)

## Русский

Исправление для выгрузки рюкзака по Alt+N. Зарегистрированные игровые инструменты и оружие остаются у персонажа, даже если мод пометил предмет как компонент, материал или руду. Проверяются ItemPrefabs и GunItems из ToolsConfiguration после загрузки модов. Инструменты можно перекладывать вручную через обычный интерфейс игры.

Это отдельная неофициальная сборка BuildPlanner от Vito Pistelli на основе тега v1.1.0, commit d611e02be3e074317631ea71878ca292658cae77. Изменена только проверка IsBuildMaterial в BuildPlannerController.cs; лицензия MIT и авторство сохранены. Это не обновление от автора BuildPlanner.

Установка: закройте игру, сохраните копию папки D:\SE2Mods\BuildPlanner, затем замените её файлы содержимым папки BuildPlanner из этого архива. Параметры запуска остаются прежними. В BuildPlanner.log первая строка версии должна содержать tools-fix.1. Для отката верните сохранённую папку. Не включайте одновременно оригинальный и исправленный BuildPlanner.

Проверка в игре ещё требуется: оставьте модовые инструменты в рюкзаке вместе с обычными материалами, нажмите Alt+N у контейнера. Материалы должны выгрузиться, инструменты — остаться. При ошибке приложите лог. AutoSorter сам не выполняет Alt+N: одного его обновления недостаточно для исправления выгрузки BuildPlanner.

## English

Unofficial BuildPlanner v1.1.0 patch for Alt+N backpack deposit. Registered hand tools and weapons are excluded before checking ore/material/component flags. Items can still be moved manually using the normal inventory UI. Tool registration is read from the loaded game's ToolsConfiguration, including mods.

Based on Vito Pistelli's MIT-licensed BuildPlanner v1.1.0 (d611e02be3e074317631ea71878ca292658cae77). Only the IsBuildMaterial filter in BuildPlannerController.cs was changed. This is not an upstream author release.

Close the game, back up your existing BuildPlanner folder, and replace its files with the BuildPlanner folder in this archive. Keep your current launch option. The startup version in BuildPlanner.log should include tools-fix.1. Restore the backup to roll back. Do not load the original and patched plugins simultaneously.

Live validation is pending. Test Alt+N with modded tools and ordinary materials in your backpack: materials should deposit and tools should stay. AutoSorter does not own the Alt+N operation; its update alone cannot fix BuildPlanner's deposit behavior.

Upstream: https://github.com/viligante8/SpaceEngineers2BuildPlanner

Validation: Release build succeeded; 28 assertions against the actual patched filter and game types passed, including the three AreaTools item GUIDs with ore/material/component/all flags, registered guns, and ordinary build inputs. No game world was loaded. NuGet's online vulnerability audit was unavailable (NU1900).
