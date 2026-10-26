<a id="top"></a>

<h1 align="center">PSArt + YourManager for Photoshop</h1>

<p align="center">Photoshop panels for illustrators: PSArt cleans, splits and redraws your art; YourManager tracks every PSD version.</p>

<p align="center"><img src="docs/media/psart/hero.png" alt="Results of PSArt tools on demo pictures: separated layer, vector lines, removed background, selection painted, curved perspective grid, part edited with AI" width="820"></p>

- **Split** a painting into layers in seconds
- **Trace** pixel lineart into sharp vector lines
- **Clean** AI images and remove plain backgrounds
- **Find** the PSD behind any exported image

<p align="center"><a href="https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.26b/PSArt_1.5.2.zip"><img alt="Download PSArt 1.5.2" src="https://img.shields.io/badge/Download-PSArt%201.5.2-2ea44f?style=for-the-badge"></a> <a href="https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.26b/YourManager_0.4.0.zip"><img alt="Download YourManager 0.4.0" src="https://img.shields.io/badge/Download-YourManager%200.4.0-1f6feb?style=for-the-badge"></a></p>

Windows only, Photoshop 2023 or later. Pictures come from the plugins' own engines on test images.

## Install

### PSArt 1.5.2

Download: **[PSArt_1.5.2.zip](https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.26b/PSArt_1.5.2.zip)** · [All versions](https://github.com/DanhBoo/psart-plugin/releases)

1. Close Photoshop and delete any older copy in `Plug-ins` ("PSArtCodex", "PSArt Codex" or "PSArt").
2. Right-click the zip > Properties > tick **Unblock** > OK, then extract it.
3. Copy the `PSArt` folder into `C:\Program Files\Adobe\Adobe Photoshop <year>\Plug-ins\` (it must end as `Plug-ins\PSArt\manifest.json`).
4. Open Photoshop > **Plugins** > **PSArt**. When asked about `start_bridge.vbs` (the Codex tab's bridge), tick *Remember my choice* and click **Allow**, or **Deny** if you do not use Codex.

Full install steps: [CAI_DAT_PSArt.txt](CAI_DAT_PSArt.txt)

### YourManager 0.4.0

Download: **[YourManager_0.4.0.zip](https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.26b/YourManager_0.4.0.zip)** · [All versions](https://github.com/DanhBoo/psart-plugin/releases)

1. Close Photoshop; delete any older YourManager in Plug-ins.
2. Copy the `ptsplugin` folder from the zip into `C:\Program Files\Adobe\Adobe Photoshop <year>\Plug-ins\`.
3. Open Photoshop > **Plugins** > **YourManager** (language: **Settings > Language**).
4. Photoshop asks to run a .vbs file on first Find / Delete: click **Allow**.

Full install steps: [CAI_DAT_YourManager.txt](CAI_DAT_YourManager.txt)

## Requirements

**PSArt**

- Windows 10 / 11
- Photoshop 2023 (24.2) or later
- Codex tab only: the Codex app (or `npm i -g @openai/codex`) signed in with a ChatGPT account. No Node.js needed.

**YourManager**

- Windows 10 / 11
- Photoshop 2023 (24.0) or later

## Features at a glance

| Tool | Tab | What it does |
|---|---|---|
| [Separate to New Layer](#psart-sepcard) | PSArt · Layer Tools | One click: the character gets its own layer, and the scene behind is filled in. |
| [Extract Lines](#psart-linecard) | PSArt · Lineart | Turn pixel lineart into vector layers that stay sharp at any zoom. |
| [Repair](#psart-repaircard) | PSArt · Lineart | Join broken strokes and smooth wobbly ones. |
| [Line weight **Beta**](#psart-weightcard) | PSArt · Lineart | Make lines thinner or thicker in one click. |
| [Select](#psart-selectcard) | PSArt · Lineart | Lasso roughly; get a clean selection that hugs your lines. |
| [Clean AI Image **Beta**](#psart-cleancard) | PSArt · Clean | Calm AI image noise: steady line color, smooth edges, clean colors. |
| [Remove background](#psart-bgcard) | PSArt · Clean | One click erases a plain background, with a smooth edge, gaps included. |
| [Smooth Color Lines **Beta**](#psart-cfixcard) | PSArt · Clean | Smooth the lines of a color painting; colors stay put. |
| [Perspective Grid](#psart-gridcard) | PSArt · Perspective | Two rough strokes on a blank layer give a perspective grid to paint on. |
| [Redraw on grid](#psart-redrawcard) | PSArt · Perspective | Redraw a loose sketch straight along your grid, with true perspective circles. |
| [Export & Replace](#psart-replacecard) | PSArt · Layer Tools | Export a layer to PNG, edit it anywhere, Replace puts it back in place. |
| [Codex](#psart-codex) | PSArt · Codex | Chat with Codex inside Photoshop; send the selection, drop results back. |
| [Find PSD / PSB from image / PSD](#ym-find) | YourManager · Find | Drop an exported JPG or PNG; open its PSD in one click. |
| [Projects](#ym-projects) | YourManager · Projects | Save as usual; each new version lands on top of its project. |
| [Drag and drop](#ym-drag) | YourManager · Projects | Sort, merge, add. |
| [Untracked](#ym-untracked) | YourManager · Projects | Files in no project: click **All**, scroll to the bottom. |
| [ID inside the file](#ym-file_id) | YourManager · Projects | Rename, copy or move a PSD; it still knows its project and version. |
| [Action history](#ym-history) | YourManager · History | Changed your mind? Click any step to go back. |
| [Settings](#ym-settings) | YourManager · Settings | Choose what gets scanned, the language, and reset data. |

<a id="psart"></a>

## PSArt 1.5.2

**One Photoshop panel: split layers, vector lineart, clean AI images, perspective grids, Codex chat.**

Heavy tools run in the background. Hover any control for a short Help box.

<a href="https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.26b/PSArt_1.5.2.zip"><img alt="Download PSArt 1.5.2" src="https://img.shields.io/badge/Download-PSArt%201.5.2-2ea44f?style=for-the-badge"></a>

### Layer Tools

Cut a part of a layer onto its own layer, export / replace images.

<p align="center"><img src="docs/media/psart/panel_layers.png" alt="Layer Tools tab" width="300"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

<a id="psart-sepcard"></a>

#### Separate to New Layer

*One click: the character gets its own layer, and the scene behind is filled in.*

<p align="center"><img src="docs/media/psart/sepRun.gif" alt="A girl lassoed in a café street scene is split into two layers; moved away, a plain cut leaves a hole while PSArt has filled the wall behind her" width="720"></p>

**How to use**

1. Pick the painting in **Layer**.
2. Lasso the part.
3. Click **Separate to New Layer**.

<details><summary>Tips & limits</summary>

- The fill blends nearby colors; paint over big hidden areas by hand.

</details>

### Lineart

Redraw raster lines as vector layers, repair breaks, change line weight, select regions.

<p align="center"><img src="docs/media/psart/panel_lineart.png" alt="Lineart tab" width="300"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

<a id="psart-linecard"></a>

#### Extract Lines

*Turn pixel lineart into vector layers that stay sharp at any zoom.*

<p align="center"><img src="docs/media/psart/lineRun.gif" alt="A pencil-style scan: original, Photoshop Color Range on the black ink (simulated) with thin, broken lines, PSArt solid vector lines; whole figure, then zoomed" width="720"></p>

<p align="center"><img src="docs/media/psart/lineLayers.gif" alt="The 4 layers Extract Lines makes, Line core, Line faint, Line body and Line edge, shown one at a time in a Layers panel (drawn), then all 4 together; whole figure and a zoom on the hair" width="720"></p>

Lines come out as 4 layers, split by how dark the ink is: turn each on or off, or recolor it.

**How to use**

1. Pick the line layer in **Lineart**.
2. Set **Options** if needed.
3. Click **Extract Lines**.

<details><summary>Options / Tips & limits</summary>

**Options**

- **Close gaps** - Also bridge small breaks in the lines.
- **Auto colors** - Take the colors from the lineart itself; off uses the 4 swatches (core, faint, body, edge).

**Tips & limits**

- When it finishes, click Done on the bar to select the new layers.

</details>

<a id="psart-repaircard"></a>

#### Repair

*Join broken strokes and smooth wobbly ones.*

<p align="center"><img src="docs/media/psart/fixRun.gif" alt="Smooth Lines on a skirt pleat, zoomed in: lines of uneven weight become even" width="720"></p>

<p align="center"><img src="docs/media/psart/joinRun.gif" alt="Join line: 130 px erased from a leg line, lassoed, and joined back along the curve" width="720"></p>

**How to use**

1. Select the line layer.
2. Lasso the break or the wobbly part.
3. Click **Join line** or **Smooth Lines**.

<details><summary>Options / Tips & limits</summary>

**Options**

- **Keep corners** - Sharp bends stay sharp; off rounds them.
- **Strength** - 0 only smooths; higher redraws the lines cleaner; above 20 the curves get simpler and even.

**Tips & limits**

- Join line needs exactly two line ends inside the selection.

</details>

<a id="psart-weightcard"></a>

#### Line weight <sup><b>Beta</b></sup>

*Make lines thinner or thicker in one click.*

**How to use**

1. Select the line layer(s).
2. Pick the **Step**.
3. Click **Thinner** or **Thicker**.

<a id="psart-selectcard"></a>

#### Select

*Lasso roughly; get a clean selection that hugs your lines.*

<p align="center"><img src="docs/media/psart/fillSelect.gif" alt="A sloppy lasso over a jacket becomes a selection that hugs the lines; the jacket is then filled" width="720"></p>

**How to use**

1. Pick the lineart in Extract Lines.
2. Lasso over the areas.
3. Click **Select**, then paint.

<details><summary>Options</summary>

- **Reach** - How far a lasso reaches. Tight: only what it covers. Wide: whole regions, like Magic Wand.

</details>

### Clean

Clean AI images, remove plain backgrounds, smooth painted lines.

<p align="center"><img src="docs/media/psart/panel_clean.png" alt="Clean tab" width="300"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

<a id="psart-cleancard"></a>

#### Clean AI Image <sup><b>Beta</b></sup>

*Calm AI image noise: steady line color, smooth edges, clean colors.*

**How to use**

1. Select the AI image layer.
2. Set the line color if needed.
3. Click **Clean**.

<a id="psart-bgcard"></a>

#### Remove background

*One click erases a plain background, with a smooth edge, gaps included.*

<p align="center"><img src="docs/media/psart/bgRun.gif" alt="Remove background on a girl in a raincoat: usual steps by hand against one click, then a close-up of the edge, hard pixel edge (simulated) against PSArt" width="720"></p>

**How to use**

1. Select the image layer.
2. Leave **Background** on Auto.
3. Click **Remove**.

<details><summary>Options / Tips & limits</summary>

**Options**

- **Remove enclosed gaps** - Also erase background seen through closed gaps.
- **Smooth** - 0 keeps the edge as found; higher is smoother; 2-3 also rounds the corners.

**Tips & limits**

- Not for busy photo backgrounds.
- Pick Light or Dark when the subject touches the image edge.

</details>

<a id="psart-cfixcard"></a>

#### Smooth Color Lines <sup><b>Beta</b></sup>

*Smooth the lines of a color painting; colors stay put.*

**How to use**

1. Select the painting; lasso the lines.
2. Set **Strength**.
3. Click **Smooth**.

### Perspective

Make perspective grids from rough strokes and redraw sketches along them.

<p align="center"><img src="docs/media/psart/panel_persp.png" alt="Perspective tab" width="300"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

<a id="psart-gridcard"></a>

#### Perspective Grid

*Two rough strokes on a blank layer give a perspective grid to paint on.*

<p align="center"><img src="docs/media/psart/perspMake.gif" alt="A blank canvas: 2 rough strokes, Make grid (Straight) gives a 1-point grid, then a hallway painted on it" width="720"></p>

<p align="center"><img src="docs/media/psart/perspCurved.gif" alt="A blank canvas: 2 rough curves, Make grid (Curved) gives bent horizontals, then a street painted on them" width="720"></p>

**How to use**

1. Draw 2 rough strokes on a new layer.
2. Choose **Type** (Straight or Curved) and **Density**.
3. Click **Make grid**, then paint along it.

<details><summary>Options / Tips & limits</summary>

**Options**

- **Density** - How many grid lines; changing it redraws the grid layers selected in the Layers panel.

**Tips & limits**

- Run Curved twice, across and down, for 4-point curves.

</details>

<a id="psart-redrawcard"></a>

#### Redraw on grid

*Redraw a loose sketch straight along your grid, with true perspective circles.*

<p align="center"><img src="docs/media/psart/perspCircle.gif" alt="On a hallway grid, a rough circle on the floor and one on the wall become ellipses that fit their grid cell" width="720"></p>

**How to use**

1. Add and tick the grids (**+ Grid**).
2. Lasso the sketch part.
3. Click **Straighten** or **Perspective Circle**.

### Edit part of a picture with AI

<a id="psart-replacecard"></a>

#### Export & Replace

*Export a layer to PNG, edit it anywhere, Replace puts it back in place.*

<p align="center"><img src="docs/media/psart/editAI.gif" alt="A picture in layers: lasso and Export save a PNG to a folder; edited, Replace puts it back; or send it in the Codex tab and right-click the answer, Replace" width="720"></p>

**How to use**

1. Select an area, click **Export**: a PNG in your folder (no AI needed).
2. Edit the PNG in any app or AI.
3. Choose it, press **Replace**: it lands in the same frame.

<details><summary>Options / Tips & limits</summary>

**Options**

- **All visible layers** - Export one image of every visible layer, not just the selected one.
- **Transparent / Background** - Keep empty areas transparent, or fill them with the Background color.
- **Stretch to fit** - Stretch the image to the frame; off keeps its proportions.

**Tips & limits**

- Choose the **Export folder** with the gear button.

</details>

<a id="psart-codex"></a>

#### Codex

*Chat with Codex inside Photoshop; send the selection, drop results back.*

**How to use**

1. Click **Connect**.
2. Select an area, type your message.
3. Press **Send**; right-click the image you get back > **Replace**.

<details><summary>Tips & limits</summary>

- Needs the Codex app signed in with your ChatGPT account; other tabs work without it.

</details>

<p align="center"><img src="docs/media/psart/panel_codex.png" alt="Codex tab" width="300"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

<p align="right"><a href="#top">back to top</a></p>

<a id="ym"></a>

## YourManager 0.4.0

**Drop an exported image; YourManager opens the PSD it came from.**

Each PSD keeps a small ID inside it, so the panel still finds it after you rename, copy or move it. Everything stays on your PC.

<a href="https://github.com/DanhBoo/psart-plugin/releases/download/v2026.10.26b/YourManager_0.4.0.zip"><img alt="Download YourManager 0.4.0" src="https://img.shields.io/badge/Download-YourManager%200.4.0-2ea44f?style=for-the-badge"></a>

### Find

<a id="ym-find"></a>

#### Find PSD / PSB from image / PSD

*Drop an exported JPG or PNG; open its PSD in one click.*

<p align="center"><img src="docs/media/ym/messy_to_psd.gif" alt="Badly named folders in Explorer; char_FINAL.jpg dropped on Find; Open; char_new_FIX.psd opens in Photoshop and its row is picked in Projects" width="820"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

**Scan IDs** reads the ID inside every PSD and image in your scan folders once, so a dropped image finds its PSD. **Rescan IDs** reads only new or changed files; YourManager does it by itself when you open Find and the last scan is over 10 minutes old.

**How to use**

1. **Settings**: add the folders that hold your PSDs.
2. **Find**: click **Scan IDs** once.
3. Drop an image on the box, click **Open**.

<details><summary>Tips & limits</summary>

- Works best on images exported from Photoshop.

</details>

### Projects

<a id="ym-projects"></a>

#### Projects

*Save as usual; each new version lands on top of its project.*

<p align="center"><img src="docs/media/ym/versions_on_save.gif" alt="Save As character_v05.psd: v5 appears on top of the Character project" width="360"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

**How to use**

1. Save As a new name for each version.
2. Double-click a version to open it.

<details><summary>Options / Tips & limits</summary>

**Options**

- **Right-click a version** - Open, show in folder, rename, move, delete (to Recycle Bin).

**Tips & limits**

- Renaming or moving an open file: the plugin saves, closes and reopens it.

</details>

<a id="ym-drag"></a>

#### Drag and drop

*Sort, merge, add.*

<p align="center"><img src="docs/media/ym/drag_projects.gif" alt="Drag Logo above Character; drop Landscape on Poster (merged); All: drag mug_icon from Untracked onto Logo (added)" width="360"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

<a id="ym-untracked"></a>

#### Untracked

*Files in no project: click **All**, scroll to the bottom.*

<p align="center"><img src="docs/media/ym/untracked_track.gif" alt="Projects > All > scroll down to Untracked > right-click tree_color > Track > it is a project on top" width="360"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

**How to use**

1. Right-click a group under **Untracked**.
2. Click **Track**: it becomes a project.

<details><summary>Tips & limits</summary>

- **Untrack** on a project sends it back to Untracked.

</details>

<a id="ym-file_id"></a>

#### ID inside the file

*Rename, copy or move a PSD; it still knows its project and version.*

<p align="center"><img src="docs/media/ym/rename_keeps_id.gif" alt="character_v02.psd renamed in Explorer, then opened: the row becomes character_lineart.psd, still v2" width="360"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

### History

<p align="center"><img src="docs/media/ym/panel_history.png" alt="History tab with three actions, the last one undone" width="360"></p>

<p align="center"><sub>mock-up, not a Photoshop screenshot</sub></p>

<a id="ym-history"></a>

#### Action history

*Changed your mind? Click any step to go back.*

**How to use**

1. Click a row to go back to it.
2. Click a faded row to redo.

### Settings

<a id="ym-settings"></a>

#### Settings

*Choose what gets scanned, the language, and reset data.*

<details><summary>Options / Tips & limits</summary>

**Options**

- **Notifications > Ask on save** - Saving a version that is not on top asks: **Yes, move to top** or **No**.

**Tips & limits**

- Delete `%APPDATA%\YourManager` to uninstall completely.

</details>

<p align="right"><a href="#top">back to top</a></p>

## What's new

### PSArt 1.5.2

- Join line follows the line across a dashed gap instead of jumping to a nearby line. ([→](#psart-repaircard))

- A closed or collapsed panel does nothing in the background.

### YourManager 0.4.0

- Newest project on top: projects are sorted by the day they were created. ([→](#ym-projects))

- **All** also lists **Untracked**: scanned files in no project, grouped by source file. **Track** makes one a project. ([→](#ym-untracked))

- Drag a group or file onto a project to add it; drag a project onto another to merge. ([→](#ym-drag))

- **Not in this project** and **Untrack** send files back to Untracked (undo in History). ([→](#ym-projects))

- Find: opening a file that is in no project makes it a project on top, with its whole group. ([→](#ym-find))

## FAQ

<details><summary><b>Does it work on macOS?</b></summary>

Not yet. Both plugins are built and tested on Windows only.
</details>

<details><summary><b>Is my artwork uploaded anywhere?</b></summary>

PSArt's drawing tools and YourManager work on your PC only. Only the PSArt Codex tab sends something out: the message and the selection you send, to Codex under your own ChatGPT account.
</details>

<details><summary><b>Something went wrong. What should I send?</b></summary>

The line of text at the bottom of the panel, your Photoshop version, and what you clicked.
</details>

<details><summary><b>PSArt asks to run start_bridge.vbs. Is that needed?</b></summary>

Only for the Codex tab. Click Deny if you do not use Codex; the other tabs work normally.
</details>

<details><summary><b>Does YourManager change my PSD files?</b></summary>

It only adds a small project code to the file info (XMP) when you save. Layers and pixels are not touched.
</details>

## Contact
This is a test release for friends. Report problems or ideas in [Issues](https://github.com/DanhBoo/psart-plugin/issues) or message the author directly.
