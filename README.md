<div align="center">

# BasicInventory

**Desktop inventory management for small businesses.**
Fast, offline-first, no subscription required.

[![Latest release](https://img.shields.io/github/v/release/basicinventory-app/basicinventory?label=latest&color=0d9488)](https://github.com/basicinventory-app/basicinventory/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/basicinventory-app/basicinventory/total?color=0d9488)](https://github.com/basicinventory-app/basicinventory/releases)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0d9488)](#system-requirements)
[![License](https://img.shields.io/badge/license-Proprietary-important)](LICENSE.md)
[![Source](https://img.shields.io/badge/source-closed-lightgrey)](#is-this-repository-the-source-code)
[![Issues](https://img.shields.io/github/issues/basicinventory-app/basicinventory?color=0d9488)](https://github.com/basicinventory-app/basicinventory/issues)
[![Discussions](https://img.shields.io/github/discussions/basicinventory-app/basicinventory?color=0d9488)](https://github.com/basicinventory-app/basicinventory/discussions)

[Buy](https://www.ebay.es/itm/318673321758) · [Download](#download) · [Report a bug](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml) · [Request a feature](https://github.com/basicinventory-app/basicinventory/issues/new?template=feature_request.yml) · [Ask a question](https://github.com/basicinventory-app/basicinventory/discussions) · [What's next](#whats-next)

</div>

---

## What BasicInventory is

BasicInventory is a Windows desktop application for businesses that need to know
what they have, where it is, and what moved — without a warehouse-scale system
and without a monthly bill.

- **Products, categories and locations** — a catalogue plus a warehouse layout of
  aisle / column / height positions.
- **Stock, two ways** — manage goods **by boxes** (stock per location) or **by
  pallets** (full SSCC detail). One data model, two presentations; switch at any
  time from Settings, with no migration and no data loss.
- **Movements with an audit trail** — entries, exits, adjustments and transfers.
  An exit registered without naming a location takes the earliest expiry first
  (FEFO, then the oldest goods); name the location, the lot or the pallet and
  what leaves is what you picked. Nothing is edited silently: every change leaves
  a movement.
- **Lots and expiry dates** — per product, only where you need them, with an
  expiry horizon on the dashboard.
- **Dashboard** — item count, total stock, items below their reorder level, goods
  expiring soon, latest movements.
- **AI assistant (optional)** — ask about your inventory in plain language using
  **your own** AI provider key. See [privacy](#privacy).
- **Excel-friendly export** — every list exports to CSV that opens straight in
  Excel, respecting the filters you applied.
- **One-click backups** — a consistent copy of your database on demand, on close,
  and restorable from the app.

> Not a point of sale, not accounting software: BasicInventory holds no prices,
> no invoices and no customer records.

## Screenshots

| Products | Stock |
| --- | --- |
| ![Product catalogue with SKU, unit, reorder level and stock](docs/images/screenshot-products.png) | ![Stock by location, item, lot and expiry](docs/images/screenshot-stock.png) |

| Movements | AI assistant |
| --- | --- |
| ![Movement history: entries, exits, adjustments and transfers](docs/images/screenshot-movements.png) | ![The assistant answering a stock question with a table](docs/images/screenshot-assistant.png) |

## Download

Every official build lives on the [Releases](https://github.com/basicinventory-app/basicinventory/releases)
page.

1. Open the [latest release](https://github.com/basicinventory-app/basicinventory/releases/latest).
2. Download `BasicInventory-Setup-x.y.z.exe`.
3. Run it. See [Installation](#installation).

**Releases contain official binaries only** — the installer, its update metadata
(`latest.yml`) and the release notes. No source code is published here (see
[below](#is-this-repository-the-source-code)).

Verify what you downloaded: each release lists the SHA-256 of the installer.

```powershell
Get-FileHash .\BasicInventory-Setup-1.0.0.exe -Algorithm SHA256
```

## System requirements

| | Minimum | Recommended |
| --- | --- | --- |
| Operating system | Windows 10 (64-bit, 21H2) | Windows 11 (64-bit) |
| Processor | Dual-core x64 | Quad-core x64 |
| Memory | 4 GB RAM | 8 GB RAM |
| Disk | 500 MB free | 1 GB free (plus room for backups) |
| Display | 1366 × 768 | 1920 × 1080 |
| Internet | Not required | Required only for updates and the optional AI assistant |

Windows on ARM is not supported. There is no macOS or Linux build.

## Installation

1. Run `BasicInventory-Setup-x.y.z.exe`.
2. Windows SmartScreen may warn about an unrecognised publisher while the
   application is not yet code-signed. Choose **More info → Run anyway** if you
   trust the download, and check the SHA-256 above first.
3. Accept the licence terms, and choose the installation folder if you do not
   want the default one.
4. The installer needs **no administrator rights** and installs for the current
   user. It creates a desktop and a Start menu shortcut.
5. On first launch BasicInventory asks for your language, your company name and
   whether you manage stock **by boxes or by pallets**, then offers a guided tour.
6. Enter your **licence key** when asked. See below.

## Activating your licence

The download is free; the **licence key** is what you buy. After the first-run
setup, BasicInventory asks for it.

- The key arrives with your purchase, in the store's delivery message. It starts
  with `BI1-`.
- Activation happens **on your computer, offline**: nothing is sent anywhere, and
  no account or registration is involved.
- **Without a key the application cannot be used.** After the first-run setup it
  shows the activation screen and waits for the key; there is no trial mode and
  no read-only mode. Your data is never destroyed by this — activate later and
  everything is where you left it — but the interface stays behind that screen.
- The key stays with your data: restoring a backup on another computer carries
  the licence with it.
- Settings shows which e-mail and order the copy is licensed to.

Lost your key? Ask through the store you bought from — your order is there.

Your data lives in `%APPDATA%\BasicInventory`:

| Path | What it is |
| --- | --- |
| `basicinventory.db` | Your inventory (SQLite) |
| `logs\basicinventory.log` | Error log used by **Settings → Errors and diagnostics** |
| `.secret.key` | Local key that encrypts your AI provider key |

Backups go where you tell them to, and start out in
`Documents\BasicInventory\Copias de seguridad` — outside the installation, so
they survive uninstalling and are easy to find, copy or sync.

**Uninstalling asks** whether to delete your data as well, and keeping it is the
preselected answer. Choose to keep it and a reinstall picks up exactly where you
left off. Your backups folder is never touched either way.

Full walkthrough: [docs/getting-started.md](docs/getting-started.md).

## Updates

**Updates are offered, never imposed.** BasicInventory checks this repository's
Releases on startup, and if there is a newer version it tells you — a strip at
the top of the window, never a dialog over what you are doing.

You then choose:

| | |
| --- | --- |
| **See what's new** | The release notes, then download and install when you want. |
| **Later** | It asks again next time you open the application. |
| **Skip this version** | It stops asking for that one. A later version asks again. |

Nothing is downloaded and nothing is installed unless you say so, and the
application never restarts on its own. Downloading and installing are separate
steps, so you can fetch an update at a quiet moment and install it when the
warehouse is closed.

**Settings → Updates** always shows the installed version, when it last checked,
and a **Check for updates** button — including for a version you skipped.

- The check is a read-only request to the public GitHub Releases API. No account
  and no data of yours is involved.
- Installing over an existing version keeps your database and settings, and a
  backup is taken automatically before the update is applied.
- You can always install manually from
  [Releases](https://github.com/basicinventory-app/basicinventory/releases).

Read [CHANGELOG.md](CHANGELOG.md) to see what changed before updating.

## Reporting a bug

Open a [bug report](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml).
The form asks for the version, your Windows version, steps to reproduce, what you
expected, what happened, a screenshot and the log — everything needed to act on
it without a round of questions.

Fastest route from inside the app: **Settings → Errors and diagnostics →
Copy diagnostics**, then paste that into the report. It carries the version, the
system details and the last errors, with your Windows user name removed from the
paths.

Please do not report **security** issues in a public issue — see
[SECURITY.md](SECURITY.md).

## Requesting a feature

Open a [feature request](https://github.com/basicinventory-app/basicinventory/issues/new?template=feature_request.yml),
or float the idea first in
[Discussions → Ideas](https://github.com/basicinventory-app/basicinventory/discussions/categories/ideas).
Describe the problem you are trying to solve rather than the solution you have in
mind — it usually leads somewhere better.

Accepted requests get the `planned` label, so
[that list](https://github.com/basicinventory-app/basicinventory/issues?q=is%3Aissue+is%3Aopen+label%3Aplanned)
is always what is actually coming.

## What's next

There is no published roadmap, and that is deliberate: what gets built next
comes from what the people using BasicInventory ask for, not from a plan written
before anyone had it installed.

- **[Planned](https://github.com/basicinventory-app/basicinventory/issues?q=is%3Aissue+is%3Aopen+label%3Aplanned)** — accepted and coming.
- **[Ideas](https://github.com/basicinventory-app/basicinventory/discussions/categories/ideas)** — under discussion. Upvotes here decide priority.
- **[Milestones](https://github.com/basicinventory-app/basicinventory/milestones)** — what is grouped into the next version.

Two things are already known: **code signing** (so Windows stops warning about
the installer) and keeping the desktop edition a one-off purchase, never a
subscription.

## Support

[SUPPORT.md](SUPPORT.md) explains the channels: **Issues** for bugs and feature
requests, **Discussions** for questions and help. Response times and what to
include are documented there.

## Is this repository the source code?

**No. BasicInventory is closed source and its source code is not public.**

This repository exists so that the product has one public home for:

- official releases and their notes,
- bug reports and feature requests,
- documentation and support,
- the update feed the application reads.

The application's source lives in a **private repository**. Pull requests are
therefore not accepted — see [CONTRIBUTING.md](CONTRIBUTING.md) for what *is*
welcome (which is quite a lot: reports, ideas, documentation corrections).

## Buying a licence

BasicInventory is commercial software. One purchase, one perpetual licence for
the version line you bought — no subscription.

**The download is free; the key is what is sold.** Anyone can install it and
look around; recording stock needs a licence. See
[Activating your licence](#activating-your-licence).

| Where | Link |
| --- | --- |
| eBay (Spanish listing) | **[Buy on eBay](https://www.ebay.es/itm/318673321758)** |
| eBay (English listing) | **[Buy on eBay](https://www.ebay.es/itm/318673323733)** |
| Gumroad | **[Buy on Gumroad](https://xabier6.gumroad.com/l/basicinventory)** |

The two eBay listings are the same product; they differ only in the language of
the description. Pick whichever you read more comfortably.

Anything about a purchase — invoices, refunds, volume or reseller enquiries —
goes through the store you bought from, using its message system: your order
travels with the question. See [SUPPORT.md](SUPPORT.md).

The licence terms are in [LICENSE.md](LICENSE.md).

## Privacy

BasicInventory is offline-first and stores your inventory **only on your
computer**, in a local SQLite database.

| What leaves your machine | When | To whom |
| --- | --- | --- |
| An update check | On startup | GitHub (public Releases API) |
| Your question plus the inventory data needed to answer it | Only if you enable the AI assistant, only when you ask something | The AI provider **you** configured |
| Nothing else | — | — |

- **No telemetry, no analytics, no crash uploads.** Errors are written to a local
  log file; you decide whether to attach it to a report.
- The AI assistant is **off until you configure it**. BasicInventory ships no API
  key: you connect your own provider (OpenAI, Anthropic, Google Gemini,
  OpenRouter) and that provider bills you directly. The key is stored encrypted
  (AES-256-GCM) with a machine-local key kept outside the database, and the app
  only ever shows a masked hint of it.
- The assistant can **read** your inventory, never modify it, and cannot reach
  your configuration, keys, backups or files.

Details: [docs/privacy.md](docs/privacy.md).

## FAQ

<details>
<summary><strong>Do I need an internet connection?</strong></summary>

No. Everything except update checks and the optional AI assistant works fully
offline.
</details>

<details>
<summary><strong>Is there a subscription?</strong></summary>

No. You buy a licence for a version line and keep using it. Patch and minor
updates within that line are included.
</details>

<details>
<summary><strong>Where is my data, and how do I move it to another computer?</strong></summary>

In `%APPDATA%\BasicInventory\basicinventory.db`. Use **Settings → Backups →
Create backup now**, copy the `.db` file across, and restore it from the same
screen on the new machine.
</details>

<details>
<summary><strong>Can several people use it at the same time?</strong></summary>

Not yet. Today BasicInventory is single-machine. Multi-user and a cloud edition
are not available yet — see [what's next](#whats-next).
</details>

<details>
<summary><strong>What does "boxes or pallets" mean?</strong></summary>

Two ways of presenting the same stock. In **boxes** mode you see quantities per
location, item, lot and expiry — no pallet concept anywhere. In **pallets** mode
you also see each pallet, its SSCC code and pallet-level actions. Switching is
instant and migrates nothing.
</details>

<details>
<summary><strong>Does the AI assistant cost extra?</strong></summary>

The assistant itself is included, but the AI provider you connect charges you for
each question on your own account. BasicInventory neither resells nor marks up
that usage, and the app says so on the screen.
</details>

<details>
<summary><strong>Why does Windows warn me when I install it?</strong></summary>

The installer is not code-signed yet, so SmartScreen does not recognise the
publisher. Code signing is planned. Until then, verify the
SHA-256 published with each release.
</details>

<details>
<summary><strong>Will you support macOS or Linux?</strong></summary>

Not in the current line, and not promised for one — add your vote in
[Discussions](https://github.com/basicinventory-app/basicinventory/discussions).
</details>

<details>
<summary><strong>Can I get the source code?</strong></summary>

No. The source is private. Source-available licensing for specific commercial
arrangements can be discussed privately — email the address in
[SUPPORT.md](SUPPORT.md).
</details>

## Licences

- **The application**: proprietary. Terms in [LICENSE.md](LICENSE.md).
- **This documentation**: free to read, quote and translate with attribution;
  see the notice at the end of [LICENSE.md](LICENSE.md).
- **Third-party components**: BasicInventory bundles open-source components
  (Electron, Node.js, Prisma, React, Next.js and others). Their licences and
  copyright notices ship with the application and are listed in
  [docs/third-party-licenses.md](docs/third-party-licenses.md).

---

<div align="center">

**[Releases](https://github.com/basicinventory-app/basicinventory/releases)** ·
**[Changelog](CHANGELOG.md)** ·
**[What's next](#whats-next)** ·
**[Support](SUPPORT.md)** ·
**[Security](SECURITY.md)**

</div>
