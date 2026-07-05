# Comicbook Strip Director

An Excalidraw Script Engine script that turns the Obsidian + Excalidraw canvas into a
comic-strip studio: drop a panel layout, fill the panels with hand-drawn characters in
any costume and pose, then punch it up with painted sound-effect FX — no drawing
skills required.

**The free tier comes preinstalled**: the 8-character Core Cast (176 poses), all 30
panel layouts, and 3 painted FX (POW! BOOM! ZAP!) work out of the box — no imports,
no extra downloads. More characters, costumes, themes and the full FX set:
**[comicstripdirector.com](https://comicstripdirector.com/)**.

## Features

- **Visual layout picker** — 30 named panel templates (grids, manga tiers, dynamic
  angled gutters, splash pages) in landscape / portrait / square, plus a parametric
  generator for any panel count. Each new page stacks below the previous one.
- **Polygon panels** — angled / diagonal / wedge pages, not just rectangular grids.
- **Split the selected panel** — local diagonal / horizontal action-beat cuts; each
  region is its own placement target.
- **Character system** — place characters by *who × costume × action*. The picker
  shows only combinations from the packs you own, every tile with a real thumbnail,
  plus per-character show/hide (**⚙ Manage**).
- **Pack import** — install `.strippack` character and FX add-on packs. Imports are
  idempotent and de-duplicated, and index files are backed up before every merge.
- **Painted FX callouts** — POW! BOOM! ZAP! stamped straight into the selected panel,
  crisp SVG preferred automatically.
- **Reserved callout zones** — composes with the
  [Comicbook Callout Editor](https://github.com/zsviczian/obsidian-excalidraw-plugin/blob/master/ea-scripts/Comicbook%20Callout%20Editor.md)
  for speech bubbles (never touches its data).

Everything the script draws is tagged `customData.stripDirector`; it never modifies
`comicCallout`.

## Install

1. Install the **Obsidian Excalidraw plugin** (2.19.1 or higher) and enable the
   **Script Engine**.
2. Copy **all three** items into your Excalidraw scripts folder (set under
   *Excalidraw → Settings → Script Engine*):
   - `Comicbook Strip Director (Library).md` — the script
   - `Comicbook Strip Director (Library).svg` — the toolbar icon (keep the basename)
   - `Comicbook Strip Director (Library)/` — the **data folder** with the free
     characters and FX (this is what makes the free tier work out of the box)
3. Reload Excalidraw scripts and run **Comicbook Strip Director** from the script
   menu. The Core Cast and free FX are already in the picker.

> Easiest way to grab everything: **Code → Download ZIP** on this repo (or clone),
> then copy this script's folder contents as above.

### Extras

- [`free/layouts-free.zip`](free/layouts-free.zip) — the 30 page templates as
  standalone SVG + PNG, for use in *other* tools (Miro, Google Drawings, Figma, …).
  The script itself has all 30 built in.
- **Add-on packs** — get them at [comicstripdirector.com](https://comicstripdirector.com/),
  drop the `.strippack` anywhere in your vault, then use **⬇ Import pack…** /
  **⬇ Import FX pack…** in the script panel.

## License

The script is MIT-licensed (see [LICENSE](LICENSE)). The bundled free content
(characters, layouts, FX) may be used freely in your own comics, personal or
commercial; redistribution or resale of the content packs themselves is not permitted.
