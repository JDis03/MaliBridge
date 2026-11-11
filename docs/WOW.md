# World of Warcraft (Retail) through Battle.net

**English** · [Español](WOW.es.md) · [Back to the README](../README.md)

World of Warcraft Retail runs in DroidDeck Mali through the official **Battle.net** client, using
Blizzard's own **native ARM64** game executable (`Wow-ARM64.exe`) instead of the x64 one.

> **Status: tested on one device.** Everything below was measured on the device in the table. Other
> Mali devices are untested. Please report what you find (see [Getting help](../README.md#getting-help)).
> This is unofficial and not affiliated with Blizzard. Running a modified Wine layer under an
> anti-cheat-protected online game carries risk for your account; use it at your own judgement.

## What was tested

| | |
|---|---|
| Device | Xiaomi 15T (Dimensity 8400, Mali-G720 MC7), 11.6 GB RAM, Android 16 |
| App | DroidDeck Mali 0.5.5.3 |
| Compatibility tool | DroidDeck-Proton 11-12.1 |
| Game | World of Warcraft Retail, build 70888, native ARM64 client |
| DXVK | the ARM64X build from [JDis03/dxvk](https://github.com/JDis03/dxvk/releases/tag/v3.1.0-mali-arm64x), copied into the Battle.net prefix |
| Result | **54-57 fps** in game, launched from Battle.net |
| Memory | the game process held about 1.2-1.3 GB resident |

## Why the ARM64 client

Blizzard's Battle.net Agent is a 32-bit program. Under Wine it sees an ARM64 host, so it asks
Blizzard's servers for the **ARM64** build and installs `Wow-ARM64.exe`. You do not need a PC and you
do not copy any game files by hand: Battle.net's own **Scan and Repair** brings the install to the
current build.

Running the native client avoids the x64 emulation layer for the game itself, which is what keeps the
phone cooler and leaves more RAM free.

## Steps

1. Install DroidDeck Mali and open it (see the [install guide](../INSTALL.md)).
2. Start the **Battle.net** entry and sign in. Install World of Warcraft from the Battle.net window.
3. Wait for the download. The game is large (about 55 GB), so plan the storage first.
4. Press **Play**.

### What to expect the first time

- **The first Battle.net start is slow** (one to two minutes) while the 32-bit parts are translated
  and the Agent starts. Wait, do not close it.
- **Keep the phone awake and DroidDeck in the foreground** while it loads. DroidDeck pauses the Linux
  side when the app leaves the foreground or the screen turns off, and a paused game looks exactly like
  a hung one. Raise the screen timeout while you test.
- **Battle.net closes itself shortly after the game is up.** The Battle.net runner in DroidDeck closes
  the leftover Battle.net processes about 20 seconds after the game starts, to give the game their
  memory. This is intended. Open Battle.net again when you want to patch or switch games.
- If Battle.net sits on a login loop or never shows its window, close the session and start it again.

## Requirements and known limits

- The native ARM64 client needs a patched `ntdll.dll` in the Proton you use. Blizzard's executable maps
  its own clean copy of `ntdll.dll` and calls system services through it; stock Wine stubs crash
  there. The patch rewrites those stubs so they only depend on the thread block. The idea and the
  script come from [arusiasotto/wow-forever-droiddeck](https://github.com/arusiasotto/wow-forever-droiddeck)
  (see `deprecated/scripts/patch-ntdll-teb-table-stub.py` there).
- **The official v0.5.5.3 APK does not include this patch, nor the DXVK build above.** I checked: the APK
  installed on the test phone is byte-identical to that release (same SHA-256), and the patched
  `ntdll.dll` and the DXVK DLLs were added by hand afterwards. A stock install is therefore not
  supported for WoW yet.
- Memory: 8 GB is the floor for the app; for WoW, 12 GB devices are the comfortable case.
- Only Retail was tested. Other Blizzard games were not.

## Credits

- [arusiasotto](https://github.com/arusiasotto): the `ntdll.dll` stub idea and the WoW-on-DroidDeck
  groundwork this builds on.
- The DroidDeck authors, for the runtime and the Battle.net runner.
