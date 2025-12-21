# Linear Calendar Generator (Obsidian Excalidraw Script)

![Obsidian](https://img.shields.io/badge/Obsidian-483699?style=for-the-badge\&logo=obsidian\&logoColor=white)
![Excalidraw](https://img.shields.io/badge/Excalidraw-6965DB?style=for-the-badge\&logo=excalidraw\&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=000000)

In [this video](https://youtu.be/j64YOie4bIw), Nick Milo explains the benefits of using a **Linear Calendar** to plan your year.

This Obsidian Excalidraw Script will generate a beautiful horizontal year calendar directly in Excalidraw with days flowing left to right and months arranged as rows.

![Screenshot](ea-scripts/linear-calendar-generator/screenshot.jpg)

## Features

- **Horizontal Timeline Layout** — Days of the week run as columns, creating a natural left-to-right reading flow
- **Month Rows** — Each month occupies its own row with labels on both left and right sides for easy reference
- **Weekend Highlighting** — Saturdays and Sundays are automatically styled differently
- **Day Headers** — Day-of-week indicators appear at both top and bottom of the calendar
- **Year Title** — The year is prominently displayed above the calendar

## Usage

1. Open an Excalidraw drawing
2. Run the script from the Excalidraw Scripts menu
3. Enter the desired year when prompted (defaults to the current year)
4. The calendar will be generated at the origin point of your canvas

## Customizing Colors

You can personalize the calendar's appearance by pre-selecting colored rectangles:

1. Create **two rectangles** in your drawing
2. Style them with your desired fill colors, stroke width, and fill style
3. **Select both rectangles** before running the script:
   - The **first rectangle's** fill and stroke style → applied to **weekdays**
   - The **second rectangle's** fill color → applied to **weekends**

If no rectangles are selected, the default color scheme is used:
- Weekdays: White (`#ffffff`)
- Weekends: Light blue-gray (`#e8eaed`)

## Layout Specifications

| Element | Value |
|---------|-------|
| Cell Width | 176px |
| Cell Height | 288px |
| Row Spacing | 32px |
| Month Label Width | 240px |
| Columns | 37 (accommodates all month alignments) |

## Installation

Download the script and place it in your Excalidraw scripts folder, or install it directly from the Excalidraw script library.

