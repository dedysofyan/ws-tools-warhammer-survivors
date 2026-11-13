# WS Tools: a Warhammer Survivors mod

Cheat and quality-of-life options for Warhammer Survivors, built into the game's own menus. This repo hosts the release downloads only. The mod is also on Nexus Mods.

**[Download the latest release](../../releases/latest)**: get `WarhammerSurvivorsMods-<version>.zip` from the Assets list. No account needed.

## What it does

- **Main menu:** a Mods button (or the normal Options button) opens Options with a new MODS tab: unlock all characters, weapons, stages, relics and arcanas, plus +1000 coins.
- **In a run:** the pause menu gets a MODS tab next to Map, Statistics, Armoury, Emperor's Tarot and Options. Q/E cycle through it like any other tab. A small F1 panel and hotkeys give quick access to the same options.
- It also:
  - skips the health-warning and "press to start" screens
  - can hide the grey side shade
  - can make your own weapon effects see-through
  - makes bolters aim at the nearest enemy
  - can open and accept chests for you
  - can show an FPS counter

Everything is optional, and nothing in the game files is modified.

### In a run (pause menu MODS tab, F1 panel, hotkeys)

- God mode (F2), heal (F3), +1 level (F4), kill player (Delete), +1000 gold (Insert).
- Spawn a miniboss of the faction on screen, with a normal chest (Home). Spawn a boss of that faction (End).
- Gold and XP multipliers (x1 / x2 / x5 / x10).
- Luck multiplier x1 to x50 (the Chance stat: pickup drops and chest size).
- Game speed (F10), move speed x0.5 to x6 (F5).
- Weapon effects opacity 100 / 75 / 50 / 30 / 15 % (F6). Only your own weapon visuals fade; enemy shots stay fully visible.
- Bolters aim at the nearest enemy (Boltgun, Heavy Bolter, Storm Bolter).
- Chests: faster opening x1 / x2 / x4 / x8 (F7), auto open, auto accept, and **always max** (5 prizes).
- Teleport to the cursor on the pause-menu Map tab (F8).
- Hide the grey side shade on the gameplay screen.

All settings are remembered between runs and game restarts.

## Installation

1. Install **BepInEx 6.0.0-be.793** (Unity IL2CPP, Windows x64) from the official build server: <https://builds.bepinex.dev/projects/bepinex_be>
   - Extract it into the game folder, next to `WarhammerSurvivors.exe`.
   - Its zip contains a `dotnet` folder. If yours doesn't, you have the wrong build.
2. Run the game once and close it. BepInEx generates its interop files on the first run. This takes a minute or two and needs internet.
3. Extract this mod's zip into the same game folder, so you end up with:
   ```
   BepInEx\plugins\SkipWarning.dll
   BepInEx\plugins\WSTools.dll
   BepInEx\plugins\WSLogic\WSLogic.dll
   ```
4. Launch the game from Steam as usual. If the health warning is skipped, the mod is running.

**Steam Deck / Linux (Proton):** install in Desktop Mode, then set the game's Launch Options to:
```
WINEDLLOVERRIDES="winhttp=n,b" %command%
```

- **Updating:** extract over the old files.
- **Uninstalling:** delete the three files above. To remove BepInEx entirely, also delete `winhttp.dll` from the game folder.

> **Unlock all is permanent and written to your save immediately. Back up your save first.**
> The save is at `<Steam>\userdata\<your id>\3669620\remote\SaveData` (Steam Cloud).

## Windows Smart App Control

Smart App Control can block the DLLs that BepInEx generates on your PC (for example `BepInEx\interop\PhaserPort.dll`). When that happens, the in-run features can't work.

Since 0.5.1 the mod detects this. It turns its in-run features off so your frame rate stays normal, and shows a message.

The only fix is to turn Smart App Control off (Windows Security > App & browser control > Smart App Control settings). Be careful: on many Windows 11 versions it can't be turned back on without reinstalling Windows.

## Performance tip

With lots of enemies on screen, turn off **Damage Numbers** and turn on **Reduce Flashing VFX** in the game's Options. Use the mod's Show FPS option to see the difference.

## Verifying the download

Each release includes `SHA256SUMS.txt`. In PowerShell, compare its value with the output of:
```
Get-FileHash WarhammerSurvivorsMods-<version>.zip
```

## Requirements and notes

- Warhammer Survivors on Steam (tested on the Unity 6000.0.74f1 build).
- BepInEx 6.0.0-be.793, Unity IL2CPP, Windows x64 (not included). Other BepInEx builds were not tested.
- Single-player only. Co-op was not tested.
- Cheats can affect your own progress or achievements, so back up your save.

---

Unofficial fan mod. Not affiliated with or endorsed by Auroch Digital or Games Workshop. No game files are included in this repo.
