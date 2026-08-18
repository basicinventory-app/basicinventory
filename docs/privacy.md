# Privacy

BasicInventory is offline-first. Your inventory is stored **on your computer**,
in a local database, and is not sent anywhere.

Last updated: 2026-08-18.

## What is collected

**Nothing.** No telemetry, no usage analytics, no crash reporting service, no
account, no registration, no phone-home.

The maintainer cannot see your data, your company name, how often you use the
application, or whether you use it at all.

## What leaves your computer, and when

Exactly one thing, visible and avoidable: a question you send to the AI
assistant, and only if you enable it. The application makes **no update check of
its own** — Windows updates it through the Microsoft Store — so nothing leaves
your machine on startup or in the background.

### Your questions to the AI assistant — only if you enable it

The assistant is off until you configure a provider. Once you do, asking a
question sends to **the provider you chose, with your own credentials**:

- the question and the conversation so far,
- the inventory data needed to answer it.

That exchange is governed by your agreement with that provider. BasicInventory is
not an intermediary: it neither sees nor stores those exchanges.

Do not want that? Do not configure the assistant. Everything else works.

## Where your data is stored

Your inventory, the error log and the local encryption key sit in a per-user
application folder that Windows manages for Store apps. **Settings → Errors and
diagnostics** shows the exact folder in use.

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

Buying a licence happens on the **Microsoft Store**, which handles your payment
details under its own privacy policy. Those details never reach the application.
The purchase is tied to your Microsoft account by Microsoft, not by
BasicInventory; the application receives no account information.

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
