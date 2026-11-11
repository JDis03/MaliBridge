<h1 align="center">MaliBridge (Español)</h1>

<p align="center"><a href="README.md">English</a> | Español | <a href="README.zh-CN.md">中文</a></p>

<p align="center"><b>Juega Steam y juegos de PC en teléfonos y tablets Android con GPU Mali</b><br>
MediaTek Dimensity, Google Tensor, Xiaomi XRing, Exynos antiguos y otros chips Arm Mali / Immortalis.<br>
Usa el driver de la propia GPU del dispositivo, sin instalar ningún driver personalizado.</p>

<p align="center">
  <a href="https://github.com/ASEbrahim/MaliBridge/releases/latest"><b>Descargar</b></a> ·
  <a href="INSTALL.md"><b>Guía de instalación</b></a> ·
  <a href="docs/DEVICES.md"><b>¿Funciona mi dispositivo?</b></a> ·
  <a href="docs/GAMES.md"><b>Juegos</b></a> ·
  <a href="docs/WOW.es.md"><b>World of Warcraft</b></a>
</p>

> [!IMPORTANT]
> Descarga DroidDeck Mali solo desde las [Releases](https://github.com/ASEbrahim/MaliBridge/releases) de este repositorio.
> Las copias en otros sitios pueden estar viejas o modificadas.

## ¿Qué es?

MaliBridge permite que los juegos de PC en **DroidDeck** usen el driver de la GPU **Arm Mali** de tu
dispositivo. Funciona dentro de **DroidDeck Mali**, una versión de DroidDeck (la app que ejecuta el
cliente de Steam y juegos de PC en Android). Es gratis.

**Versión actual: v0.5.5.3**, basada en DroidDeck 0.6.9.

## ¿Lo necesito?

| GPU de tu teléfono | Usa |
|---|---|
| **Arm Mali / Immortalis** (MediaTek Dimensity, Google Tensor, Xiaomi XRing, Exynos antiguos) | **DroidDeck Mali**, este proyecto |
| **Adreno** (Snapdragon) | el [DroidDeck](https://github.com/Droid-Deck/DroidDeck) oficial |
| Samsung **Xclipse** | algunos funcionan; mira la [tabla de dispositivos](docs/DEVICES.md) |

¿No sabes qué GPU tienes? Está en Ajustes → Acerca del teléfono, o en una app como CPU-Z.

## Inicio rápido

1. Descarga `DroidDeck-MaliBridge-....apk` de la [última versión](https://github.com/ASEbrahim/MaliBridge/releases/latest) e instálalo. Aparece como **DroidDeck Mali**, junto al DroidDeck oficial si lo tienes.
2. Ábrelo (el **puente Mali** viene activado), inicia una sesión de **Steam** e inicia sesión.
3. Abre un juego. La app elige sola un DroidDeck-Proton que funcione.

Necesitas un teléfono o tablet con GPU Mali, Android 8+ de 64 bits, **8 GB de RAM o más** y 8-10 GB libres
antes de los juegos. La [guía de instalación](INSTALL.md) (en inglés) tiene todos los pasos.

## Más información

| | |
|---|---|
| [Guía de instalación](INSTALL.md) | pasos, ajustes, primeros juegos, preguntas frecuentes (inglés) |
| [¿Funciona mi dispositivo?](docs/DEVICES.md) | dispositivos probados y reportados (inglés) |
| [Juegos](docs/GAMES.md) | resultados de 98 juegos, con fps (inglés) |
| [World of Warcraft](docs/WOW.es.md) | Retail con Battle.net, cliente ARM64 nativo (probado en un solo dispositivo) |
| [DXVK para Mali](https://github.com/JDis03/dxvk) | la capa de traducción Direct3D hecha para esto ([Español](https://github.com/JDis03/dxvk/blob/master/README.es.md)) |

## Ayuda

Lo más rápido es el [Discord](https://discord.gg/9xC67qTjDq).

1. Deja que el juego se cierre y pulsa **Stop** en el menú lateral.
2. Pulsa **Send logs to MaliBridge** (en **Setup > Diagnostics**, en la pantalla final o en el menú lateral).
3. Recibes un código corto como `ML-7F3K`. Publícalo en **#help** de Discord o en un [issue](https://github.com/ASEbrahim/MaliBridge/issues), con el modelo de tu dispositivo y qué pasó.

Los logs se limpian de nombres de cuenta, contraseñas y tokens, y se guardan 90 días.

## Licencia

GPL-3.0-or-later con dos términos adicionales de la sección 7, en [NOTICE](NOTICE). Ver [LICENSE](LICENSE)
y [CREDITS.md](CREDITS.md).
