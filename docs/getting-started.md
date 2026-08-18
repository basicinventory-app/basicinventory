# Getting started

From the Store to a warehouse you can actually use, in about twenty minutes.

## 1. Install

BasicInventory installs from the
**[Microsoft Store](https://apps.microsoft.com/detail/9N8GQS365ZLM)**. Open the
listing and select **Get**. Windows installs and pins it — no security warning,
no administrator rights — and the copy is **already licensed**, so first
run goes straight to setup below with no key to enter. See
[how to get it](microsoft-store.md).

## 2. First run

The setup asks three things:

1. **Language** — Spanish or English. Changeable later in Settings.
2. **Company name** — appears in the sidebar and on exports.
3. **How you manage stock**:
   - **Boxes** — you think in "how many units of this item are in this location".
     No pallet concept appears anywhere.
   - **Pallets** — you handle whole pallets with SSCC codes, and want to see and
     act on each one.

   Choose what matches how you talk about your goods. It changes only what the
   screens show; both modes store the same thing, and you can switch at any time
   in **Settings → Management mode** without migrating anything.

There is **no licence key to enter**: the Store copy is licensed by your
purchase, tied to your Microsoft account, so setup goes straight on with nothing
to activate.

Then take the guided tour. It walks the real screens with sample data and can be
replayed from the **?** button in the top bar.

## 3. Set your backup folder first

**Settings → Backups → Backups folder.** It starts out at
`Documents\BasicInventory\Copias de seguridad`, which is outside the
installation and survives uninstalling. Point it at a synced folder (OneDrive,
Drive) or an external drive if you can — a backup on the same disk as the
original protects you from mistakes, not from a dead disk.

A copy is written automatically every time you close the application, and you can
create one on demand with **Create backup now**. Old copies are pruned according
to **Backups to keep**.

Do this before entering real data, not after. See [Backups](backups.md).

## 4. Build the catalogue

Work in this order; each step depends on the previous one.

### Categories

**Categories → New.** Keep them broad — "Beverages", "Cleaning", "Packaging".
Categories group reporting; they are not a place for detail.

### Locations

**Locations → New**, or generate a grid. Each location is
**aisle · column · height**, shown as `A-01-2`, with an optional zone
("Cold room", "Returns").

Use the labels already painted on your shelves. If the shelf says B-3-1, call it
B-3-1 — matching reality beats a tidier scheme nobody uses.

### Products

**Products → New**:

| Field | What it is for |
| --- | --- |
| SKU | Your unique code. Must be unique; it is what you search by. |
| Name | What people call it. |
| Unit | Units, boxes, kilos… free text, shown everywhere the quantity appears. |
| Reorder level | Below this, the item is flagged on the dashboard. |
| Category | Optional. |
| Requires lot | Ask for a lot number on every entry. |
| Requires expiry | Ask for an expiry date on every entry. |

Only enable lot and expiry where you genuinely track them: every entry will
demand them.

## 5. Load your opening stock

**Stock → Register entry** (boxes mode) or **Pallets → New** (pallets mode) for
each item you already hold: item, location, quantity, and lot/expiry where the
product requires them.

Each entry creates an `IN` movement, so your history starts on day one.

If you have hundreds of lines, do a first pass with the most valuable or
fastest-moving items and grow from there — a half-loaded system used daily beats
a complete one abandoned mid-import. (Excel import is a frequent request — add
yours in [Discussions](https://github.com/basicinventory-app/basicinventory/discussions/categories/ideas).)

## 6. Day to day

| You did this | Do this in BasicInventory |
| --- | --- |
| Goods arrived | **Entry** — item, location, quantity, lot/expiry |
| Goods went out | **Exit** — item, location and quantity; the movement keeps the lot and the location |
| You counted and reality differs | **Adjustment** — enter the real count; the difference is recorded |
| You moved goods to another location | **Transfer** — origin, destination, quantity |
| You need the list for someone else | **Export** from the pagination bar; opens in Excel |

Everything leaves a movement. **Movements** is the searchable history: what, how
much, where, when, and why if you wrote a reason.

## 7. Ask the assistant (optional)

**AI assistant → Configuration** connects your own AI provider account. Then ask
in plain language: *"which items are below their minimum?"*, *"what expires this
month?"*, *"where is lot L26061?"*.

It reads your inventory and nothing else — no changes, no access to keys,
backups or files — and each question is billed to you by your provider, not by
BasicInventory. See [AI assistant](ai-assistant.md).

## Where your data lives

Your inventory, the error log and the local encryption key sit in a per-user
application folder that Windows manages for Store apps. You rarely need the raw
path — the in-app backup is the supported way to reach your data — but
**Settings → Errors and diagnostics** always shows the exact folder in use.

Moving to another computer: use **Settings → Backups → Create backup now**, copy
the backup file across, and restore it from **Settings → Backups** on the new
machine.

## Next

- [Backups and restore](backups.md)
- [AI assistant](ai-assistant.md)
- [Troubleshooting](troubleshooting.md)
- [Privacy](privacy.md)
