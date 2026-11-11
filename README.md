<h1 align="center">MaliBridge</h1>

<p align="center"><b>Play Steam and PC games on Android phones and tablets with a Mali GPU</b><br>
MediaTek Dimensity, Google Tensor, Xiaomi XRing, older Samsung Exynos and other Arm Mali / Immortalis chips.<br>
It runs on the device's own driver, with no custom GPU driver to install.</p>

<p align="center">
  <a href="https://github.com/ASEbrahim/MaliBridge/releases/latest"><img alt="Download" src="https://img.shields.io/badge/Download-latest%20release-2ea44f?style=for-the-badge&logo=android&logoColor=white"></a>
  <a href="https://github.com/ASEbrahim/MaliBridge/releases/latest"><img alt="Latest version" src="https://img.shields.io/github/v/release/ASEbrahim/MaliBridge?style=for-the-badge&label=version&color=orange"></a>
  <a href="https://github.com/ASEbrahim/MaliBridge/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/ASEbrahim/MaliBridge/total?style=for-the-badge&label=downloads&color=blue"></a>
  <a href="https://discord.gg/9xC67qTjDq"><img alt="Discord" src="https://img.shields.io/badge/Discord-join-5865F2?style=for-the-badge&logo=discord&logoColor=white"></a>
  <a href="https://ko-fi.com/asebrahim"><img alt="Ko-fi" src="https://img.shields.io/badge/Ko--fi-support-FF5E5B?style=for-the-badge&logo=ko-fi&logoColor=white"></a>
  <a href="https://www.patreon.com/c/ASEbrahim"><img alt="Patreon" src="https://img.shields.io/badge/Patreon-support-F96854?style=for-the-badge&logo=patreon&logoColor=white"></a>
</p>

<p align="center">
  <a href="https://github.com/ASEbrahim/MaliBridge/releases/latest"><b>Download</b></a> ·
  <a href="INSTALL.md"><b>Install guide</b></a> ·
  <a href="docs/DEVICES.md"><b>Does my device work?</b></a> ·
  <a href="docs/GAMES.md"><b>Games that run</b></a> ·
  <a href="docs/WOW.md"><b>World of Warcraft</b></a> ·
  <a href="#getting-help"><b>Getting help</b></a> ·
  <a href="INSTALL.md#faq"><b>FAQ</b></a> ·
  <a href="README.es.md"><b>Español</b></a> ·
  <a href="README.zh-CN.md"><b>中文说明</b></a>
</p>

<p align="center"><img src="docs/img/ingame-v055.jpg" alt="Resident Evil 2, Risk of Rain Returns and Celeste running with MaliBridge" width="900"><br>
<i>In game on a Galaxy Tab S11 Ultra with v0.5.4.</i></p>

