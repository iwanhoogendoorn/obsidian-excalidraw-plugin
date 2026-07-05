# Comicbook Strip Director

An Excalidraw Script Engine script that turns the Obsidian + Excalidraw canvas into a
comic-strip studio: drop a panel layout, fill the panels with hand-drawn characters in
any costume and pose, then punch it up with painted sound-effect FX — no drawing
skills required.

**The free tier ships in this folder** (see [`free/`](free/)): the 8-character Core
Cast, 30 panel-layout templates, and 3 painted FX. More characters, costumes, themes
and the full FX set: **[comicstripdirector.com](https://comicstripdirector.com/)**.

## Features

- **Visual layout picker** — 30 named panel templates (grids, manga tiers, dynamic
  angled gutters, splash pages) in landscape / portrait / square, plus a parametric
  generator for any panel count. Each new page stacks below the previous one.
- **Polygon panels** — angled / diagonal / wedge pages, not just rectangular grids.
- **Split the selected panel** — local diagonal / horizontal action-beat cuts; each
  region is its own placement target.
- **Character system** — place characters by *who × costume × action*. The picker
  shows only combinations from the packs you've imported, every tile with a real
  thumbnail, plus per-character show/hide (**⚙ Manage**).
- **Pack import** — install `.strippack` character and FX packs. Imports are
  idempotent and de-duplicated, and index files are backed up before every merge.
- **Painted FX callouts** — POW! BOOM! ZAP! stamped straight into the selected panel.
- **Reserved callout zones** — composes with the
  [Comicbook Callout Editor](https://github.com/zsviczian/obsidian-excalidraw-plugin/blob/master/ea-scripts/Comicbook%20Callout%20Editor.md)
  for speech bubbles (never touches its data).

Everything the script draws is tagged `customData.stripDirector`; it never modifies
`comicCallout`.

## Install

1. Install the **Obsidian Excalidraw plugin** (2.19.1 or higher) and enable the
   **Script Engine**.
2. Copy both files into your Excalidraw scripts folder (set under
   *Excalidraw → Settings → Script Engine*):
   - [`Comicbook Strip Director (Library).md`](Comicbook%20Strip%20Director%20(Library).md)
   - [`Comicbook Strip Director (Library).svg`](Comicbook%20Strip%20Director%20(Library).svg)
     (the toolbar icon — keep the same basename)
3. Reload Excalidraw scripts and run **Comicbook Strip Director** from the script menu.

### Add the free content

| File in [`free/`](free/) | What it is | How to use |
|---|---|---|
| `core-free.strippack` | The 8 founding characters (Mia, Walt, Priya, Sam, Dr. Nadia, Rico, Grace, Felix) in every base pose | Put it anywhere in your vault → script panel → **⬇ Import pack…** |
| `comic-fx-free.strippack` | 3 painted FX: POW! BOOM! ZAP! (PNG + SVG) | Put it in your vault → **⬇ Import FX pack…** |
| `layouts-free.zip` | 30 blank page templates as SVG + PNG | The script has all 30 built in — this zip is for using them in *other* tools (Miro, Google Drawings, Figma, …) |

Premium packs install exactly the same way — get them at
[comicstripdirector.com](https://comicstripdirector.com/), drop the `.strippack` in
your vault, and import.

## License

The script is MIT-licensed (see [LICENSE](LICENSE)). The bundled free content
(characters, layouts, FX) may be used freely in your own comics, personal or
commercial; redistribution or resale of the packs themselves is not permitted.
