<div align="center">
  <p>
    <img src="https://raw.githubusercontent.com/HichTala/draw2/refs/heads/main/figures/banner-draw.png" alt="DRAW Banner">
  </p>
<div>

[![DRAW2 Workflow](https://github.com/HichTala/draw2-plugin/actions/workflows/push.yaml/badge.svg)](https://github.com/HichTala/draw2-plugin/actions/workflows/push.yaml)
[![Licence](https://img.shields.io/pypi/l/ultralytics)](../LICENSE)
[![Github](https://img.shields.io/badge/-github-181717?logo=github&labelColor=555)](https://github.com/HichTala/draw2)
[![Twitter](https://img.shields.io/badge/-twitter-000?logo=x&labelColor=555)](https://twitter.com/hichtala)
[![HuggingFace Downloads](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fhuggingface.co%2Fapi%2Fmodels%2FHichTala%2Fdraw2&query=%24.downloads&logo=huggingface&label=downloads&color=%23FFD21E)](https://huggingface.co/HichTala/draw2)
[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat&logo=medium&labelColor=555)](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a)
[![WandB](https://img.shields.io/badge/visualize_in-W%26B-yellow?logo=weightsandbiases&color=%23FFBE00)](https://wandb.ai/hich_/draw)

[🇬🇧 English](../README.md) | [🇫🇷 Français](README_fr.md) | [🇧🇷 Português](README_pt-br.md) | [🇯🇵 日本語](README_jp.md)

</div>

</div>

DRAW 2 (que significa **D**etect and **R**ecognize **A** **W**ide range of cards version 2 — detectar y reconocer una
amplia gama de cartas, versión 2) es un detector de objetos entrenado para detectar cartas de _Yu-Gi-Oh!_ en todo tipo
de imágenes, y en particular en imágenes de duelos.

Este proyecto es la parte de plugin del sistema DRAW 2. Permite a los usuarios integrar el detector directamente en sus
directos o vídeos grabados, y todo ello **sin necesidad de conocimientos técnicos particulares**.
El plugin puede mostrar las cartas detectadas en tiempo real para mejorar la experiencia de quienes lo ven.
El proyecto del backend de Python está disponible [aquí](https://github.com/HichTala/draw2).

Este proyecto está licenciado bajo la [GNU Affero General Public License v3.0](LICENCE); ¡todas las contribuciones son
bienvenidas!

---

## <div align="center">📰 Novedades</div>

> 🃏 **Último pool de cartas:** `BLZD` --- última actualización `18-05-2026`
> 🔧 **Última versión de la app:** `0.2.1-beta` --- última actualización `01-06-2026`

<table>
  <tr>
    <th>Fecha</th>
    <th>Tipo</th>
    <th>Descripción</th>
  </tr>
  <tr>
    <td><b>01-06-2026</b></td>
    <td>🔧 Versión de la app</td>
    <td>Versión 0.2.1-beta publicada --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.2.1">ver notas de la versión</a></td>
  </tr>
  <tr>
    <td><b>18-05-2026</b></td>
    <td>🃏 Pool de cartas</td>
    <td>Pool de cartas actualizado --- ahora admite cartas hasta <i>Blazing Dominion</i></td>
  </tr>
  <tr>
    <td><b>06-04-2026</b></td>
    <td>🃏 Pool de cartas</td>
    <td>Pool de cartas actualizado --- ahora admite cartas hasta <i>Maze of Muertos</i></td>
  </tr>
  <tr>
    <td><b>06-04-2026</b></td>
    <td>🔧 Versión de la app</td>
    <td>Versión 0.2.0-beta publicada --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.2.0">ver notas de la versión</a></td>
  </tr>
  <tr>
    <td><b>09-03-2025</b></td>
    <td>🔧 Versión de la app</td>
    <td>Versión 0.1.5-alpha publicada --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.1.5">ver notas de la versión</a></td>
  </tr>
  <tr>
    <td><b>24-08-2025</b></td>
    <td>🃏 Pool de cartas</td>
    <td>Pool de cartas actualizado --- ahora admite cartas hasta <i>Justic Hunter</i></td>
  </tr>
</table>

---

## <div align="center">📄 Documentación</div>

### 🛠️ Instalación

Sigue las instrucciones de instalación según tu sistema operativo para que todo funcione correctamente:

<details open>
<summary>🪟 Windows</summary>

1. Descarga el instalador del plugin desde este
   enlace: [DRAW2 Plugin Installer](https://github.com/HichTala/draw2-plugin/releases/download/0.2.1/draw2-plugin-installer.exe)
2. Ejecuta el instalador y sigue las instrucciones en pantalla.
3. Una vez completada la instalación, abre OBS Studio. Si todo está configurado correctamente, deberías ver en el
   menú `Docks` una nueva opción llamada `Draw 2`. Puedes activar el dock y colocarlo donde quieras.

   ¡La instalación ha terminado, ya puedes disfrutar detectando!

</details>

<details>
<summary>🐧 Linux</summary>

Próximamente 👀

</details>

<details>
<summary>🍏 MacOS</summary>

No conozco OBS en macOS lo suficiente como para ofrecer una guía de instalación fiable.
El plugin compila correctamente en macOS, pero no lo he probado a fondo.
Si tienes experiencia con plugins de OBS en macOS y quieres contribuir con una guía de instalación,
no dudes en enviar un pull request.

#### Compilar desde el código fuente (macOS)

Todavía no hay una versión precompilada para macOS, así que tienes que compilar el plugin tú mismo.

1. Instala los requisitos de compilación con [Homebrew](https://brew.sh):

   ```bash
   brew install cmake ccache coreutils jq xcbeautify
   ```

   También necesitas un **Xcode** reciente (con sus herramientas de línea de comandos).

2. Configura y compila (universal — `arm64` + `x86_64`):

   ```bash
   cmake --preset macos
   cmake --build build_macos --config RelWithDebInfo
   ```

3. El bundle del plugin compilado se genera en:

   ```
   build_macos/RelWithDebInfo/draw2-plugin.plugin
   ```

4. Instálalo copiando el bundle en tu carpeta de plugins de OBS y luego reinicia OBS:

   ```bash
   mkdir -p "$HOME/Library/Application Support/obs-studio/plugins"
   cp -R build_macos/RelWithDebInfo/draw2-plugin.plugin \
     "$HOME/Library/Application Support/obs-studio/plugins/"
   ```

   Una vez que OBS se reinicie, el plugin aparece como `Draw 2` en el menú `Docks`.

#### Configurar el backend de Python (macOS)

El plugin ejecuta el backend `draw` como un **proceso Python separado** — no incorpora
un intérprete. Tú proporcionas una instalación de Python que tenga el paquete `draw`,
y el plugin lanza `<prefix>/bin/python` y se comunica con él a través de memoria compartida.
Todavía no hay descarga automática en macOS, así que debes configurarlo manualmente.

> El Python que indiques solo necesita `bin/python` y el paquete `draw` importable.
> **Cualquier Python 3 reciente funciona — no tiene que coincidir con la compilación del
> plugin** (el plugin ya no incorpora un intérprete). Un CPython autocontenido es la
> opción más sencilla.

1. Consigue un CPython autocontenido. Una compilación reubicable de
   [python-build-standalone](https://github.com/astral-sh/python-build-standalone)
   funciona bien y no se romperá con `brew upgrade`:

   ```bash
   # pick the install_only build for your arch (aarch64 for Apple Silicon)
   curl -fL -o python.tar.gz \
     https://github.com/astral-sh/python-build-standalone/releases/download/<tag>/cpython-3.13.<x>+<tag>-aarch64-apple-darwin-install_only.tar.gz
   mkdir -p ~/.draw2-runtime && tar -xzf python.tar.gz -C ~/.draw2-runtime
   ```

2. Instala el backend `draw` en ese prefijo. Usa la **rama `obs-plugin`** —
   esa es la que expone el punto de entrada que el plugin lanza (la rama por defecto
   `main` es la CLI independiente):

   ```bash
   ~/.draw2-runtime/python/bin/python -m pip install "git+https://github.com/HichTala/draw2@obs-plugin"
   ```

3. En los ajustes de Draw 2, establece **Select Python installation** en la carpeta del prefijo
   (la que contiene `bin/` y `lib/`), p. ej. `~/.draw2-runtime/python`.
   Estructura esperada:

   ```text
   <prefix>/bin/python
   <prefix>/lib/python3.13/site-packages/draw
   ```

   </details>

### 🚀 Uso

Cuando el plugin está instalado y los pesos del modelo están descargados, puedes abrir OBS Studio.

1. Abre el menú `Docks` y selecciona `Draw 2` para activar el dock del plugin.
2. En el dock de Draw 2 puedes configurar los ajustes del plugin haciendo clic en el icono de engranaje junto al
   botón `Start DRAW`:
   - **Select Python installation**: ruta al prefijo de Python que tiene instalado el backend `draw` (la carpeta que
     contiene `bin/` y `lib/`). Debe ser una instalación de Python completa, no un virtualenv. Consulta la sección de
     configuración de macOS para más detalles.
   - **Select Deck List**: elige el archivo de deck list que contiene las cartas que quieres detectar. Se pueden
     gestionar hasta 3 deck lists a la vez. Para añadir nuevas deck lists, puedes hacer clic en el botón
     `Open Folder` y arrastrar y soltar tus archivos de deck list (en formato ydk) en la carpeta que se abre.
   - **Minimum Out of Screen Time**: el tiempo mínimo que debe pasar para que una carta recién detectada pueda volver
     a mostrarse.
   - **Minimum Screen Time**: el tiempo mínimo que se muestra una carta.
   - **Confidence Threshold**: define el nivel de confianza mínimo para la detección de cartas. Las detecciones por
     debajo de este umbral se ignorarán.
   - **Advanced features** (desactivadas por defecto): dos ajustes opcionales de la entrada del detector que solo
     afectan a lo que ve el detector, no a tu salida en directo. Actívalas aquí y configura los valores en la fuente
     `Draw Display`:
     - **Enable detector input crop** — añade los campos **Crop (Left/Top/Right/Bottom, px)** a la fuente, para
       enfocar la detección en la región donde se colocan las cartas.
     - **Enable 180° input rotation** — añade el interruptor **Rotate input 180°** a la fuente, para una cámara
       montada al revés.
     - Cuando alguna de las dos está activada, la fuente también gana el interruptor **Preview detector input**:
       actívalo para que la fuente muestre el fotograma recortado/rotado que alimenta al detector (así puedes
       ajustar el recorte directamente en el preview de la fuente), y desactívalo para volver a mostrar las
       cartas detectadas.
   - **Enable debug logging** (desactivado por defecto): muestra diagnósticos detallados — el log del dock muestra
     el lanzamiento exacto del backend (rutas de deck resueltas, canal, umbrales) y cada línea del backend sin
     filtrar, y el log de OBS recibe los detalles de captura (fuente de entrada, dimensiones, recorte/rotación).
     Útil cuando la detección no funciona como se espera.
3. El plugin proporciona una nueva fuente llamada `Draw Display`. Puedes añadirla a tu escena como cualquier otra
   fuente. Esta fuente mostrará las cartas detectadas en pantalla. Puedes elegir de qué fuente/escena detectar las
   cartas.
4. Haz clic en el botón `Start DRAW` para iniciar el proceso de detección. El plugin empezará a detectar cartas en
   tiempo real y a mostrarlas en pantalla mediante la fuente `Draw Display`. El plugin comienza a detectar en el
   momento en que ves el botón `Stop DRAW`. Si no lo ves, algo salió mal.
5. En caso contrario, ¡disfruta del plugin!

Aquí tienes una pequeña vista previa :)

<div align="center">
    <img src="https://raw.githubusercontent.com/HichTala/draw2/refs/heads/main/figures/overview.gif" width="960" height="540" />
</div>

---

## <div align="center">🔍 Descripción del método</div>

Se ha publicado un artículo en Medium que explica el proceso principal, desde la recopilación de datos hasta la
predicción final. Puedes leerlo en
[esta](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a)
dirección. Si tienes cualquier pregunta, no dudes en abrir una issue.

[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat&logo=medium&labelColor=555)](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a)

---

## <div align="center">💬 Contacto</div>

Puedes contactarme en Twitter [@hichtala](https://twitter.com/hichtala) o por correo
en [hich.tala.phd@gmail.com](mailto:hich.tala.phd@gmail.com).

---

## <div align="center">⭐ Historial de Stars</div>

<div align="center">
  <a href="https://www.star-history.com/#hichtala/draw2&type=date&legend=top-left">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=hichtala/draw2&type=date&theme=dark&legend=top-left" />
      <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=hichtala/draw2&type=date&legend=top-left" />
      <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=hichtala/draw2&type=date&legend=top-left" />
    </picture>
  </a>
</div>