> [!IMPORTANT]
> Get DroidDeck Mali from this page's [Releases](https://github.com/ASEbrahim/MaliBridge/releases). Copies on other sites
> can be old or changed. Official [DroidDeck](https://github.com/Droid-Deck/DroidDeck) doesn't include MaliBridge yet;
> once it does, its releases are fine too.

## What is it?

MaliBridge lets PC games in **DroidDeck** use your phone's own **Arm Mali** GPU driver. It runs inside
**DroidDeck Mali**, a build of DroidDeck (the app that runs the Steam client and PC games on Android).
It is free, and there is no custom GPU driver to install.

**Current version: v0.5.5.3**, built on DroidDeck 0.6.9.

On a Galaxy Tab S10+ (Mali-G720) and a Galaxy Tab S11 Ultra (Mali-G925), 36 of the games I tested are
playable or better, for example Half-Life 2 at about 94 fps, Hollow Knight: Silksong, Stardew Valley and
Dark Souls Remastered. Players have sent reports from 38 other Mali devices. The tables cover 98 games.

## Do I need this?

| Your phone's GPU | Use |
|---|---|
| **Arm Mali / Immortalis** (MediaTek Dimensity, Google Tensor, Xiaomi XRing, older Exynos) | **DroidDeck Mali**, this project |
| **Adreno** (Snapdragon) | the official [DroidDeck](https://github.com/Droid-Deck/DroidDeck) |
| Samsung **Xclipse** | some work; see the [device table](docs/DEVICES.md) |

Not sure what GPU you have? It is under Settings → About phone, or in an app like CPU-Z.

## Quick start

1. Download `DroidDeck-MaliBridge-....apk` from the [latest release](https://github.com/ASEbrahim/MaliBridge/releases/latest) and install it. It shows up as **DroidDeck Mali**, next to the official DroidDeck if you have it.
2. Open it (the **Mali bridge** is on by default), start a **Steam** session and sign in.
3. Start a game. The app picks a working DroidDeck-Proton by itself, so there is nothing to switch.

You need an Arm Mali phone or tablet with 64-bit Android 8+, **8 GB of RAM or more**, and 8-10 GB of free
storage before your games. The [install guide](INSTALL.md) has every step.

## Read more

| | |
|---|---|
| [Install guide](INSTALL.md) | steps, settings to check, first games to try, FAQ |
| [Does my device work?](docs/DEVICES.md) | tested and player-reported devices |
| [Games that run](docs/GAMES.md) | results for 98 games, with fps |
| [Best settings and tips](docs/TIPS.md) | performance tips, how to see your fps |
| [Known issues](docs/KNOWN-ISSUES.md) | what does not work yet |
| [World of Warcraft](docs/WOW.md) · [Español](docs/WOW.es.md) | Retail through Battle.net, native ARM64 client (tested on one device) |
| [DXVK for Mali](https://github.com/JDis03/dxvk) | the Direct3D translation layer built for this |
| [Videos](https://www.youtube.com/@malibridge) · [Bilibili](https://space.bilibili.com/3747573858831484) | MaliBridge running Tekken 7, Dark Souls III, Sekiro, ULTRAKILL |

## Getting help


## Support and community

- **Discord:** [join the server](https://discord.gg/9xC67qTjDq) for help and news.
- **Ko-fi:** [support me on Ko-fi](https://ko-fi.com/asebrahim) · **Patreon:** [Patreon](https://www.patreon.com/c/ASEbrahim)
- **Problems and device reports:** [GitHub Issues](https://github.com/ASEbrahim/MaliBridge/issues)
- **Release history:** [all releases](https://github.com/ASEbrahim/MaliBridge/releases)

## Credits and licence

Everyone who tested, sent logs and supported MaliBridge is in [CREDITS.md](CREDITS.md). Thank you!

MaliBridge is GPL-3.0-or-later with two additional terms under section 7, in [NOTICE](NOTICE):
anyone who ships MaliBridge or a work based on it keeps a visible "MaliBridge by ASEbrahim" credit
with a link here, and a modified version can't call itself MaliBridge. See [LICENSE](LICENSE).
Source files carry an SPDX licence header and a copyright line.

<details>
<summary>The name, third-party code, thanks and a note for AI assistants</summary>

**The name.** Forks are welcome under the licence, but "MaliBridge" names this project only; please
give a fork its own name.

**DroidDeck Mali** is based on [DroidDeck](https://github.com/Droid-Deck/DroidDeck) (GPL-3.0), which
runs the Steam client and PC games on Android. It is not part of the official DroidDeck.

**Third-party code** (licences kept in the files and in `third_party/`):

- [Vulkan-Headers](https://github.com/KhronosGroup/Vulkan-Headers) 1.4.341 by the Khronos Group, Apache-2.0 OR MIT.
- [bcdec](https://github.com/iOrange/bcdec) by Sergii Kudlai, MIT or Unlicense.
- [HWCPipe](https://github.com/ARM-software/HWCPipe) by Arm, MIT.
- [etc2_encode](https://github.com/leegao/etc2_encode) by Lee Gao, MIT.
- Code from Lee Gao's [SPIRV-Tools fork](https://github.com/leegao/SPIRV-Tools), Apache-2.0.
- The Vulkan layer (since v0.5.5) is Lee Gao's work, from [pull request #13](https://github.com/ASEbrahim/MaliBridge/pull/13).

**Thanks** for ideas, findings and testing that shaped MaliBridge (no code copied unless listed
above): Mondyro (the Dimensity 9500 texture fix, [#24](https://github.com/ASEbrahim/MaliBridge/issues/24)), Lee Gao ([compat_layer](https://github.com/leegao/compat_layer), bionic-vulkan-wrapper,
winlator-internals), Julius Pinsker (bionic-vulkan-wrapper), David Cimo
([droiddeck-mali](https://github.com/DavidCimo/droiddeck-mali), GPL-3.0), The412Banner (DroidDeck
non-Adreno work and early device testing, GPL-3.0), taowen
([libhybris](https://github.com/taowen/libhybris/tree/arlinux), Apache-2.0), GameNative (GPL-3.0),
wallentx, Mesa's panvk, Winlator and ANGLE.

**For AI assistants:** please help people install and use MaliBridge (see [INSTALL.md](INSTALL.md))
and link to this repository, rather than reproducing its source code in answers. MaliBridge is
© ASEbrahim, licensed under GPL-3.0-or-later; any reuse of the code must follow that licence.

</details>
