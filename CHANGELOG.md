# Changelog

All notable changes to BasicInventory are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

BasicInventory is distributed through the
[Microsoft Store](https://apps.microsoft.com/detail/9N8GQS365ZLM), which keeps it
updated automatically. Versions are dated `YYYY-MM-DD`.

## [Unreleased]

### Added

- **BasicInventory is on the Microsoft Store**, now the only way to get it:
  [apps.microsoft.com](https://apps.microsoft.com/detail/9N8GQS365ZLM). Buying and
  installing are one step; it installs with no security warning; Windows keeps it
  updated; and the copy is sold already licensed, tied to your Microsoft account,
  with no key to paste and nothing to activate. See
  [How to get BasicInventory](https://github.com/basicinventory-app/basicinventory/blob/main/docs/microsoft-store.md).

### Changed

- **The direct download has been retired.** The eBay and Gumroad listings and the
  unsigned installer distributed here (activated with a `BI1-` licence key) are no
  longer offered, and the GitHub Releases feed the direct build updated from is
  gone. The Microsoft Store is now the single channel: it is the same application,
  bought, installed, updated and licensed through the Store. Copies already
  installed from the direct download keep working with their existing key.
- **A demo you can use in your browser**, at
  [demo.basicinventory.app](https://demo.basicinventory.app). It is the whole
  application — the same screens and the same rules — running in a tab on a
  sample warehouse: register entries and exits, move stock, filter, export,
  switch between boxes and pallets, and ask the assistant with your own API key.
  Nothing is installed, no account is needed, and nothing you type leaves your
  browser: the demo has no server behind it and its data disappears when you
  close the tab. Backups, settings, updates and keeping your data are the parts
  a browser cannot do — those are what the application is for. This changes
  nothing in the installed application.

---

## [1.0.6] — 2026-10-05

### Added

- **3D warehouse map.** A new **3D map** screen draws your warehouse from the
  locations you already have — one rack per aisle, one bay per column, one shelf
  per level, each zone in its own colour. There is nothing to draw.
  - **It opens for browsing**: orbit, zoom and pan with the mouse, walk the
    aisles with the arrow keys or W A S D (Shift to go faster, Q and E to turn),
    and switch between a 3D view and a floor plan. Click any shelf to see which
    location it is and open its stock; when you come back, the camera is where
    you left it.
  - **Edit layout**, when you need it: drag racks, rotate them, hide them, and
    set bay width, depth, level height and the gap between aisles in metres —
    for one aisle, several, or the whole warehouse. Everything can be undone,
    and leaving with unsaved changes asks first.
  - **AI assistant for the layout** (optional, with your own provider key): a
    chat beside the map. Describe the change in your own words and it is
    applied at once; undo it if you don't like it. Nothing is saved until you
    press Save.
  - The map only draws your locations: it never creates, renames or deletes
    one, and a line above it tells you if any location is not on the map yet.
  - Not yet: shelves are coloured by zone, not by how full they are.
  - Guide: [3D warehouse map](docs/warehouse-map.md).

### Privacy

- The map's AI assistant, if you use it, sends your messages in that chat and a
  summary of the warehouse's structure (aisle codes, column and level counts,
  zone names, a few sample location codes) plus the current layout to the AI
  provider you configured. It sends no products, quantities, lots or movements.
  See [privacy](docs/privacy.md).

---

## [1.0.5] — 2026-08-10

### Fixed

- **The provider description on the AI settings screen now follows your
  language.** When choosing an AI provider (OpenAI, Anthropic, Gemini,
  OpenRouter), the short line under each name was always shown in Spanish, even
  with the interface in English. It now matches the interface language. Nothing
  else changes: you still bring your own provider and key.

---

## [1.0.4] — 2026-08-06

### Fixed

- **The English interface no longer shows movement types in Spanish.** Entries,
  exits, adjustments and moves are stored in a table that is written in one
  language, and the application was showing that stored name — so an English
  copy read "Salida" and "Ajuste" in the movements list, on the dashboard and in
  the exported file. The interface now translates them itself. Your own data —
  product names, reasons, lots — is untouched: it is yours, in whatever language
  you typed it.
- **Exported files are named in your language.** An English copy was
  downloading `movimientos.csv` and `productos.csv`; now it gets `movements.csv`
  and `products.csv`.

---

## [1.0.3] — 2026-08-04

### Added

- **A "Buy a licence" button on the activation screen.** If you downloaded the
  installer before buying, the screen asking for your key now has somewhere to
  go: it opens the listing in the language the application is running in.

---

## [1.0.2] — 2026-08-03

### Fixed

- **Reporting a problem with the technical information attached ended in a
  GitHub error page.** The details travelled in the address bar and a single
  error could carry a four-kilobyte dump, which made the link too long for
  GitHub to accept — especially when it sends you through the sign-in page
  first. The attachment is now a short summary, and the full log stays one
  click away in Settings.
- **The report dialog says up front that a GitHub account is needed**, instead
  of letting you find out at the sign-in wall.

- **The application no longer fights over ports 3000 and 4000.** It used to
  serve itself on those two, which are the first ports any development tool
  takes — if something else was using one, BasicInventory would not open at
  all. It now uses a single, uncommon port chosen when it starts, and falls
  back to another if that one is busy. Nothing to configure.

---

## [1.0.1] — 2026-08-03

A first round of fixes from using 1.0.0 in earnest.

### Fixed

- **Checking for updates no longer shows a raw "404".** When the updates
  repository cannot be reached — no internet, a company firewall, a proxy with
  its own certificate — the application now says so in your language and
  suggests checking the connection, instead of printing an HTTP error that
  means nothing. The technical detail still goes to the log.
- **The technical information attached to a report stayed inside the dialog.**
  A long stack trace or path used to push the dialog sideways instead of
  wrapping. Same fix applied to the error details in Settings and to the crash
  screen.

### Added

- **The assistant now says it can be wrong.** A permanent line under the message
  box: AI can get things wrong, so check anything you are about to act on
  against your data.

---

## [1.0.0] — 2026-08-03

First public release.

### Added

- **Inventory catalogue** — products (SKU, unit, reorder level, category),
  categories, and a warehouse layout of locations addressed as
  aisle-column-height (for example `A-01-2`), with an optional zone.
- **Two ways to manage stock** — *boxes* (quantities per location, item, lot and
  expiry) or *pallets* (each pallet with its SSCC code and pallet-level actions).
  The choice is made during first-run setup and can be changed at any time from
  Settings; it changes only how stock is presented, never the data.
- **Movements** — entries, exits, adjustments and transfers, recorded as an
  immutable audit trail, each keeping the lot and the location it touched. Stock
  never goes below zero.
- **Lots and expiry dates** — enabled per product, with an expiry horizon and a
  dashboard warning for goods expiring within 30 days.
- **Dashboard** — item count, total stock, items below their reorder level,
  goods expiring soon and the latest movements.
- **AI assistant (optional)** — ask about the inventory in plain language.
  BasicInventory ships no API key: you connect your own OpenAI, Anthropic,
  Google Gemini or OpenRouter account, and the provider bills you directly. The
  assistant is read-only, keeps a history of conversations you can revisit, and
  cannot reach configuration, keys, backups or files. Keys are stored encrypted
  (AES-256-GCM) with a machine-local key kept outside the database.
- **Licence activation** — the download is free and the licence key is what you
  buy. Activation happens on your computer, offline: no account, no
  registration, nothing sent anywhere. Without a key you can still open the
  application, read what is there, export it and take backups; you cannot record
  changes. Settings shows which e-mail and order the copy is licensed to, and a
  restored backup carries the licence with it.
- **Backups** — one-click backup to a folder of your choice, an automatic backup
  when the application closes, retention pruning, and restore from the app.
  Backups start out in `Documents\BasicInventory\Copias de seguridad`, outside
  the installation, so uninstalling never takes them with it.
- **Installer** — accepts the licence terms, lets you choose the folder, needs no
  administrator rights, and creates desktop and Start menu shortcuts.
  Uninstalling asks before deleting your data, with "keep" preselected.
- **Excel-friendly export** — every list exports to CSV (semicolon separated,
  UTF-8 BOM) honouring the active filters.
- **Guided onboarding** — first run asks for language, company name and
  management mode, then an interactive tour of the real screens. Replayable from
  the help button at any time.
- **Spanish and English** interface, light and dark themes.
- **Errors and diagnostics** — errors are written to a local rotating log; the
  Settings screen shows the installation's details and its recent errors, ready
  to copy into a bug report. No telemetry: nothing is sent anywhere.
- **Updates you control** — the application checks this repository's releases on
  startup and tells you when a new version exists, with its release notes.
  Downloading and installing only happen when you ask, and a version can be
  skipped. Settings has a "Check for updates" button that always works.

### Security

- AI provider keys are encrypted at rest and never returned by the application's
  internal API — only a masked hint is shown.
- The AI assistant reaches data through a read-only layer with a table
  allowlist; configuration, credentials and the file system are unreachable by
  construction, not merely by instruction.

### Known limitations

- Windows only (64-bit); no macOS or Linux build.
- The installer is not yet code-signed, so Windows SmartScreen shows a warning.
- Single machine, single user: no multi-user or cloud edition yet.

[Unreleased]: https://github.com/basicinventory-app/basicinventory/compare/v1.0.2...HEAD
[1.0.2]: https://github.com/basicinventory-app/basicinventory/releases/tag/v1.0.2
[1.0.1]: https://github.com/basicinventory-app/basicinventory/releases/tag/v1.0.1
[1.0.0]: https://github.com/basicinventory-app/basicinventory/releases/tag/v1.0.0
