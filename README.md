<div align="center">

# BasicInventory

**Desktop inventory management for small businesses.**
Fast, offline-first, no subscription required.

[![Microsoft Store](https://img.shields.io/badge/Microsoft%20Store-get%20it-0d9488)](https://apps.microsoft.com/detail/9N8GQS365ZLM)
[![Latest release](https://img.shields.io/github/v/release/basicinventory-app/basicinventory?label=latest&color=0d9488)](https://github.com/basicinventory-app/basicinventory/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/basicinventory-app/basicinventory/total?color=0d9488)](https://github.com/basicinventory-app/basicinventory/releases)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0d9488)](#system-requirements)
[![License](https://img.shields.io/badge/license-Proprietary-important)](LICENSE.md)
[![Source](https://img.shields.io/badge/source-closed-lightgrey)](#is-this-repository-the-source-code)
[![Issues](https://img.shields.io/github/issues/basicinventory-app/basicinventory?color=0d9488)](https://github.com/basicinventory-app/basicinventory/issues)
[![Discussions](https://img.shields.io/github/discussions/basicinventory-app/basicinventory?color=0d9488)](https://github.com/basicinventory-app/basicinventory/discussions)

[Get it on the Microsoft Store](https://apps.microsoft.com/detail/9N8GQS365ZLM) · [Try the demo](https://demo.basicinventory.app) · [Other ways to get it](#download) · [Report a bug](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml) · [Request a feature](https://github.com/basicinventory-app/basicinventory/issues/new?template=feature_request.yml) · [Ask a question](https://github.com/basicinventory-app/basicinventory/discussions) · [What's next](#whats-next)

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
- **Movements with an audit trail** — entries, exits, adjustments and transfers,
  each recording the item, the quantity, the lot and the location it touched.
  Nothing is edited silently: every change leaves a movement.
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

## Try it first

[**demo.basicinventory.app**](https://demo.basicinventory.app) is the whole
application running in your browser, on a sample warehouse. Register entries and
exits, move stock, filter, export, switch between boxes and pallets, ask the
assistant with your own API key. Nothing to install, no account, and nothing you
type leaves your tab — the demo runs entirely in the browser and its data
disappears when you close it.

What the demo cannot show, because a browser tab is not a PC: backups, settings,
updates and keeping your data. Those are the application.

## Screenshots

| Products | Stock |
| --- | --- |
| ![Product catalogue with SKU, unit, reorder level and stock](docs/images/screenshot-products.png) | ![Stock by location, item, lot and expiry](docs/images/screenshot-stock.png) |

| Movements | AI assistant |
| --- | --- |
| ![Movement history: entries, exits, adjustments and transfers](docs/images/screenshot-movements.png) | ![The assistant answering a stock question with a table](docs/images/screenshot-assistant.png) |

## Download

There are two ways to get BasicInventory. They install two different builds of
the **same application** — see [Two ways to get it](docs/microsoft-store.md) for
the full comparison.

### The Microsoft Store — recommended

**[Get it on the Microsoft Store](https://apps.microsoft.com/detail/9N8GQS365ZLM)**

Buying and installing are one step. Microsoft signs the package, so there is no
SmartScreen warning; the Store keeps it updated; and the copy is **sold already
licensed** — there is no key to paste. This is the simplest path and the one most
people should take.

### The direct download — an alternative

Buy the licence on [eBay or Gumroad](#buying-a-licence), then download the
installer from the [Releases](https://github.com/basicinventory-app/basicinventory/releases)
page and activate it with your `BI1-` key.

1. Open the [latest release](https://github.com/basicinventory-app/basicinventory/releases/latest).
2. Download `BasicInventory-Setup-x.y.z.exe`.
3. Run it. See [Installation](#installation).

**Releases contain official binaries only** — the installer, its update metadata
(`latest.yml`) and the release notes. No source code is published here (see
[below](#is-this-repository-the-source-code)). This installer is not code-signed,
so Windows SmartScreen may warn about the publisher; verify the SHA-256 each
release lists.

```powershell
Get-FileHash .\BasicInventory-Setup-1.0.5.exe -Algorithm SHA256
```

The Store copy and a direct-download copy are two different modes: a Store
purchase is not a `BI1-` key, and a `BI1-` key is not a Store purchase. Pick one
way to install and stay on it.

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

### From the Microsoft Store

Open the [Store listing](https://apps.microsoft.com/detail/9N8GQS365ZLM) and
select **Get**. Windows downloads, installs and pins it — no SmartScreen warning,
no administrator rights, nothing to run by hand. It is **already licensed**, so
first launch goes straight to setup: your language, your company name and whether
you manage stock **by boxes or by pallets**, then the guided tour. There is no
key to enter. To remove it later, use **Windows Settings → Apps** like any Store
app.

### From the direct download

1. Run `BasicInventory-Setup-x.y.z.exe`.
2. Windows SmartScreen may warn about an unrecognised publisher while this build
   is not yet code-signed. Choose **More info → Run anyway** if you trust the
   download, and check the SHA-256 above first. (The Store build is signed and
   does not do this.)
3. Accept the licence terms, and choose the installation folder if you do not
   want the default one.
4. The installer needs **no administrator rights** and installs for the current
   user. It creates a desktop and a Start menu shortcut.
5. On first launch BasicInventory asks for your language, your company name and
   whether you manage stock **by boxes or by pallets**, then offers a guided tour.
6. Enter your **licence key** when asked. See below.

## Activating your licence

BasicInventory is licensed one way per install, decided by where you got it.

**From the Microsoft Store** the copy is sold already licensed: the licence is
your Store purchase, tied to your Microsoft account, and there is no key to enter
and nothing to activate. Reinstall it — or install it on another PC signed in
with the same Microsoft account — and it is licensed again from the Store.

**From the direct download** the download is free and the **licence key** is what
you buy:

- The key arrives with your purchase, in the store's delivery message. It starts
  with `BI1-`.
- Activation happens **on your computer, offline**: nothing is sent anywhere, and
  no account or registration is involved.
- **Without a key this build cannot be used.** After the first-run setup it shows
  the activation screen and waits for the key; there is no trial mode and no
  read-only mode. Your data is never destroyed by this — activate later and
  everything is where you left it — but the interface stays behind that screen.
- The key stays with your data: restoring a backup on another computer carries
  the licence with it.
- Settings shows which e-mail and order the copy is licensed to. Lost your key?
  Ask through the store you bought from — your order is there.

Either way, to see everything working before you buy, use the browser demo:
[demo.basicinventory.app](https://demo.basicinventory.app).

## Your data and backups

BasicInventory stores your inventory **only on your computer**, and both builds
back it up the same way — from inside the app, so it never depends on where the
files sit. Use **Settings → Backups → Create backup now**, and a copy is also
written automatically every time you close the application. Backups start out in
`Documents\BasicInventory\Copias de seguridad` — a folder you choose, outside the
application, easy to find, copy or sync — and moving to another computer is:
back up, copy the file across, restore it there. That works whichever way either
computer was installed.

The exact folder holding the live database and logs is always shown in
**Settings → Errors and diagnostics**. On the **direct download** it is
`%APPDATA%\BasicInventory`:

| Path | What it is |
| --- | --- |
| `basicinventory.db` | Your inventory (SQLite) |
| `logs\basicinventory.log` | Error log used by **Settings → Errors and diagnostics** |
| `.secret.key` | Local key that encrypts your AI provider key |

The **Store** build keeps the same files in its own per-user app folder (Windows
manages it for packaged apps); the diagnostics screen shows you the path, and the
in-app backup is the supported way to reach the data either way.

Removing the direct download **asks** whether to delete your data, with keeping it
preselected — reinstall and you pick up where you left off. Removing the Store
build follows Windows' own rule for Store apps. Your backups folder, being
outside the application, is never touched either way.

Full walkthrough: [docs/getting-started.md](docs/getting-started.md).

## Updates

**From the Microsoft Store, updates are automatic.** Windows keeps the Store copy
current in the background, the way it does every Store app; you never fetch or
install anything by hand. The rest of this section is about the **direct
download**, which updates itself from this repository.

**Updates are offered, never imposed.** The direct-download build checks this
repository's Releases on startup, and if there is a newer version it tells you — a
strip at the top of the window, never a dialog over what you are doing.

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
the version line you bought — no subscription. The price is the same wherever you
buy; the difference is how the licence reaches you.

| Where | Link | What you get |
| --- | --- | --- |
| **Microsoft Store** (recommended) | **[Get it on the Microsoft Store](https://apps.microsoft.com/detail/9N8GQS365ZLM)** | Buy and install in one step. Licensed to your Microsoft account, no key. Signed, auto-updating. |
| eBay (Spanish listing) | [Buy on eBay](https://www.ebay.es/itm/318673321758) | A `BI1-` key for the direct download. |
| eBay (English listing) | [Buy on eBay](https://www.ebay.es/itm/318673323733) | A `BI1-` key for the direct download. |
| Gumroad | [Buy on Gumroad](https://xabier6.gumroad.com/l/basicinventory) | A `BI1-` key for the direct download. |

The Microsoft Store is the main channel: it is the least to think about, and the
copy arrives signed, already licensed and kept up to date. The eBay and Gumroad
listings sell a `BI1-` key for the direct download instead — the same
application, activated by hand. The two eBay listings are the same product and
differ only in the language of the description; pick whichever you read more
comfortably. See [Two ways to get it](docs/microsoft-store.md) and
[Activating your licence](#activating-your-licence).

Anything about a purchase — invoices, refunds, volume or reseller enquiries —
goes through the store you bought from, using its message system: your order
travels with the question. See [SUPPORT.md](SUPPORT.md).

The licence terms are in [LICENSE.md](LICENSE.md).

## Privacy

BasicInventory is offline-first and stores your inventory **only on your
computer**, in a local SQLite database.

| What leaves your machine | When | To whom |
| --- | --- | --- |
| An update check | On startup, **direct download only** | GitHub (public Releases API) |
| Your question plus the inventory data needed to answer it | Only if you enable the AI assistant, only when you ask something | The AI provider **you** configured |
| Nothing else | — | — |

The Store build makes no update check of its own — Windows updates it — so on a
Store install the only thing that ever leaves your machine is an AI question you
choose to ask.

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

Use **Settings → Backups → Create backup now**, copy the file across, and restore
it from the same screen on the new machine — that works whichever way either
computer was installed, and is the supported route. The live database sits in
`%APPDATA%\BasicInventory\basicinventory.db` on the direct download, or in the
Store build's own per-user folder; either exact path is shown in **Settings →
Errors and diagnostics**.
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
<summary><strong>Should I use the Microsoft Store or the direct download?</strong></summary>

The Store, unless you have a reason not to. It buys and installs in one step, the
package is signed (no SmartScreen warning), it updates itself, and it arrives
already licensed — there is no key to paste. The direct download exists for
buying a `BI1-` key on eBay or Gumroad and activating by hand. They are two
different modes of the same application; a Store purchase is not a key, and a key
is not a Store purchase. See [Two ways to get it](docs/microsoft-store.md).
</details>

<details>
<summary><strong>Why does Windows warn me when I install it?</strong></summary>

Only the **direct download** does this: that installer is not code-signed yet, so
SmartScreen does not recognise the publisher — verify the SHA-256 published with
each release, then **More info → Run anyway**. The **Microsoft Store** build is
signed by Microsoft and installs with no warning.
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
