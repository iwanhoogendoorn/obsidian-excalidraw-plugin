/*

Aligns multiple text boxes on the same horizontal line.
Select multiple text elements, then choose an alignment option:
- Top: Align all text boxes to the topmost element's position
- Middle: Align all text boxes to the vertical center of the selection
- Bottom: Align all text boxes to the bottommost element's position
- First Selected: Align all text boxes to the first selected element's position

```javascript
*/

// Get all selected text elements
const elements = ea.getViewSelectedElements().filter((el) => el.type === "text");

// Check if we have enough elements to align
if (elements.length < 2) {
    new Notice("Please select at least 2 text elements to align horizontally");
    return;
}

// Calculate bounding box values
const topY = Math.min(...elements.map((el) => el.y));
const bottomY = Math.max(...elements.map((el) => el.y + el.height));
const middleY = (topY + bottomY) / 2;
const firstY = elements[0].y;
const firstMiddleY = elements[0].y + elements[0].height / 2;

// Alignment options
const alignOptions = [
    "Top - align to topmost element",
    "Middle - align to vertical center",
    "Bottom - align to bottommost element",
    "First Selected - align to first element"
];

const alignValues = ["top", "middle", "bottom", "first"];

// Show suggester to pick alignment type
const selectedAlign = await utils.suggester(alignOptions, alignValues);

if (!selectedAlign) return;

// Copy elements for editing
ea.copyViewElementsToEAforEditing(elements);
const eaElements = ea.getElements();

// Apply the selected alignment
eaElements.forEach((el) => {
    switch (selectedAlign) {
        case "top":
            // Align top edges
            el.y = topY;
            break;
        case "middle":
            // Align centers vertically
            el.y = middleY - el.height / 2;
            break;
        case "bottom":
            // Align bottom edges
            el.y = bottomY - el.height;
            break;
        case "first":
            // Align to first selected element's vertical center
            el.y = firstMiddleY - el.height / 2;
            break;
    }
});

// Update the view
ea.addElementsToView(false, false);

