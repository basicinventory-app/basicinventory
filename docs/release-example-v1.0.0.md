# Example: release notes for v1.0.0

This is the text published as the GitHub Release for the first version. Kept in
the repository as a worked example of the tone and structure expected from every
release — see [`.github/RELEASE_NOTES_TEMPLATE.md`](../.github/RELEASE_NOTES_TEMPLATE.md)
for the blank form.

---

## BasicInventory v1.0.0 — first public release

Know what you have, where it is, and what moved. BasicInventory is a Windows
desktop application for small businesses that need real stock control without a
warehouse-scale system and without a monthly bill.

**Update:** first version — nothing to update from · **Backup recommended before updating:** not applicable

### ✨ What you get

- **Your catalogue and your warehouse** — products with SKU, unit, reorder level
  and category; locations addressed the way you already say them out loud
  (`A-01-2`: aisle, column, height).
- **Stock the way you work** — manage goods **by boxes** (quantities per
  location, item, lot and expiry) or **by pallets** (each pallet with its SSCC
  code). Choose during setup, change whenever you like: it changes what you see,
  never your data.
- **Movements you can trust** — entries, exits, adjustments and transfers, each
  one recorded permanently. Exits take the earliest expiry first, and stock can
  never go below zero by accident.
- **Lots and expiry dates** — switched on per product, with the goods expiring in
  the next 30 days on the dashboard.
- **A dashboard that answers the morning questions** — how many items, how much
  stock, what is below its minimum, what expires soon, what moved last.
- **AI assistant, optional and yours** — ask "which items are below their
  minimum?" or "where is lot L26061?" in plain language. BasicInventory ships no
  API key: you connect your own OpenAI, Anthropic, Gemini or OpenRouter account
  and that provider bills you directly. The assistant only reads; it cannot
  change your data, and it cannot reach your keys, backups or files.
- **Backups without ceremony** — one click, plus an automatic copy every time you
  close the application, with restore from the same screen.
- **Export that opens in Excel** — every list, honouring the filters you applied.
- **Spanish and English**, light and dark, and a guided tour on first run.

### 🔐 Privacy

Your inventory stays on your computer, in a local database. No telemetry, no
analytics, no crash uploads. The only things that ever leave the machine are the
update check against this repository and — if you enable the assistant — your
questions to the AI provider you configured. Your provider key is stored
encrypted with a machine-local key kept outside the database.

### ⚠️ Known limitations

- Windows 10/11, 64-bit only. No macOS or Linux build.
- The installer is not code-signed yet, so Windows SmartScreen shows a warning.
  Verify the hash below. Code signing is planned.
- Single machine, single user. Multi-user and a cloud edition are planned.

### 📦 Download

| File | Purpose |
| --- | --- |
| `BasicInventory-Setup-1.0.0.exe` | Installer (Windows 10/11, 64-bit) |
| `latest.yml` | Update metadata — used by the application, not for manual download |

**SHA-256** of the installer:

```
0000000000000000000000000000000000000000000000000000000000000000
```

```powershell
Get-FileHash .\BasicInventory-Setup-1.0.0.exe -Algorithm SHA256
```

### 🧾 First steps

1. Run the installer — no administrator rights needed.
2. Pick your language, type your company name and choose boxes or pallets.
3. Take the guided tour. It uses the real screens, so nothing is a mock-up.
4. Set your backup folder in **Settings → Backups** before you load real data.

Full documentation: [Getting started](getting-started.md).

Something wrong? [Report it](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml)
with **Settings → Errors and diagnostics → Copy diagnostics** pasted in. Ideas
for what should come next belong in
[Discussions → Ideas](https://github.com/basicinventory-app/basicinventory/discussions/categories/ideas)
— what comes after 1.0 is shaped by what the first users ask for.

Thank you for trying it.
