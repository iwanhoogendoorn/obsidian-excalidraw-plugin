# Create Table - Excalidraw Script

An Obsidian Excalidraw script that generates customizable tables with a clean grid layout, colored headers, and flexible styling options.

![Video](video.gif)

## Features

- **Table Creation Wizard** - Step-by-step guided setup (8 steps)
- **Custom dimensions** - Specify the number of rows and columns
- **Adjustable cell size** - Set custom width and height for cells
- **Customizable borders** - Control outer border and inner line thickness
- **Column header color** - Highlight the first row with a background color
- **Row header color** - Highlight the first column with a background color
- **Professional styling** - Architect mode for clean, precise lines
- **Auto-grouped** - All elements are grouped for easy repositioning

## Installation

1. Copy `Create Table.md` to your Excalidraw scripts folder:
   ```
   .obsidian/plugins/obsidian-excalidraw-plugin/scripts/
   ```

2. Restart Obsidian or reload the Excalidraw plugin

3. The script will appear in the Excalidraw scripts menu

## Usage

1. Open any Excalidraw drawing in Obsidian
2. Run the script from the scripts menu (or use the command palette)
3. Follow the 8-step wizard:

| Step | Setting | Description | Default |
|------|---------|-------------|---------|
| 1/8 | **Rows** | Number of rows | 4 |
| 2/8 | **Columns** | Number of columns | 4 |
| 3/8 | **Cell Width** | Width in pixels | 120 |
| 4/8 | **Cell Height** | Height in pixels | 50 |
| 5/8 | **Outer Border** | Border thickness in pixels | 3 |
| 6/8 | **Inner Lines** | Line thickness in pixels | 1 |
| 7/8 | **Column Header Color** | Background color for first row | Light Blue |
| 8/8 | **Row Header Color** | Background color for first column | Light Orange |

4. The table will be created and automatically selected

## Header Colors

Choose from these color options for column and row headers:

| Color | Hex Code |
|-------|----------|
| None (transparent) | `transparent` |
| Light Blue | `#e3f2fd` |
| Light Orange | `#fff3e0` |
| Light Green | `#e8f5e9` |
| Light Purple | `#f3e5f5` |
| Light Yellow | `#fffde7` |
| Light Red | `#ffebee` |
| Light Gray | `#f5f5f5` |
| Light Teal | `#e0f2f1` |
| Light Pink | `#fce4ec` |
| Light Indigo | `#e8eaf6` |

**Note:** The top-left cell uses the column header color when both headers are enabled.

## Example

Creating a 5x4 table with colored headers:

| Setting | Value |
|---------|-------|
| Rows | 5 |
| Columns | 4 |
| Cell Width | 150 |
| Cell Height | 40 |
| Outer Border | 4 |
| Inner Lines | 1 |
| Column Header | Light Blue |
| Row Header | Light Green |

## Styling

The table is created with:
- **Inner lines**: Customizable stroke width (default: 1px)
- **Outer border**: Customizable stroke width (default: 3px)
- **Line style**: Architect (clean, no roughness)
- **Stroke color**: Dark gray (#1e1e1e)
- **Fill style**: Solid (for header backgrounds)

## Tips

- Press **Enter** on any prompt to accept the default value
- Press **Escape** to cancel the wizard at any step
- After creation, the table is grouped - double-click to edit individual cells
- Use Excalidraw's styling tools to change colors after creation
- Set both header colors to "None (transparent)" for a plain table
- Minimum values: 1 row/column, 20px cell dimensions, 1px line thickness

## License

MIT License


