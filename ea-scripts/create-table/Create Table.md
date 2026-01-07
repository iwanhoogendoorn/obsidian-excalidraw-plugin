/*

Creates a table with customizable rows and columns.

```javascript
*/

// Prompt for number of rows
const rowsInput = await utils.inputPrompt("Rows", "Number of rows", "3");
if (!rowsInput) return;
const rows = parseInt(rowsInput) || 3;

// Prompt for number of columns  
const colsInput = await utils.inputPrompt("Columns", "Number of columns", "3");
if (!colsInput) return;
const cols = parseInt(colsInput) || 3;

// Prompt for cell width
const widthInput = await utils.inputPrompt("Cell Width", "Width in pixels", "100");
if (!widthInput) return;
const cellWidth = parseInt(widthInput) || 100;

// Prompt for cell height
const heightInput = await utils.inputPrompt("Cell Height", "Height in pixels", "40");
if (!heightInput) return;
const cellHeight = parseInt(heightInput) || 40;

// Table dimensions
const tableWidth = cols * cellWidth;
const tableHeight = rows * cellHeight;

// Clear previous EA state
ea.reset();

// Group ID
const groupId = ea.generateElementId();

// Set style for inner cells (thinner lines)
ea.style.strokeColor = "#1e1e1e";
ea.style.backgroundColor = "transparent";
ea.style.fillStyle = "hachure";
ea.style.roughness = 0; // Architect mode
ea.style.strokeWidth = 1;

// Create inner cell rectangles
for (let r = 0; r < rows; r++) {
    for (let c = 0; c < cols; c++) {
        ea.addRect(c * cellWidth, r * cellHeight, cellWidth, cellHeight);
    }
}

// Set style for outer border (thicker line)
ea.style.strokeWidth = 3;

// Add outer border rectangle on top
ea.addRect(0, 0, tableWidth, tableHeight);

// Group all elements
ea.getElements().forEach(el => {
    el.groupIds = [groupId];
});

// Add to view
await ea.addElementsToView(true, false);
