# Does my device work?

[Back to the README](../README.md)


You need an Arm Mali GPU (Immortalis is Mali too); Steam also starts on some Samsung Xclipse GPUs, see the table. Find your device below. Not sure which chip you
have? It's under Settings → About phone (or About tablet), or in an app like CPU-Z, which shows the
GPU too.

What the labels mean:

- **Works**: Steam starts and games run. A player reported it, or I tested it.
- **Works, with notes**: it runs, with a limit named in the notes.

Everything except the two tablets comes from player reports; I haven't tested those devices myself.
If your device has the same GPU as one below, it will probably behave the same, but phone makers
ship different driver versions, so a report is still useful.

| GPU | Device (chip) | Driver | Status | Notes |
|---|---|---|---|---|
| Mali-G57 | Redmi Note 12S (Helio G96) |  | **Works, with notes** | [Player report](https://github.com/ASEbrahim/MaliBridge/discussions/2#discussioncomment-19128201): Steam works first try; lighter games run (DDNet, YOMI Hustle, Space Menace, Death Road to Canada) |
| Mali-G57 | Xiaomi phone (MediaTek, G57 MC2) | r54p1 | **Works, with notes** | Left 4 Dead 2 at 17-19 fps |
| Mali-G57 | Samsung Galaxy F15 | r38p1 | **Works** | Steam opens, player confirmed |
| Mali-G68 | Samsung Galaxy A16 5G | r38p1 | **Works** | Steam opens, player confirmed |
| Mali-G57 | Samsung Galaxy A07 (Helio G99) |  | **Works** | Tap Ninja about 59 fps |
| Mali-G68 | Samsung Galaxy A54 | r38p1 | **Works, with notes** | Steam opens; menus are slow |
| Mali-G68 | Samsung Galaxy A34 5G (Dimensity 1080) |  | **Works** | Star Wars Republic Commando playable, about 30 fps |
| Mali-G76 | Samsung Galaxy S10+ phone (Exynos 9820) | r38p1 beta | **Works, with notes** | Steam opens and a game ran, slowly |
| Mali-G77 | Retroid Pocket 4 Pro (Dimensity 1100) | r32p1 | **Works, with notes** | Steam and Big Picture run; some screens flicker |
| Mali-G77 | Huawei Nova 7 (Kirin 985) |  | **Works, with notes** | Slay the Spire 1 and 2 run; one game says "Direct3D isn't supported" |
| Mali-G78 | Samsung Galaxy S21 | r38p0 | **Works** | Muse Dash about 53 fps |
| Mali-G610 | Xiaomi 12T (Dimensity 8100-Ultra) | r32p1 | **Works, with notes** | [Player report](https://github.com/ASEbrahim/MaliBridge/issues/34#issuecomment-6570084449): Steam runs and Half-Life plays |
| Mali-G615 | POCO X6 Pro (Dimensity 8300-Ultra) |  | **Works, with notes** | [Player report](https://github.com/Droid-Deck/DroidDeck/issues/218#issuecomment-6311114838): Lighter games run (GTA San Andreas, Burnout Paradise about 30 fps); heavier ones 12-14 fps |
| Mali-G615 | Dimensity 8350 phone |  | **Works** | [Player report](https://github.com/Droid-Deck/DroidDeck/issues/218#issuecomment-6322050101): Rivals of Aether about 55 fps |
| Mali-G615 | Xiaomi phone (G615 MC2) | r44p1 | **Works** | Final Fantasy Resonance about 46 fps |
| Mali-G615 | Infinix phone (G615 MC6, 11.5 GB RAM) | r44p1 | **Works, with notes** | Tekken 7 9-30 fps; the phone ran out of free memory |
| Mali-G710 | OnePlus Ace 2V (Dimensity 9000) | r32p1 | **Works, with notes** | [Player report](https://github.com/Droid-Deck/DroidDeck/issues/218#issuecomment-6335790759): RimWorld plays for 1-2 hours; Half-Life 2 starts. Needs DXVK 1.10.3 picked by hand |
| Immortalis-G715 | Xiaomi 13T Pro (Dimensity 9200+) | r38p1 | **Works, with notes** | [Player report](https://github.com/ASEbrahim/MaliBridge/discussions/2#discussioncomment-19352669): Dead Cells 39-47 fps, BALL x PIT about 35 fps, Hades about 17 fps; Steam's menus 20-25 fps |
| Immortalis-G715 | vivo X90s (Dimensity 9200+) | r38p1 | **Works, with notes** | [Player report](https://github.com/ASEbrahim/MaliBridge/issues/51#issuecomment-6571868319): Steam's black screen is gone since v0.5.5; playable but a bit laggy |
| Immortalis-G715 | Pixel 8 / 8 Pro (Tensor G3) | r54 | **Works** | [Player reports](https://github.com/Droid-Deck/DroidDeck/issues/218#issuecomment-6306332804): Cuphead 60-100 fps, Hades 30-60, Dishonored 15-25 |
| Immortalis-G715 | Pixel 9 (Tensor G4) | r54p3 | **Works, with notes** | [Player report](https://github.com/Droid-Deck/DroidDeck/pull/517#issuecomment-6220985381): Steam starts; games not confirmed yet |
| Immortalis-G720 | Samsung Galaxy Tab S10+ (Dimensity 9300+) | r44p1 | **Works** | Tested in depth |
| Immortalis-G720 | vivo X100 Pro (Dimensity 9300) |  | **Works, with notes** | [Player report](https://github.com/ASEbrahim/MaliBridge/discussions/2#discussioncomment-19193192): Cuphead about 100 fps; Steam's menus about 15 fps with a white flash; Forza Horizon 4 closes when going into the game |
| Immortalis-G720 | realme Neo7 (Dimensity 9300+) | r44p1 | **Works** | [Player report](https://github.com/ASEbrahim/MaliBridge/issues/5): Stardew Valley about 59 fps, Balatro 55-72 fps |
| Mali-G720 | Xiaomi 15T (Dimensity 8400) |  | **Works, with notes** | World of Warcraft Retail (native ARM64 client, Battle.net) 54-57 fps; tested on this one device, see [the WoW guide](WOW.md) |
| Immortalis-G720 | Xiaomi 14T Pro (Dimensity 9300+) | r44p1 | **Works, with notes** | [Player report](https://github.com/ASEbrahim/MaliBridge/discussions/2#discussioncomment-19146763): Steam, controller and downloads work; Alan Wake 20-50 fps on Low; some graphics glitches that need a game restart |
| Mali-G720 | POCO X8 Pro (Dimensity 8500) | r49p1 | **Works, with notes** | [Player reports](https://github.com/ASEbrahim/MaliBridge/issues/9#issuecomment-6328655497): Indiana Jones and the Emperor's Tomb about 30 fps; Hob has freezes |
| Mali-G720 | POCO X7 Pro (Dimensity 8400-Ultra) |  | **Works** | [Player report](https://github.com/ASEbrahim/MaliBridge/issues/23): Lighter games run (Stardew Valley, Rain World, Tukoni: Forest Keepers and more); [Darksiders Genesis 23-27 fps on Low](https://github.com/ASEbrahim/MaliBridge/issues/62) |
| Immortalis-G925 | Samsung Galaxy Tab S11 Ultra (Dimensity 9400) | r49p1 | **Works** | Tested in depth |
| Immortalis-G925 | vivo X200 (Dimensity 9400) |  | **Works** | [Player report](https://github.com/Droid-Deck/DroidDeck/issues/218#issuecomment-6314012693): Euro Truck Simulator 2 about 20 fps, Goat Simulator about 35 fps |
| Mali-G925 | Xiaomi Pad 7S Pro (XRing O1) | r49p1 | **Works** | Steam runs |
| Immortalis-G925 | iQOO Z10 Turbo Plus |  | **Works, with notes** | Skyrim about 61 fps; the on-screen controller did not respond in the menu |
| Mali-G1-Ultra | Xiaomi 17T Pro (Dimensity 9500) | r54p1 | **Works, with notes** | [Player report](https://github.com/ASEbrahim/MaliBridge/discussions/2#discussioncomment-19149991): 20+ games run (Hollow Knight, Hades, Dead Cells, Celeste); green-square texture artifacts in some games |
| Mali-G1-Ultra | OPPO Find X9 Pro (Dimensity 9500) | r54p1 | **Works, with notes** | [Player reports](https://github.com/Droid-Deck/DroidDeck/issues/218#issuecomment-6312412336): Balatro, Slay the Spire; green-square texture artifacts in some games |
| Mali-G1-Ultra | Redmi K90 Max (Dimensity 9500) | r54p1 | **Works, with notes** | [Player report](https://github.com/Droid-Deck/DroidDeck/issues/218#issuecomment-6330586020): Little Nightmares and II about 10 fps (corrected by the player); Reshaping Creatures 5-9 fps |
| Mali-G1-Ultra | vivo X300 (Dimensity 9500) | r54p1 | **Works, with notes** | Mad Max steady 60 fps, Hollow Knight about 60 fps; Steam menus are slow |
| Mali-G1-Ultra | Samsung Galaxy Tab S12+ | r54p1 | **Works, with notes** | Batman: Arkham Asylum runs; in one cutscene lights show through walls |
| Mali-G2-Ultra-NX | Xiaomi 18 Fold (XRing O3) | r56p0 | **Works** | [Player reports](https://github.com/ASEbrahim/MaliBridge/issues/7): Self-test 13/13, Steam, Brotato about 77 fps |
| Mali-G2-Ultra-NX | Xiaomi Pad 9 Pro Max (XRing O3) |  | **Works** | [Player report](https://github.com/ASEbrahim/MaliBridge/discussions/2#discussioncomment-19136786): Human Fall Flat works, Portal 2 40-50 fps at 1080p; Titanfall 2 does not start yet |
| Xclipse 530 | Samsung Galaxy A55 |  | **Works, with notes** | [Player report](https://github.com/ASEbrahim/MaliBridge/issues/27): Steam starts; games not confirmed yet |

Device not listed, or something doesn't work? Tap **Send logs to MaliBridge** in the app and post the code in the [Discord](https://discord.gg/9xC67qTjDq).

More device reports and tests from players are in the Discord, along with test builds, help and extras.

**Help wanted: not tested yet.** Reports from these would help the most:

| Chip | GPU | Example devices |
|---|---|---|
| Dimensity 9300 / 9300+ (other devices) | Immortalis-G720 MC12 | OPPO Find X7 |
| Dimensity 9400 / 9400+ (other devices) | Immortalis-G925 MC12 | OPPO Find X8 |
| Dimensity 7300 and similar | Mali-G615 / G610 | many mid-range phones (smaller GPUs: expect light games only) |
| Exynos 1280 | Mali-G68 | Galaxy A53 |

**Not Mali:** Snapdragon chips have Adreno GPUs (use the official DroidDeck). Samsung's newer Exynos
chips have Xclipse GPUs, and some of those phones work (the Galaxy A55 is in the table). On Samsung
phones updated to Android 17 (One UI 9), Steam stayed on its loading screen; v0.5.5.3 should fix that.
In my own tests with v0.5.5.3, Steam reached its sign-in screen on a Galaxy S26 FE (Android 17) and a
Galaxy A56. Players with the Galaxy S24+ (Xclipse 940, [#43](https://github.com/ASEbrahim/MaliBridge/issues/43))
and A56 (Xclipse 540, [#29](https://github.com/ASEbrahim/MaliBridge/issues/29)) haven't confirmed it yet.

On a device that isn't in the table, it's still a test: it depends on the GPU and its driver.
Logs from your device help a lot (see [Getting help](../README.md#getting-help)).
