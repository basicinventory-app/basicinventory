# Privacy

BasicInventory is offline-first. Your inventory is stored **on your computer**,
in a local database, and is not sent anywhere.

Last updated: 2026-07-29.

## What is collected

**Nothing.** No telemetry, no usage analytics, no crash reporting service, no
account, no registration, no phone-home.

The maintainer cannot see your data, your company name, how often you use the
application, or whether you use it at all.

## What leaves your computer, and when

Exactly two things, both visible and both avoidable:

### 1. The update check — direct download only

On the **direct download**, the application asks GitHub on startup whether a newer
release exists. It is an anonymous, read-only request to a public API. GitHub,
like any web server, sees the request and your IP address; BasicInventory sends
nothing about you or your data.

The **Microsoft Store** build makes no such check: Windows updates it the way it
updates every Store app, so this request does not happen at all. On a Store
install the only thing that ever leaves your machine is an AI question you choose
to ask, below.

### 2. Your questions to the AI assistant — only if you enable it

The assistant is off until you configure a provider. Once you do, asking a
question sends to **the provider you chose, with your own credentials**:

- the question and the conversation so far,
- the inventory data needed to answer it.

That exchange is governed by your agreement with that provider. BasicInventory is
not an intermediary: it neither sees nor stores those exchanges.

Do not want that? Do not configure the assistant. Everything else works.

## Where your data is stored

`%APPDATA%\BasicInventory`:

| File | Contents |
| --- | --- |
| `basicinventory.db` | Your entire inventory (SQLite) |
| `logs\basicinventory.log` | Local error log, rotated, capped in size |
| `.secret.key` | Local key encrypting your AI provider key |

Backups go wherever you point them in Settings — including a synced folder, which
means your data then also lives with that provider. Your choice, worth being
aware of.

## Your AI provider key

- Encrypted at rest with **AES-256-GCM**.
- The encryption key lives **outside** the database, in `.secret.key` (or in the
  `BASICINVENTORY_SECRET` environment variable when set), so a copy of the
  database — a backup, a file sent to support — carries no usable credential.
- The application never displays the key, only a masked hint like `••••1234`.
- Deleting the provider deletes the key.

## The error log

Errors are written locally so a problem can be diagnosed after the fact. The log
contains error messages, stack traces and file paths — no inventory rows.

**Settings → Errors and diagnostics** shows the recent entries and copies them as
text, with your Windows user name removed from paths. Nothing is uploaded: you
decide whether to attach it to a report.

Rotated automatically at 2 MB, keeping three files. Delete the folder any time.

## Personal data (GDPR)

BasicInventory processes no personal data on the maintainer's behalf. There is no
server, no account and no collection, so there is no controller-processor
relationship to document for the application itself.

If **you** store personal data inside your inventory — a person's name in a lot
reference, for example — you remain its sole controller: it is on your machine,
under your backups, and it reaches a third party only if you enable the AI
assistant and ask a question that includes it.

## Purchases

Buying a licence happens on the store platform — the Microsoft Store, eBay or
Gumroad — which handles your payment details under its own privacy policy. Those
details never reach the application. A Microsoft Store purchase is tied to your
Microsoft account by Microsoft, not by BasicInventory; the application receives
no account information.

## Children

BasicInventory is business software and is not directed at children.

## Changes to this policy

Material changes are announced in the release notes and in
[Discussions → Announcements](https://github.com/basicinventory-app/basicinventory/discussions/categories/announcements),
with the date above updated. Claims made here are commitments: if the product
ever changes what it sends, this page changes in the same release.

## Questions

Open a [discussion](https://github.com/basicinventory-app/basicinventory/discussions),
or use the private address in [SUPPORT.md](../SUPPORT.md).
