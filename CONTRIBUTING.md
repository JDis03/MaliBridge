# Contributing & Upstreaming (`JDis03/MaliBridge`)

This fork tracks [ASEbrahim/MaliBridge](https://github.com/ASEbrahim/MaliBridge) and coordinates Mali/TBDR testing, documentation, and DXVK integration via [JDis03/dxvk](https://github.com/JDis03/dxvk).

## Repositories

- **MaliBridge (this repo):** Vulkan bridge layer/server (`ASEbrahim/MaliBridge` fork) + device reports & game docs.
- **DXVK for Mali:** [JDis03/dxvk](https://github.com/JDis03/dxvk) (`doitsujin/dxvk` fork with `tilerMode`, `isArmMali()`, `preferTransferClears`, async pipeline compilation, and `COFF-ARM64X` builds).
- **Android launcher base:** [Droid-Deck/DroidDeck](https://github.com/Droid-Deck/DroidDeck) / [ASEbrahim/DroidDeck](https://github.com/ASEbrahim/DroidDeck). *(Note: upstream `ASEbrahim/MaliBridge` v0.5.6 currently ships an APK release while its v0.5.6 source archive is still pending.)*

## How to contribute

```bash
git clone https://github.com/JDis03/MaliBridge.git
cd MaliBridge
git remote add upstream https://github.com/ASEbrahim/MaliBridge.git
git fetch upstream
```

1. **Keep commits scoped by purpose.** Separate documentation/device reports (`docs/`), MaliBridge C/C++ fixes (`layer/`, `server/`, `client/`), and DXVK changes (open those in [JDis03/dxvk](https://github.com/JDis03/dxvk)).
2. **Respect upstream naming & licensing.** Keep the `"MaliBridge by ASEbrahim"` credit per [LICENSE](LICENSE) and [NOTICE](NOTICE). Any custom redistributable build based on modified sources must use its own name.
3. **Include real hardware measurements.** For performance or compatibility PRs, state your device SoC, Mali GPU + driver version (`rXXpY`), resolution, DroidDeck-Proton version, and `vkbridge-server.log` `perf:` / `gpu counters` lines.

## Contributing back to upstream (`ASEbrahim/MaliBridge`)

To prepare a clean PR for upstream:

```bash
git fetch upstream
git checkout -b pr/<topic> upstream/main
git cherry-pick <commit-sha>
```

Keep fork-only links/notes out of upstream PR branches so maintainers can merge cleanly.
