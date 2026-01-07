# Create Table - Excalidraw Script

An Obsidian Excalidraw script that generates customizable tables with a clean grid layout.

## Features

- **Custom dimensions** - Specify the number of rows and columns
- **Adjustable cell size** - Set custom width and height for cells
- **Professional styling** - Architect mode for clean, precise lines
- **Emphasized borders** - Outer border is thicker than inner grid lines
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
3. Enter the following when prompted:
   - **Rows** - Number of rows (default: 3)
   - **Columns** - Number of columns (default: 3)
   - **Cell Width** - Width in pixels (default: 100)
   - **Cell Height** - Height in pixels (default: 40)
4. The table will be created and automatically selected

## Example

Creating a 4x3 table with 120px wide and 50px tall cells:

| Prompt | Value |
|--------|-------|
| Rows | 4 |
| Columns | 3 |
| Cell Width | 120 |
| Cell Height | 50 |

## Styling

The table is created with:
- **Inner lines**: 1px stroke width
- **Outer border**: 3px stroke width
- **Line style**: Architect (clean, no roughness)
- **Color**: Dark gray (#1e1e1e)

## Tips

- Press **Enter** on any prompt to accept the default value
- After creation, the table is grouped - double-click to edit individual cells
- Use Excalidraw's styling tools to change colors after creation

## Related Scripts

- `Align Text Boxes Horizontally.md` - Align multiple text elements on the same horizontal line

## License

Free to use and modify.

