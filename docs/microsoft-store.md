# How to get BasicInventory

BasicInventory is on the **[Microsoft Store](https://apps.microsoft.com/detail/9N8GQS365ZLM)**,
and that is the one place to buy and install it. Buying and installing are a
single step, and the copy arrives signed, already licensed and kept up to date by
Windows.

Want to see it working before you buy? [Try the browser demo](https://demo.basicinventory.app)
first — the whole application on a sample warehouse, nothing to install.

## Installing

Open the [Store listing](https://apps.microsoft.com/detail/9N8GQS365ZLM) and
select **Get**. Windows downloads, installs and pins it — no security warning,
no administrator rights, nothing to run by hand. On first launch it goes straight
to setup: your language, your company name and whether you manage stock **by boxes
or by pallets**, then a guided tour.

To remove it later, use **Windows Settings → Apps**, like any Store app.

## Your licence

The purchase *is* the licence. It is tied to your Microsoft account, so there is
nothing to activate: no key to paste, no activation screen, no registration.
Reinstall it — or install it on another PC signed in with the same Microsoft
account — and it is licensed again from the Store.

## Updates

Windows keeps the Store copy up to date in the background, like any Store app —
nothing to fetch or install by hand, and the application makes no update check of
its own. Installing an update keeps your database and settings. See
[Updates](../README.md#updates).

## Your data, backups and moving between computers

Your inventory is stored **only on your computer**, offline-first, in a local
SQLite database — no telemetry. See [privacy](privacy.md).

BasicInventory backs up from inside the app (**Settings → Backups → Create backup
now**, plus an automatic copy on close) into a folder you choose under your
Documents. To move machines: back up, copy the file across, restore it. Your
backups folder sits outside the application, so an uninstall never touches it —
which is the real reason to set a backup folder before entering real data
([getting started](getting-started.md)).

The live database and logs sit in a per-user application folder that Windows
manages for Store apps. You rarely need the raw path — the in-app backup is the
supported way to reach your data — but **Settings → Errors and diagnostics**
always shows the exact folder in use.

## Refunds and purchase questions

Anything about a purchase — invoices, refunds, volume or reseller enquiries —
goes through the Microsoft Store's own purchase and refund policy, which keeps it
attached to your order. See [SUPPORT.md](../SUPPORT.md).
