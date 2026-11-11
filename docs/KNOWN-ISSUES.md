# Known issues

[Back to the README](../README.md)


- **OpenGL games on the Galaxy Tab S9 FE** (Mali-G68) can show broken textures, for example Euro
  Truck Simulator 2 in OpenGL mode. Being looked into. On the Galaxy A16, A54, F15, Tab S10 Lite and
  Anbernic RG556, OpenGL games are not tested yet.
- **Short freezes while moving** in some games that stream their textures in as you walk (Dark
  Souls III, Hob). v0.5.5.3 writes down what each freeze was waiting on, so logs from a game that
  freezes help.
- **Steam's menu closing over and over** on some Xiaomi, POCO and vivo phones, and games going back
  to Steam on the POCO X8 Pro ([#55](https://github.com/ASEbrahim/MaliBridge/issues/55)). v0.5.5.3
  writes down why it closes, so send logs right after it happens.
- **Games closing when the phone runs low on memory.** v0.5.5.3 might help in some games. Close
  other apps first and launch one game per session.
- **Some Huawei phones on Android 10** (P30, P40 Pro) can stop at Steam setup. v0.5.5.3 might help;
  if it still stops, logs help.
- **Steam's menus on some vivo and iQOO phones** can run at about 15 fps, with a white flash when a menu opens.
  v0.5.5 has a change for this that is not checked on a phone yet. If you have one of these phones, logs help.
- **The Witcher 3 (DX12) on the Mali-G925** runs at about 29 fps, but one session froze in a cutscene.
  Being looked into.
- **Bright Memory: Infinite on the Mali-G720** barely runs in DirectX 11, and its DirectX 12 mode
  doesn't run.
- **Deep Rock Galactic on the Mali-G925** can freeze after loading into the Space Rig. Being worked on.
- **Stray and ENDER LILIES on the Mali-G925** run with plain colours instead of their own colour
  grading (Poppy Playtime and ASTRONEER too). Being worked on.
- **Stray with `-dx12`** closes about 60 s after starting on the G925. The default (DX11) is fine.
- **Risk of Rain 2**: one performance-mode launch on the G925 showed no picture for about 2 minutes
  on its title load, then went on. It did not happen again.
- **The Steam window on the Mali-G925** can feel slow. Games are not affected.
- **Green-square texture artifacts** in some games on Dimensity 9500 phones (Mali-G1-Ultra). Being
  looked into.
- **Just Cause 2, Mafia II and Space Marine** can stay on Steam's "Updating executable" step: Steam's
  copy protection check takes too long inside DroidDeck.
- **Resident Evil 2** can show "Failed to send play data to RE NET" on its menu. Press OK: the game
  plays normally. Only Capcom's online play statistics are affected.
- **Dark Souls III on slower devices** can say "Frame rate unsuitable for online play" and return to
  the title. That is the game's own rule below about 20 fps: play it offline there.
- **Outer Wilds, ASTRONEER and The Forest** are limited by the CPU on the G925, so lowering the
  resolution or settings helps little.

## What's next

- Fixing the short freezes while moving (Dark Souls III, Hob).
- Better performance optimizations.
- Smoother first visits to new areas.
- The games limited by the CPU (The Forest, ASTRONEER, Outer Wilds) and Just Cause 2.
- DirectX 12: The Witcher 3's cutscene freeze, Stray in DX12, Elden Ring, Bright Memory.
- Phones where Steam's menus close over and over or stay black.
- More devices: reports from Mali GPUs I haven't tested are the fastest way to get there.
