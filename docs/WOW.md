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
| App | DroidDeck Mali 0.5.6 (tested on 0.5.5.3 and 0.5.6) |
| Compatibility tool | DroidDeck-Proton 11-12.1 |
| Game | World of Warcraft Retail, native ARM64 client (`Wow-ARM64.exe`) |
| DXVK | the ARM64X build from [JDis03/dxvk](https://github.com/JDis03/dxvk/releases/tag/v3.1.1-mali-arm64x) (`v3.1.1-mali-arm64x`) |
| Result | **~59 fps** in the 3D login/menu scene; **~27–28 fps** flat in-world (Westfall / Elwynn Forest, native 1280×720, `vsync=0`, MaliBridge `performance` mode) |
| Memory | the game process held about 1.2–1.3 GB resident |

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

- **The `ntdll.dll` fix is already in DroidDeck-Proton, nothing to patch.** Blizzard's executable maps
  its own clean copy of `ntdll.dll` and calls system services through it, and stock Wine stubs crash
  there. DroidDeck-Proton carries the fix since **11-11.3** (release notes: "World of Warcraft on
  ARM64EC", by [arusiasotto](https://github.com/arusiasotto)), and the app's default, 11-11.10, has it:
  I checked that its `ntdll.dll` contains the 258 rewritten stubs. Older Proton builds do not.
- **Comparison vs DroidDeck's bundled DXVK:** Measured on Mali-G720 MC7 (1280×720, `vsync=0`, `performance` mode), `JDis03/dxvk` cuts `vkGetPhysicalDeviceMemoryProperties2` polling from **1,042 calls/10 s** on bundled DXVK down to **27–36 calls/10 s**, and adds `preferTransferClears` (~0.7 ms/frame faster in Westfall). Note that `droiddeck-proton-run` restores the bundled DXVK on session start from `desired.tsv` unless launched directly or packaged into the runtime.
- **In-world GPU bound:** At native 1280×720 in-world, Mali-G720 MC7 is hardware-saturated (~704 MHz, heavy compute ASSAO / Volume Fog / Clustered Lighting / FFT water shaders + fragment bandwidth). Lowering `RenderScale` (e.g. `0.5`–`0.7`) increases FPS at the cost of 3D sharpness.
- Memory: 8 GB is the floor for the app; for WoW, 12 GB devices are the comfortable case.
- Only Retail was tested. Other Blizzard games were not.

## Credits

- [arusiasotto](https://github.com/arusiasotto): the `ntdll.dll` stub idea and the WoW-on-DroidDeck
  groundwork this builds on.
- The DroidDeck authors, for the runtime and the Battle.net runner.
