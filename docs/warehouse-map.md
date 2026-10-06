# 3D warehouse map

The **3D map** draws your warehouse from the locations you already have. There
is nothing to draw: every location is an *aisle · column · height*, so an aisle
becomes a rack, a column becomes a bay along it, and a height becomes a shelf
level. Aisles in the same zone are placed together and share a colour.

The map only **draws** your locations. It never creates, renames or deletes one —
that is still done in **Locations**.

Open it from the sidebar: **3D map**.

## Getting around

The map opens for browsing. Nothing can be moved by accident in this mode.

| | |
| --- | --- |
| Arrow keys or **W A S D** | Walk through the warehouse |
| **Shift** (hold) | Move faster — handy in a large warehouse |
| **Q** / **E** | Turn left or right |
| Drag | Orbit the view |
| Right-drag | Pan across the floor |
| Mouse wheel | Zoom in or out |
| **Perspective** / **Top** | Switch between a 3D view and a floor plan |
| **Fit view** | Frame the whole warehouse again |

**Click any shelf** and the panel on the right tells you which real location it
is — code, aisle, column, height and zone — with **View stock** to open what is
stored there. When you come back to the map, the camera is where you left it.

## The coverage line

Above the map, a line counts your locations and how many the map represents:

> 240 locations in the database · 240 represented · 0 not represented

If you add a location in a new aisle, it shows as **not represented** until it
has a place on the map; **Add the pending aisles** places it for you.

## Changing the layout

Press **Edit layout** to change how the warehouse is drawn:

- **Click** a rack to select it, **Shift + click** to select several.
- **Drag** a rack across the floor, **Rotate 90°**, or **Hide** it.
- Set measurements in metres with sliders: bay width, depth, height between
  levels, first-level height, gap between bays and **gap between aisles** — for
  one aisle, the selected ones, or the whole warehouse.
- **Undo** reverses the last change; **Reset** goes back to the automatic layout.
- **Save** keeps the layout and returns to browsing. **Exit** with unsaved
  changes asks before discarding them.

Nothing you change here touches your locations or your stock: it only changes
how the warehouse is drawn.

## AI assistant (optional)

Inside **Edit layout**, the **AI assistant** button opens a chat beside the map.
Describe the change in your own words — *"aisle F is in another building, far
from the rest"*, *"leave 5 metres between every aisle"* — and the racks move
straight away. Under each reply you can see what changed, and **Undo** is right
there. Nothing is saved until you press **Save**.

It uses the same AI provider and your own key as the
[inventory assistant](ai-assistant.md); with no provider configured, it takes
you to set one up. It cannot create, rename or delete locations, and it never
sees your products or stock.

**What it sends to your provider:** your messages in that chat and a summary of
the warehouse's structure — aisle codes, how many columns, levels and locations
each has, zone names, a few sample location codes — plus the current layout
(positions and measurements). No products, quantities, lots or movements. See
[privacy](privacy.md).

## What it does not do (yet)

- Shelves are coloured by **zone**, not by how full they are.
- It is a configurator, not a CAD program: no walls, doors or dimensioned
  drawings to export.
- Racks are uniform within an aisle (every bay of an aisle has the same width).
