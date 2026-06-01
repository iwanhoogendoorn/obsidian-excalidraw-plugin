# Color Scheme Manager - Excalidraw Script

An Obsidian Excalidraw script that swaps the entire **Stroke** and **Background/Fill** colour palettes of the active drawing between named, categorized themes — on the fly, from a docked side panel. Comes with a large built-in library (Cloud Providers, Code Editors, Tech Brands, Design Systems, and more) and lets you create or import your own.

![icon](Color%20Scheme%20Manager.svg)

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

| Button | Action |
|--------|--------|
| **+ New scheme** | Pick a stroke + fill; a full 10-accent palette is auto-synthesized |
| **Import** | Paste hex codes (2 = stroke+fill, 6+ = a full theme); lands in **Custom** |
| **Add presets** | Pull in any built-in themes you don't already have |
| **Save selection** | Capture the stroke/fill of the currently selected element as a new scheme |
| **Load all → picker** | Load every saved scheme's colours into the picker at once |
| **Reset picker** | Restore Excalidraw's default palette |
| ✎ / 🗑 (per row) | Rename / delete a scheme |
| `↺ Default` row | Reset the picker to Excalidraw defaults |

## Creating & Importing

- **New scheme:** choose a stroke and a fill — the script builds a coherent 10-accent family (analogous hues + tonal range) so you still get the full 15-swatch grid.
- **Import:** paste hex values separated by spaces, commas, or newlines. 6+ colours are used as-is (cycled to 10); 2–5 are expanded into a harmonious spread. Works directly with a Paletton text export.

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
- Deleting a built-in theme is fine — it won't be re-added (a version flag tracks the one-time merge).

## License

MIT License
