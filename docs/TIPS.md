# Best settings and performance tips

[Back to the README](../README.md)


- **Proton:** you don't need to switch. The app picks a working DroidDeck-Proton by itself (the
  default is DroidDeck-Proton 11-11.10), and it doesn't move your games to a newer one on its own. Valve's own "Proton (ARM64)" and "Steam Linux Runtime"
  can't start inside DroidDeck. Games with a Linux version too (Portal 2, Half-Life 2 and others)
  need a DroidDeck-Proton set by hand.
- **Start with Safe mode (the default).** It is the most compatible setting. **Performance mode**
  (Safe mode: off) is an option under the Mali bridge button; on my tablets it was only 0-2% faster,
  and on weaker GPUs (Mali-G57, G68, G610) the logs I've read show no gain. Try it once a game works
  fine, and if anything breaks, switch back to Safe mode before reporting it.
- **DXVK: automatic** (the default) picks an older DXVK on phones whose GPU is too old for
  Proton's.
- **Steam menus: automatic** (the default) keeps Steam's menus from coming out black on older Mali
  GPUs. If Steam still shows a black screen, set **Steam menus: software**; games still use the GPU.
- **Games MaliBridge sets up by itself:** Don't Starve Together, Half-Life 2 and RimWorld on older
  phones, Indiana Jones and the Emperor's Tomb, Stray, SOMA and the two Amnesia games. You don't
  need launch options for them.

Safe mode, DXVK and Steam menus are in **Setup**, under the Mali bridge button. The
[install guide](../INSTALL.md#how-demanding-each-game-is) groups the games by how demanding they are.

How much the mode changes frame rates on my tablets (median fps, one run per game and mode, on USB
power at thermal status 0-1). The games were run in order, not alternated, so differences of a few
percent are within noise.

| Game (scene) | G720 safe | G720 performance | G925 safe | G925 performance |
|---|---|---|---|---|
| Half-Life 2 (train ride) | 74.1 | 75.9 | 93.7 | 93.7 |
| Subnautica (menu) | 62.0 | 62.3 | 81.3 | 81.5 |
| Stray (title) | 17.1 | 15.8 | 58.4 | 58.0 |
| Stardew Valley (title, 60 fps cap) | 60.0 | 60.0 | 60.0 | 60.0 |
| Risk of Rain 2 (title) | 35.6 | 35.8 | 56.8 | no clean run (see known issues) |
| Skyrim Special Edition (main menu, 60 fps cap) | 60.7 | 60.7 | not tested | not tested |

**Tips**

- **Lower the resolution if the game is slow.** Use the game's own resolution or render scale, and
  DroidDeck's Steam resolution setting (720p by default). This helps when the GPU is the limit,
  which is true for most games on weaker chips. It does nothing for games limited by the CPU
  (The Forest, ASTRONEER, Outer Wilds).
- **Set a frame limit.** In Steam's performance settings, pick 30 or 60 (or a number that divides
  your screen's refresh rate). An even 30 feels better than a wandering 40, and the phone stays
  cooler.
- **Keep the device cool.** Phones slow themselves down when they get hot; I saw frame rates drop
  after a while on both tablets. Take the case off, don't play while fast charging, and lower the
  frame limit for long sessions.
- **Close other apps first, and launch one game per session.** Android closes a game when it runs
  out of memory, and the heavier games need it: 8 GB is fine for light games, 12 GB or more for the
  big ones. A phone with little free memory runs the same game much slower.
- **Expect a slow first launch.** The first time you open Steam, and the first time you start each
  game, shaders are compiled and things stutter. When Steam shows "Processing Vulkan shaders", let
  it finish. It gets smoother the more you play.
- **Keep storage free.** You need 8-10 GB before any games, plus each game's size and a few
  hundred MB of cache that grows as you play.
- **If Steam keeps asking you to sign in or never gets past its loading screen,** sign in once,
  then switch Steam to offline mode (Steam menu, Go Offline). Installed games still start.
  Downloads and updates need you to be online.
- **If a game closes or looks wrong,** stop the session and use **Send logs to MaliBridge** (see
  [Getting help](../README.md#getting-help)). Launch the game once per session so the logs show one attempt.
- **Ask in the [Discord](https://discord.gg/9xC67qTjDq)** if a game doesn't run well; other
  players share their settings there.

### Seeing your fps

- **Steam's Performance Overlay** (in a Steam session): press the **⋯** button for Steam's quick menu, open
  **Performance** (the ⚡ tab) and set **Performance Overlay Level**: 1 shows the fps, 4 shows everything (CPU,
  memory, battery, a frame-time graph). It runs only while it's switched on. It works on any device, including
  Samsung tablets that hide their temperature sensors. Values the phone doesn't let apps read
  (often CPU temperature or GPU power) show as 0.
- **Performance HUD** (DroidDeck Mali's own): side menu → **Display** → **Performance HUD**. It shows the fps
  with the battery level, battery temperature, power draw in watts and Android's thermal state, from Android's
  own readings, so it works on any device. Power draw shows only on phones that report the battery's current,
  and the thermal state needs Android 10 or newer. In Steam sessions it starts off, since Steam's overlay is there.
