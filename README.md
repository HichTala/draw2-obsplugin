<div align="center">
  <p>
    <img src="https://raw.githubusercontent.com/HichTala/draw2/refs/heads/main/figures/banner-draw.png" alt="DRAW Banner">
  </p>
<div>

[![DRAW2 Workflow](https://github.com/HichTala/draw2-plugin/actions/workflows/push.yaml/badge.svg)](https://github.com/HichTala/draw2-plugin/actions/workflows/push.yaml)
[![Licence](https://img.shields.io/pypi/l/ultralytics)](LICENSE)
[![Github](https://img.shields.io/badge/-github-181717?logo=github&labelColor=555)](https://github.com/HichTala/draw2)
[![Twitter](https://img.shields.io/badge/-twitter-000?logo=x&labelColor=555)](https://twitter.com/hichtala)
[![HuggingFace Downloads](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fhuggingface.co%2Fapi%2Fmodels%2FHichTala%2Fdraw2&query=%24.downloads&logo=huggingface&label=downloads&color=%23FFD21E)](https://huggingface.co/HichTala/draw2)
[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat&logo=medium&labelColor=555)](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a)
[![WandB](https://img.shields.io/badge/visualize_in-W%26B-yellow?logo=weightsandbiases&color=%23FFBE00)](https://wandb.ai/hich_/draw)

[🇫🇷 Français](readmes/README_fr.md) | [🇧🇷 Português](readmes/README_pt-br.md) | [🇯🇵 日本語](readmes/README_jp.md) | [🇪🇸 Español](readmes/README_es.md)

</div>

</div>

DRAW 2 (which stands for **D**etect and **R**ecognize **A** **W**ide range of cards version 2) is an object detector
trained to detect _Yu-Gi-Oh!_ cards in all types of images, and in particular in dueling images.

This project is the plugin part of the DRAW 2 system. It allows users to seamlessly integrate the
detector directly into their live streams or recorded videos; and those **without any particular technical skills**.
The plugin can display detected cards in real time for an enhanced viewing experience.
The python backend project is available [here](https://github.com/HichTala/draw2).

This project is licensed under the [GNU Affero General Public License v3.0](LICENCE); all contributions are welcome.

---

## <div align="center">📰 News</div>

> 🃏 **Latest card pool:** `BLZD` --- last updated `18-05-2026`
> 🔧 **Latest app version:** `0.2.1-beta` --- last updated `01-06-2026`

<table>
  <tr>
    <th>Date</th>
    <th>Type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><b>01-06-2026</b></td>
    <td>🔧 App Update</td>
    <td>Released version 0.2.1-beta --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.2.1">see release notes</a></td>
  </tr>
  <tr>
    <td><b>18-05-2026</b></td>
    <td>🃏 Card Pool</td>
    <td>Card pool updated --- now supports cards up to <i>Blazing Dominion</i></td>
  </tr>
  <tr>
    <td><b>06-04-2026</b></td>
    <td>🃏 Card Pool</td>
    <td>Card pool updated --- now supports cards up to <i>Maze of Muertos</i></td>
  </tr>
  <tr>
    <td><b>06-04-2026</b></td>
    <td>🔧 App Update</td>
    <td>Released version 0.2.0-beta --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.2.0">see release notes</a></td>
  </tr>
  <tr>
    <td><b>09-03-2025</b></td>
    <td>🔧 App Update</td>
    <td>Released version 0.1.5-alpha --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.1.5">see release notes</a></td>
  </tr>
  <tr>
    <td><b>24-08-2025</b></td>
    <td>🃏 Card Pool</td>
    <td>Card pool updated --- now supports cards up to <i>Justic Hunter</i></td>
  </tr>
</table>

---

## <div align="center">📄Documentation</div>

### 🛠️ Installation

Follow the installation instruction depending on your operating system so everything works smoothly:

<details open>
<summary>🪟 Windows</summary>

1. Download the plugin installer from this
   link: [DRAW2 Plugin Installer](https://github.com/HichTala/draw2-plugin/releases/download/0.2.1/draw2-plugin-installer.exe)
2. Run the installer and follow the on-screen instructions.
3. Once the installation is complete, launch OBS Studio. If everything is set up correctly, you should see in the
   `Docks` menu
   a new option called `Draw 2`. You can activate the dock and dock it wherever you want.

   The download is complete, you can enjoy detecting !

</details>

<details>
<summary>🐧 Linux</summary>

Coming soon 👀

</details>

<details>
<summary>🍏 MacOS</summary>

I'm not familiar enough with OBS on macOS to provide a reliable installation guide.
The plugin is able to compile successfully on macOS, but I haven't tested it thoroughly.
If you have experience with OBS plugins on macOS and would like to contribute an installation guide,
please feel free to submit a pull request.

#### Building from source (macOS)

There is no pre-built macOS release yet, so you have to build the plugin yourself.

1. Install the build prerequisites with [Homebrew](https://brew.sh):

   ```bash
   brew install cmake ccache coreutils jq xcbeautify
   ```

   You also need a recent **Xcode** (with its command line tools).

2. Configure and build (universal — `arm64` + `x86_64`):

   ```bash
   cmake --preset macos
   cmake --build build_macos --config RelWithDebInfo
   ```

3. The built plugin bundle is produced at:

   ```
   build_macos/RelWithDebInfo/draw2-plugin.plugin
   ```

4. Install it by copying the bundle into your OBS plugins folder, then restart OBS:

   ```bash
   mkdir -p "$HOME/Library/Application Support/obs-studio/plugins"
   cp -R build_macos/RelWithDebInfo/draw2-plugin.plugin \
     "$HOME/Library/Application Support/obs-studio/plugins/"
   ```

   Once OBS restarts, the plugin appears as `Draw 2` in the `Docks` menu.

#### Setting up the Python backend (macOS)

The plugin runs the `draw` backend as a **separate Python process** — it does not
embed an interpreter. You provide a Python installation that has the `draw`
package, and the plugin launches `<prefix>/bin/python` and communicates with it
over shared memory. There is no automatic download on macOS yet, so you set this
up manually.

> The Python you point to just needs `bin/python` and the `draw` package
> importable. **Any reasonably recent Python 3 works — it does not have to match
> the plugin's build** (the plugin no longer embeds an interpreter). A
> self-contained CPython is the easiest to set up.

1. Get a self-contained CPython. A relocatable build from
   [python-build-standalone](https://github.com/astral-sh/python-build-standalone)
   works well and won't be broken by `brew upgrade`:

   ```bash
   # pick the install_only build for your arch (aarch64 for Apple Silicon)
   curl -fL -o python.tar.gz \
     https://github.com/astral-sh/python-build-standalone/releases/download/<tag>/cpython-3.13.<x>+<tag>-aarch64-apple-darwin-install_only.tar.gz
   mkdir -p ~/.draw2-runtime && tar -xzf python.tar.gz -C ~/.draw2-runtime
   ```

2. Install the `draw` backend into that prefix. Use the **`obs-plugin` branch** —
   that is the one that exposes the entry point the plugin launches (the default
   `main` branch is the standalone CLI):

   ```bash
   ~/.draw2-runtime/python/bin/python -m pip install "git+https://github.com/HichTala/draw2@obs-plugin"
   ```

3. In the Draw 2 settings, set **Select Python installation** to the prefix folder
   (the one that contains `bin/` and `lib/`), e.g. `~/.draw2-runtime/python`.
   Expected layout:

   ```text
   <prefix>/bin/python
   <prefix>/lib/python3.13/site-packages/draw
   ```

   </details>

### 🚀 Usage

When the plugin is installed and the model weights are downloaded, you can launch OBS Studio.

1. Open the `Docks` menu and select `Draw 2` to activate the plugin dock.
2. In the Draw 2 dock, you can configure the plugin settings by clicking on the gear icon next to `Start DRAW` button:
   - **Select Python installation**: Path to the Python prefix that has the `draw` backend installed (the folder
     containing `bin/` and `lib/`). Must be a full Python install, not a virtualenv. See the macOS setup section
     for details.
   - **Select Deck Lists**: Choose the deck list file(s) with the cards you want to detect — up to 3.
     To add deck lists, click `Open Folder` and drop your `.ydk` files into the opened folder.
   - **Minimum Out of Screen Time**: The minimum time a card just detected can be displayed again.
   - **Minimum Screen Time**: The minimum time a card is displayed.
   - **Confidence Threshold**: Set the minimum confidence level for card detection. Detections below this threshold
     will be ignored.
   - **Advanced features** (all off by default): opt-in toggles. Enable one here, then configure it where noted.
     - **Enable two players** — adds a **Player 2** set of deck lists and runs a **separate detector per player**,
       so two players can be processed at once. Leave it off for a single-player setup.
     - **Enable detector input crop** — adds **Crop (Left/Top/Right/Bottom, px)** fields to the `Draw Display`
       source, to focus detection on the region where cards are placed.
     - **Enable 180° input rotation** — adds a **Rotate input 180°** toggle to the source, for a camera mounted
       upside down.
     - With crop or rotation enabled, the source also gains a **Preview detector input** toggle: turn it on to
       render the cropped/rotated frame it feeds the detector (so you can dial in the crop right in the source's
       preview), then turn it off to go back to showing detected cards.
     - **Enable debug logging** — surfaces verbose diagnostics: the dock log shows the exact backend launch
       (resolved deck paths, channel, thresholds) and every backend line unfiltered, and the OBS log gets the
       capture details (input source, dimensions, crop/rotation). Handy when detection isn't behaving.
     - **Enable remote decklist** — load a deck from an HTTP(S) URL instead of a local `.ydk` file; see the note
       below the `Draw Display` source.
     - **Export detected card info to files** — write the detected cards (JSON / JSONL / plain text) to a per-user
       folder, for OBS Text sources, bots or overlays; see the note below the `Draw Display` source.
3. The plugin provide a new source called `Draw Display`. You can add it to your scene like any other source.
   This source will display the detected cards on the screen. You can choose what source/scene to detect cards from.
   With two-player mode enabled, use the **Detector / Player** property on the source to pick which detector it reads from (**Player 1** or **Player 2**); add one `Draw Display` per player to show both at once.

   > 💡 The plugin can also load a decklist from an **HTTP(S) URL** instead of a local `.ydk` file — handy when
   > your deck list is served by a remote API or tournament system. It is **off by default** — enable
   > **Enable remote decklist** in Draw 2 settings (*Advanced features*); the URLs are then configured in a
   > dedicated **Decklist** tab.
   >
   > Two modes are available once enabled:
   > - **Import deck from URL…** (button in the Decklist tab) — fetches the URL once and writes the result as a
   >   normal `.ydk` into the decklists folder, so you can use it as a regular file deck.
   > - **Per-player URL field** — one URL per player (Player 1, plus Player 2 in two-player mode). While remote
   >   is on, these replace the file selectors; the URL is fetched live at Start DRAW. On any failure that player
   >   simply starts with no deck filter.
   >
   > Accepted server response formats: JSON array of card IDs (passcodes); JSON object
   > `{ "main": [...], "extra": [...], "side": [...] }`; raw `.ydk` text; or plain text containing numeric IDs.
   >
   > An optional auth header (name + value, e.g. `Authorization` / `Bearer …`) can be configured and is sent
   > with every request.
   >
   > ⚠️ URLs and the header value are stored in plain text in QSettings, like all other plugin settings —
   > avoid placing long-lived secrets there.

   > 💡 The plugin can also **export detected card info to files** so you can show it anywhere — an OBS Text source
   > the streamer reads on stream, bots, or HTML/browser overlays. It is **off by default** — enable *Export
   > detected card info to files* in the Draw 2 settings (*Feature flags*) and restart DRAW. While running, each
   > detector writes to `plugin_config/draw2-plugin/state/` (per player `N`):
   > - `current_pN.json` — cards currently on screen:
   >   `{ "updated_at", "channel", "cards": [ { "id", "name", "type", "attribute", "race", "atk", "def", "desc" } ] }`
   >   (rich fields come from YGOPRODeck; missing fields are omitted).
   > - `events_pN.jsonl` — append-only log, one JSON per line:
   >   `{ "ts", "event": "appeared" | "disappeared", "card": { … } }`.
   > - `current_card_pN.txt` — plain text, names of the cards on screen (newline-separated). Point an OBS **Text**
   >   source at this file (*Read from file*) to show the current card live.
   >
   > Metadata language defaults to English; set the `card_info_lang` key in the Draw 2 settings store to one of
   > `en` / `fr` / `de` / `it` / `pt` (YGOPRODeck does not provide Spanish). The backend half lives in the `draw2`
   > backend; the plugin only points it at the output folder.
4. Click the `Start DRAW` button to start the detection process. The plugin will start detecting cards in real time
   and display them on the screen using the `Draw Display` source. The plugin start detecting from the moment you see
   the
   `Stop DRAW` button. If you don't see it something went wrong.
5. In the other case you can enjoy the plugin!

Here is a small overview :)

<div align="center">
    <img src="https://raw.githubusercontent.com/HichTala/draw2/refs/heads/main/figures/overview.gif" width="960" height="540" />
</div>

---

## <div align="center">🔍Method Overview</div>

A medium blog post explainng the main process from data collection to final prediction has been written.
You can access it at [this](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a) adress. If you have any questions, don't hesitate to open an issue.

[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat&logo=medium&labelColor=555)](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a)

---

## <div align="center">💬Contact</div>

You can reach me on Twitter [@hichtala](https://twitter.com/hichtala) or by email
at [hich.tala.phd@gmail.com](mailto:hich.tala.phd@gmail.com).

---

## <div align="center">⭐Star History</div>

<div align="center">
  <a href="https://www.star-history.com/#hichtala/draw2&type=date&legend=top-left">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=hichtala/draw2&type=date&theme=dark&legend=top-left" />
      <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=hichtala/draw2&type=date&legend=top-left" />
      <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=hichtala/draw2&type=date&legend=top-left" />
    </picture>
  </a>
</div>
