# WS Tools: a Warhammer Survivors mod

Cheat and quality-of-life options for Warhammer Survivors, built into the game's own menus. This repo hosts the release downloads only. The mod is also on Nexus Mods.

**[Download the latest release](../../releases/latest)**. No account needed. From the Assets list, pick one:

| File | What it is |
|---|---|
| `WarhammerSurvivorsMods_Standalone-<version>.zip` | **Easiest.** BepInEx + WS Tools in one zip: extract into the game folder and play. |
| `WarhammerSurvivorsMods-<version>.zip` | WS Tools only, if you already have BepInEx 6.0.0-be.793. |
| `BepInEx_for_WarhammerSurvivors_6.0.0-be.793.zip` | BepInEx only (the mod loader), console window off. |

## What it does

- **Main menu:** a Mods button (or the normal Options button) opens Options with a new MODS tab: +1000 coins, skip Enhancements after a run, and one UNLOCK button each for all characters, weapons, stages, relics and arcanas.
- **Character select:** locked characters show their unlock progress ("Progress: 88 / 100 (88%)").
- **Objectives and boss keys:** stage select, hero select and the run show what is still left to unlock. A minute-25 boss can only be hurt with its key weapon: stage select shows which one, and level-up marks it.
- **In a run:** the pause menu gets a MODS tab next to Map, Statistics, Armoury, Emperor's Tarot and Options (Q/E or LB/RB cycle through it; D-pad and A work inside it). An F1 panel in the game's own style (40K or Age of Sigmar look, collapsible with the mouse) and hotkeys give quick access to the same options. Every option can have a hotkey: set them in Options > MODS in the main menu.

Everything is optional, and nothing in the game files is modified.

### In a run

- God mode (F2), heal (F3), +1 level (F4), kill player (Delete), +1000 gold (Insert), +10 rerolls / skips / banishes.
- Spawn a miniboss with a chest (Home, the stage's own minibosses first), the stage's boss (End), or a chest next to you (Page Up).
- **Nuke** (Page Down): kills everything on screen, your drops stay on the floor. 40K fires a Storm Eagle Rocket.
- **Storm Eagle Rocket keeps drops:** the rocket blast no longer erases chests and items.
- Multipliers: gold and XP (x1-x10), luck (x1-x50), magnet / pickup range (x1-x25, with a circle that shows the pull area), damage (x1-x100). Enemy speed x1 / 0.75 / 0.5 / 0.25 (F9).
- **Weapon and passive slots:** 1 to 12 or no limit, mid-run (F7/F8 weapons, F5/F6 passives).
- Game speed (F10), move speed x0.5 to x6.
- Weapon effects opacity 100% down to 0%. Only your own weapon visuals fade; enemy shots stay fully visible.
- About 35 ranged weapons aim at the nearest enemy, the mouse cursor, or the right analog stick . With a gamepad, R3 blinks toward the aim.
- Chests: faster opening, auto open, auto accept, **always max** (5 prizes), chest SFX on / off (the stage music keeps playing).
- **Minimap** (M, or L3): stage items, places, chests and drops around you, in the corner the F1 panel does not use.
- Mouse movement: point and click (with a destination ring), the game's drag, or off.
- Teleport to the mouse cursor (right click), in play or on the pause-menu Map tab.
- **Twin-Tailed City:** a label under the timer shows your area (Ghyran / Aqshan) and the next area boss.
- **Auto Redeploy:** a Redeploy you have left is used automatically when you die.
- Hide the grey side shade, show an FPS counter, F1 panel left or right (F11) with auto-hide while you play and on the results / Enhancements screens.

### General

- Skips the Auroch Digital / Games Workshop logos, the health warning and the "Press any button" screen.
- Gamepad in the main menu: Select opens Mods.

All settings are remembered between runs and game restarts. The mod reacts to the game's own events instead of scanning the scene: about 0.3 ms per frame on PC, under 1 ms on Steam Deck.

## Installation

### Standalone (easiest)

1. Find the game folder: Steam > right-click Warhammer Survivors > Manage > Browse local files.
2. Extract `WarhammerSurvivorsMods_Standalone-<version>.zip` into that folder, keeping the folders.
3. Start the game from Steam. The first start takes a minute or two while BepInEx builds its files. If the game goes straight to the main menu, the mod is running.

### Mod only

1. Install **BepInEx 6.0.0-be.793**, exactly this file: <https://builds.bepinex.dev/projects/bepinex_be/793/BepInEx-Unity.IL2CPP-win-x64-6.0.0-be.793%2Bdbc82f0.zip>
   Extract it into the game folder, next to `WarhammerSurvivors.exe`. You should then have a `dotnet` folder and a `BepInEx` folder there.
2. Start the game once and close it.
3. Extract `WarhammerSurvivorsMods-<version>.zip` into the same folder, so you end up with:
   ```
   BepInEx\plugins\SkipWarning.dll
   BepInEx\plugins\WSTools.dll
   BepInEx\plugins\WSLogic\WSLogic.dll
   ```
4. Start the game from Steam.

**Steam Deck / Linux (Proton):** install in Desktop Mode, then set the game's Launch Options to:
```
WINEDLLOVERRIDES="winhttp=n,b" %command%
```

- **Updating:** extract over the old files.
- **Uninstalling:** delete the three plugin files. To remove BepInEx entirely, also delete `winhttp.dll` from the game folder.

> **Unlock all is permanent and written to your save immediately. Back up your save first.**
> The save is at `<Steam>\userdata\<your id>\3669620\remote\SaveData` (Steam Cloud).

## Troubleshooting

- **ESC doesn't open the pause menu:** check that no gamepad is switched on. The game follows the last used controller.
- **Low FPS with lots of enemies:** turn off **Damage Numbers** and turn on **Reduce Flashing VFX** in the game's Options, and lower the weapon effects opacity.
- **Windows Smart App Control** can block the DLLs that BepInEx generates (for example `BepInEx\interop\PhaserPort.dll`). The mod detects this and turns its in-run features off so your frame rate stays normal. The only fix is to turn Smart App Control off (Windows Security > App & browser control > Smart App Control settings). On many Windows 11 versions it can't be turned back on without reinstalling Windows.
- **After a game update:** delete `BepInEx\interop` and `BepInEx\cache` and start the game again. The mod itself may also need an update.

## Verifying the download

Each release includes `SHA256SUMS.txt`. In PowerShell, compare its value with the output of:
```
Get-FileHash <file name>.zip
```

## Notes

- Warhammer Survivors on Steam, tested on the Unity 6000.0.74f1 build.
- BepInEx is open source under the LGPL-2.1 license: <https://github.com/BepInEx/BepInEx>. The packages contain the unmodified official build #793.
- Cheats can affect your own progress or achievements, so back up your save.

---

Unofficial fan mod. Not affiliated with or endorsed by Auroch Digital or Games Workshop. No game files are included in this repo.
