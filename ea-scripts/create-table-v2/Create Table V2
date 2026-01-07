/*

Table Creation Wizard - Creates a customizable table with headers and styling options.

```javascript
*/

// ============================================
// TABLE CREATION WIZARD
// ============================================

// Default values
const defaults = {
    rows: 4,
    cols: 4,
    cellWidth: 120,
    cellHeight: 50,
    outerBorder: 3,
    innerLine: 1,
    columnHeaderColor: "#e3f2fd",
    rowHeaderColor: "#fff3e0"
};

// Color palette for header selection
const colorOptions = [
    { name: "None (transparent)", value: "transparent" },
    { name: "Light Blue", value: "#e3f2fd" },
    { name: "Light Orange", value: "#fff3e0" },
    { name: "Light Green", value: "#e8f5e9" },
    { name: "Light Purple", value: "#f3e5f5" },
    { name: "Light Yellow", value: "#fffde7" },
    { name: "Light Red", value: "#ffebee" },
    { name: "Light Gray", value: "#f5f5f5" },
    { name: "Light Teal", value: "#e0f2f1" },
    { name: "Light Pink", value: "#fce4ec" },
    { name: "Light Indigo", value: "#e8eaf6" }
];

// ============================================
// WIZARD PROMPTS
// ============================================

// 1. Number of rows
const rowsInput = await utils.inputPrompt(
    "Table Wizard (1/8): Rows",
    "Enter number of rows",
    String(defaults.rows)
);
if (!rowsInput) return;
const rows = Math.max(1, parseInt(rowsInput) || defaults.rows);

// 2. Number of columns
const colsInput = await utils.inputPrompt(
    "Table Wizard (2/8): Columns",
    "Enter number of columns",
    String(defaults.cols)
);
if (!colsInput) return;
const cols = Math.max(1, parseInt(colsInput) || defaults.cols);

// 3. Cell width
const widthInput = await utils.inputPrompt(
    "Table Wizard (3/8): Cell Width",
    "Width in pixels",
    String(defaults.cellWidth)
);
if (!widthInput) return;
const cellWidth = Math.max(20, parseInt(widthInput) || defaults.cellWidth);

// 4. Cell height
const heightInput = await utils.inputPrompt(
    "Table Wizard (4/8): Cell Height",
    "Height in pixels",
    String(defaults.cellHeight)
);
if (!heightInput) return;
const cellHeight = Math.max(20, parseInt(heightInput) || defaults.cellHeight);

// 5. Outer border thickness
const outerBorderInput = await utils.inputPrompt(
    "Table Wizard (5/8): Outer Border",
    "Border thickness in pixels",
    String(defaults.outerBorder)
);
if (!outerBorderInput) return;
const outerBorderWidth = Math.max(1, parseInt(outerBorderInput) || defaults.outerBorder);

// 6. Inner line thickness
const innerLineInput = await utils.inputPrompt(
    "Table Wizard (6/8): Inner Lines",
    "Line thickness in pixels",
    String(defaults.innerLine)
);
if (!innerLineInput) return;
const innerLineWidth = Math.max(1, parseInt(innerLineInput) || defaults.innerLine);

// 7. Column header color
const columnHeaderChoice = await utils.suggester(
    colorOptions.map(c => c.name),
    colorOptions.map(c => c.value),
    "Table Wizard (7/8): Column Header Color"
);
if (columnHeaderChoice === undefined) return;
const columnHeaderColor = columnHeaderChoice;

// 8. Row header color
const rowHeaderChoice = await utils.suggester(
    colorOptions.map(c => c.name),
    colorOptions.map(c => c.value),
    "Table Wizard (8/8): Row Header Color"
);
if (rowHeaderChoice === undefined) return;
const rowHeaderColor = rowHeaderChoice;

// ============================================
// TABLE GENERATION
// ============================================

// Calculate table dimensions
const tableWidth = cols * cellWidth;
const tableHeight = rows * cellHeight;

// Clear previous EA state
ea.reset();

// Generate group ID for all elements
const groupId = ea.generateElementId();

// Base style settings
ea.style.strokeColor = "#1e1e1e";
ea.style.fillStyle = "solid";
ea.style.roughness = 0; // Architect mode (clean lines)

// ============================================
// CREATE CELLS
// ============================================

// Create all cells with appropriate styling
for (let r = 0; r < rows; r++) {
    for (let c = 0; c < cols; c++) {
        const x = c * cellWidth;
        const y = r * cellHeight;
        
        // Determine cell background color
        let bgColor = "transparent";
        
        // First row = column header
        if (r === 0 && columnHeaderColor !== "transparent") {
            bgColor = columnHeaderColor;
        }
        // First column = row header (but not if it's also the column header)
        else if (c === 0 && r > 0 && rowHeaderColor !== "transparent") {
            bgColor = rowHeaderColor;
        }
        
        // Set style for this cell
        ea.style.backgroundColor = bgColor;
        ea.style.strokeWidth = innerLineWidth;
        
        // Add the cell rectangle
        ea.addRect(x, y, cellWidth, cellHeight);
    }
}

// ============================================
// CREATE OUTER BORDER
// ============================================

// Set style for outer border (thicker line, no fill)
ea.style.strokeWidth = outerBorderWidth;
ea.style.backgroundColor = "transparent";

// Add outer border rectangle on top
ea.addRect(0, 0, tableWidth, tableHeight);

// ============================================
// GROUP & ADD TO VIEW
// ============================================

// Group all elements together
ea.getElements().forEach(el => {
    el.groupIds = [groupId];
});

// Add to view (centered on cursor)
await ea.addElementsToView(true, false);
