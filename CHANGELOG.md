# Changelog

All notable changes to BasicInventory are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Each released version has an installer on the
[Releases](https://github.com/basicinventory-app/basicinventory/releases) page.
Versions are dated `YYYY-MM-DD`.

## [Unreleased]

### Added

- Nothing yet.

---

## [1.0.2] — 2026-08-03

### Fixed

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
  immutable audit trail. Exits consume the earliest expiry first (FEFO, then
  FIFO) and never take stock below zero.
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
