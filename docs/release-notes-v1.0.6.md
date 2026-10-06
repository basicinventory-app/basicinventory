# Release notes: v1.0.6

Customer-facing notes for the Microsoft Store update. Use them for the
announcement discussion; the same content is mirrored in
[CHANGELOG.md](../CHANGELOG.md).

---

## BasicInventory v1.0.6

Your warehouse in 3D: a new map that draws itself from the locations you already
have, and that you can walk through, click and rearrange.

**How you get it:** automatically, through the Microsoft Store — Windows updates
your copy in the background. Nothing to download or install by hand.

### ✨ New

- **3D warehouse map** — a new **3D map** screen in the sidebar. Every
  location's aisle, column and height become racks, bays and shelves, with each
  zone in its own colour. There is nothing to draw.
- **Walk through it** — orbit and zoom with the mouse, move with the arrow keys
  or W A S D (Shift to go faster, Q and E to turn), and switch to a floor plan.
  Click any shelf to see which location it is and open its stock; come back and
  the camera is where you left it.
- **Rearrange it** — **Edit layout** lets you drag racks, rotate and hide them,
  and set bay width, depth, level height and the gap between aisles in metres.
  Undo, reset, and nothing is kept until you press Save.
- **Or just say it** — the optional **AI assistant** inside Edit layout moves
  the racks from a sentence ("aisle F is in another building, far from the
  rest"). It uses your own AI provider and key, applies the change straight
  away, and one click undoes it.

### ⚠️ Important

- The map **only draws** your locations: it never creates, renames or deletes
  one. A line above the map tells you if a location is not on it yet.
- If you use the map's AI assistant, it sends your messages and a summary of
  your aisles and the map layout to the AI provider you configured — no
  products, quantities, lots or movements. Details in
  [privacy](https://github.com/basicinventory-app/basicinventory/blob/main/docs/privacy.md).
- Not yet: shelves are coloured by zone, not by how full they are.

Guide: [3D warehouse map](https://github.com/basicinventory-app/basicinventory/blob/main/docs/warehouse-map.md).

### 🧾 Notes

- Requires Windows 10 or 11, 64-bit. See the [system requirements](https://github.com/basicinventory-app/basicinventory#system-requirements).
- Updates keep your database and settings.
- Not seeing the update yet? **Microsoft Store → Library → Get updates**.
- Something wrong? [Report it](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml) with **Settings → Errors and diagnostics → Copy diagnostics**.
