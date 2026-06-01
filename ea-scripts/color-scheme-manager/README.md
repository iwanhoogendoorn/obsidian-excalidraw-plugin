# Color Scheme Manager - Excalidraw Script

An Obsidian Excalidraw script that swaps the entire **Stroke** and **Background/Fill** colour palettes of the active drawing between named, categorized themes — on the fly, from a docked side panel. Comes with a large built-in library (Cloud Providers, Code Editors, Tech Brands, Design Systems, and more) and lets you create or import your own.

![Video](Color%20Scheme%20Manager.gif)

## Features

- **Docked side panel** - Browse and apply schemes without leaving your drawing
- **Categorized library** - A **Category** dropdown filters ~60 built-in themes across 8 categories
- **Full 15-swatch palettes** - Every scheme populates the picker's extended grid (3×5) *and* the toolbar quick-pick rows, each swatch with a light→dark shade ramp
- **Stroke + Fill only** - Themes the element Stroke and Background/Fill palettes; the **canvas background is always left untouched (white)**
- **Smart apply** - With elements selected it recolours them; with nothing selected it sets the active stroke/fill for the next elements you draw
- **Create your own** - Pick two colours and a full 10-accent palette is auto-synthesized
- **Import** - Paste hex codes (e.g. a [Paletton](https://paletton.com) "as text" export) to build a scheme/theme instantly
- **Active indicator** - The currently applied scheme is highlighted with a ▸ marker (persists across reloads)
- **Reset** - A `↺ Default` entry restores Excalidraw's built-in palette
- **Persistent** - All schemes (built-in + custom) are saved in the plugin's script settings

## Installation

1. Copy `Color Scheme Manager.md` to your Excalidraw scripts folder:
   ```
   .obsidian/plugins/obsidian-excalidraw-plugin/scripts/
   ```
   (or your configured Excalidraw *Scripts folder*)

2. Restart Obsidian or reload the Excalidraw plugin

3. The script will appear in the Excalidraw scripts menu

> Requires Excalidraw plugin **2.19.1** or higher.

## Usage

1. Open any Excalidraw drawing in Obsidian
2. Run **Color Scheme Manager** from the scripts menu (or the command palette) — a **Color Schemes** side panel docks open
3. Use the **Category** dropdown to filter the list
4. **Click a scheme's name** to apply it
5. **Reopen the colour picker** to see the refreshed extended grid (Excalidraw caches the open popover)

### What happens when you apply a scheme

| Context | Result |
|---------|--------|
| Elements selected | Their **stroke** and **fill** are recoloured |
| Nothing selected | The **active** stroke/fill is set for the next elements you draw |
| Always | The native picker (quick-pick rows + extended 3×5 grid) is repainted with the scheme's family |
| Never | The canvas background colour is left as-is |

## Built-in Library

| Category | Examples |
|----------|----------|
| **Cloud Providers** | Oracle Redwood, AWS, Microsoft Azure, Google Cloud, IBM Cloud, DigitalOcean, Alibaba Cloud |
| **Code Editors** | Nord, Dracula, Solarized, Monokai, Gruvbox, One Dark, Tokyo Night, Catppuccin, Ayu |
| **Tech Brands** | GitHub, Slack, Spotify, Discord, Stripe, Figma, Twitch, Netflix, Firefox, Notion |
| **Design Systems** | Material, Tailwind, Bootstrap, Fluent, Carbon, Ant Design |
| **Nature** | Ocean, Forest, Sunset, Autumn, Desert, Arctic, Coral Reef, Lavender |
| **Solids** | Teal, Amber, Crimson, Violet, Rose, Indigo, Emerald, Slate |
| **Vibrant** | Cyberpunk, Neon, Synthwave, Pastel, Candy, Tropical |
| **Minimal** | Mono, Mono Ink, Blueprint, Sepia, Grayscale |

## Panel Controls

| Control | Action |
|---------|--------|
| ℹ️ (top, next to title) | Toggle the **About** description |
| **Category** dropdown | Filter the list by category (your choice is remembered) |
| **+ New scheme** | Pick a stroke + fill, then choose a category; a full 10-accent palette is auto-synthesized |
| **Import** | Paste hex codes (2 = stroke+fill, 6+ = a full theme), then choose a category |
| **Sample format** | Download a template `.txt` showing exactly what Import expects |
| **Add presets** | Pull in any built-in themes you don't already have |
| **Save selection** | Capture the stroke/fill of the currently selected element as a new scheme |
| **Load all → picker** | Load every saved scheme's colours into the picker at once |
| **Reset picker** | Restore Excalidraw's default palette |
| 🎚️ (per row) | **Customize picker** — hand-pick the exact swatches, order, and top-picks |
| ✎ (per row) | Rename **and/or** change the scheme's category |
| 🗑 (per row) | Delete the scheme (asks for confirmation) |
| `↺ Default` row | Reset the picker to Excalidraw defaults |

## Adding your own schemes

There are three ways to add a scheme — each one then prompts you for a category:

- **+ New scheme** — choose a stroke and a fill in the native colour pickers. The script builds a coherent 10-accent family (analogous hues + tonal range) so you still get the full 15-swatch grid.
- **Import** — paste colours in either a simple flat list (script derives stroke/fill) or the labelled `STROKE:`/`FILL:` format for full control. Works directly with a [Paletton](https://paletton.com) "as text" export. See **Import format** below.
- **Save selection** — select a styled element on the canvas, then click *Save selection* to capture its stroke and fill.

### Import format

Click **Sample format** in the panel to download a ready-to-edit template (`color-scheme-import-sample.txt`). There are **two ways** to import.

**Stroke / Fill / Canvas** map to Excalidraw's three colour pickers. In this script the **canvas background is always white and not editable**, so you only ever define **stroke** and **fill**. Each picker grid holds up to **15 swatches = 3 rows × 5 columns** (the first 5 you list are row 1, the next 5 row 2, the next 5 row 3), and every swatch gets an automatic light→dark shade ramp.

Hex is 6 digits, the leading `#` is optional, and `transparent` / `black` / `white` are allowed as names.

#### Option A — Simple (one flat list)

Paste a single list; the script derives stroke and fill for you.

- **2–5** colours → a scheme (1st = stroke, 2nd = fill), auto-expanded to 15.
- **6+** colours → a theme (first 10 used). Stroke = your colours + dark shades; Fill = lighter tints.

```text
5E81AC 81A1C1 88C0D0 8FBCBB A3BE8C B48EAD BF616A D08770 EBCB8B 4C566A
```

#### Option B — Full control (labelled stroke + fill)

Label each picker explicitly. `STROKE:` and `FILL:` take up to 15 colours each (3×5); `TOPPICKS_*` are the 5 quick swatches shown before the grid opens (optional). `NAME:` and `CATEGORY:` are optional (you'll be prompted if omitted).

```text
NAME: My Full Theme
CATEGORY: Custom

# STROKE picker — 15 colours = 3 rows x 5 columns
STROKE:
1E1E1E 5E81AC 81A1C1 88C0D0 8FBCBB
A3BE8C B48EAD BF616A D08770 EBCB8B
4C566A 2E3440 3B4252 434C5E D8DEE9

# FILL picker — 15 colours = 3 rows x 5 columns
FILL:
transparent D8DEE9 E5E9F0 ECEFF4 C0D0E0
CFE8CF E8D6E8 F4C7C3 F5D9C8 F7ECC9
EBEEF3 C2C9D6 CDD3DE D6DBE5 B9C2D0

# Quick-pick rows — 5 colours each (optional)
TOPPICKS_STROKE: black 5E81AC BF616A A3BE8C EBCB8B
TOPPICKS_FILL: transparent E5E9F0 F4C7C3 CFE8CF F7ECC9
```

## Customizing the picker

If you don't want *all* of a scheme's colours loaded, or want a different order than the auto-generated one, click the **🎚️** button on a scheme row to open the **Customize picker** editor. It works on any scheme (built-in or your own) and edits four lists:

- **Stroke grid** and **Fill grid** — up to 15 swatches each (3 rows × 5).
- **Stroke top-picks** and **Fill top-picks** — the 5 quick swatches shown before the grid opens.

In each list you can:

- **+ Add colour** via Excalidraw's native picker,
- **click a swatch** to change it,
- **drag the ⠿ handle** to reorder (drag-and-drop),
- **✕** to remove.

A live preview strip shows each list as you edit.

- **Save** stores the exact spec on the scheme (so applying it loads precisely those colours, in that order).
- **↺ Revert to default** restores a built-in scheme's original colours (stroke / fill / accents) and clears the custom picker — the clean way to undo edits. (For your own schemes, it just clears the picker.)
- **Load from theme…** copies any other theme's default colours into the editor as a starting point.

The canvas background always stays white.

> Tip: the labelled **Import** format (Option B above) writes the same spec — the editor is just the visual way to do it.

## Categories

- The **Category** dropdown at the top filters which schemes are shown.
- Built-in themes ship with a fixed category (Cloud Providers, Code Editors, etc.). New and imported schemes default to **Custom**.
- **Assign a category** when creating/importing (pick an existing one or choose **＋ New category…** to type a brand-new name), or change it later with the **✎** button on any row — this works on built-in themes too.
- A category exists only while at least one scheme uses it. **Move or delete the last scheme in a category and that category disappears from the dropdown** automatically — there is no separate "delete category" step.

## Deleting

- Click the **🗑** on a row to delete that scheme (you'll be asked to confirm).
- Deleting a **built-in** theme is fine — it will **not** be re-added on the next run (a version flag tracks the one-time merge of built-ins).
- To wipe everything and start over, delete the `Color Scheme Manager` entry under `scriptEngineSettings` in `data.json` (see below) while Obsidian is closed; the built-ins will be re-seeded on next run.

## Where schemes are stored

All schemes (built-in and custom) live together in the plugin's script settings:

```
.obsidian/plugins/obsidian-excalidraw-plugin/data.json
  → scriptEngineSettings → "Color Scheme Manager" → "Saved Schemes (JSON)"
```

Back up or move that value to transfer your library.

## Tips

- The colour picker caches while open — **close and reopen it** to see a newly applied palette.
- The first cell of each picker stays **transparent**; **black** and **white** are kept as fixed anchors. Every other swatch is theme-derived.
- Press **Escape** to cancel any prompt.
- Use the ℹ️ button at the top of the panel for a quick in-app description.

## License

MIT License
