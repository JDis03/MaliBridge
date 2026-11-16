# World of Warcraft (Retail) con Battle.net

[English](WOW.md) · **Español** · [Volver al README](../README.md)

World of Warcraft Retail corre en DroidDeck Mali con el cliente oficial **Battle.net**, usando el
ejecutable **ARM64 nativo** de Blizzard (`Wow-ARM64.exe`) en lugar del x64.

> **Estado: probado en un solo dispositivo.** Todo lo que sigue se midió en el dispositivo de la
> tabla. Los demás dispositivos Mali no se han probado. Cuéntanos qué te pasa (ver
> [Getting help](../README.md#getting-help)). Es no oficial y sin relación con Blizzard. Usar una capa
> Wine modificada en un juego online con anticheat tiene riesgo para tu cuenta; úsalo bajo tu criterio.

## Qué se probó

| | |
|---|---|
| Dispositivo | Xiaomi 15T (Dimensity 8400, Mali-G720 MC7), 11,6 GB de RAM, Android 16 |
| App | DroidDeck Mali 0.5.6 (probado en 0.5.5.3 y 0.5.6) |
| Herramienta de compatibilidad | DroidDeck-Proton 11-12.1 |
| Juego | World of Warcraft Retail, cliente ARM64 nativo (`Wow-ARM64.exe`) |
| DXVK | el build ARM64X de [JDis03/dxvk](https://github.com/JDis03/dxvk/releases/tag/v3.1.1-mali-arm64x) (`v3.1.1-mali-arm64x`) |
| Resultado | **~59 fps** en el menú 3D; **~27–28 fps** estables dentro del mundo (Westfall / Bosque de Elwynn, 1280×720 nativo, `vsync=0`, modo `performance`) |
| Memoria | el proceso del juego ocupaba unos 1,2–1,3 GB residentes |

## Por qué el cliente ARM64

El Agent de Battle.net es un programa de 32 bits. Bajo Wine ve un equipo ARM64, así que pide a los
servidores de Blizzard la versión **ARM64** e instala `Wow-ARM64.exe`. No necesitas un PC ni copiar
archivos del juego a mano: el **Escanear y reparar** de Battle.net deja la instalación en la versión
actual.

Ejecutar el cliente nativo evita la capa de emulación x64 para el juego en sí, y por eso el teléfono
se calienta menos y queda más RAM libre.

## Pasos

1. Instala DroidDeck Mali y ábrelo (ver la [guía de instalación](../INSTALL.md)).
2. Abre la entrada de **Battle.net** e inicia sesión. Instala World of Warcraft desde la ventana de Battle.net.
3. Espera la descarga. El juego es grande (unos 55 GB), así que revisa antes el almacenamiento.
4. Pulsa **Jugar**.

### Qué esperar la primera vez

- **El primer arranque de Battle.net es lento** (uno o dos minutos) mientras se traducen las partes de
  32 bits y arranca el Agent. Espera y no lo cierres.
- **Mantén el teléfono despierto y DroidDeck en primer plano** mientras carga. DroidDeck pausa el lado
  Linux cuando la app sale de primer plano o se apaga la pantalla, y un juego pausado se ve igual que
  uno colgado. Sube el tiempo de apagado de pantalla mientras pruebas.
- **Battle.net se cierra solo poco después de que el juego esté en marcha.** El lanzador de Battle.net
  de DroidDeck cierra lo que queda de Battle.net unos 20 segundos después de iniciar el juego, para
  darle esa memoria al juego. Es intencional. Vuelve a abrir Battle.net cuando quieras actualizar o
  cambiar de juego.
- Si Battle.net se queda en un bucle de inicio de sesión o nunca muestra su ventana, cierra la sesión
  y arráncala de nuevo.

## Requisitos y límites conocidos

- **El arreglo de `ntdll.dll` ya está en DroidDeck-Proton, no hay que parchear nada.** El ejecutable de
  Blizzard mapea su propia copia limpia de `ntdll.dll` y llama a los servicios del sistema a través de
  ella, y los stubs normales de Wine fallan ahí. DroidDeck-Proton lleva el arreglo desde la **11-11.3**
  (notas de la versión: "World of Warcraft on ARM64EC", de
  [arusiasotto](https://github.com/arusiasotto)), y el Proton por defecto de la app, 11-11.10, lo tiene:
  comprobé que su `ntdll.dll` contiene los 258 stubs reescritos. Los Proton más antiguos no.
- **Comparación frente al DXVK integrado de DroidDeck:** Medido en Mali-G720 MC7 (1280×720, `vsync=0`, modo `performance`), `JDis03/dxvk` reduce las consultas `vkGetPhysicalDeviceMemoryProperties2` de **1.042 llamadas/10 s** en el DXVK integrado a **27–36 llamadas/10 s**, y añade `preferTransferClears` (~0,7 ms/frame más rápido en Westfall). Ten en cuenta que `droiddeck-proton-run` restaura el DXVK integrado al iniciar sesión desde `desired.tsv` salvo que se lance directo o se empaquete en el runtime.
- **Límite de GPU dentro del mundo:** A 1280×720 nativos en el mundo, la Mali-G720 MC7 queda saturada por hardware (~704 MHz, compute shaders pesados de ASSAO / Volume Fog / Clustered Lighting / agua FFT + ancho de banda fragment). Bajar `RenderScale` (p. ej. `0.5`–`0.7`) sube los FPS a costa de nitidez 3D.
- Memoria: 8 GB es el mínimo de la app; para WoW, un dispositivo de 12 GB es el caso cómodo.
- Solo se probó Retail. No se probaron otros juegos de Blizzard.

## Créditos

- [arusiasotto](https://github.com/arusiasotto): la idea del stub de `ntdll.dll` y la base de WoW en
  DroidDeck sobre la que esto se apoya.
- Los autores de DroidDeck, por el runtime y el lanzador de Battle.net.
