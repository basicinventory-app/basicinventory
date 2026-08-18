# Two ways to get it: Microsoft Store or direct download

BasicInventory ships as two builds of the **same application**. They differ only
in how you buy it, how it installs, how it updates and how it is licensed — the
screens, the data and every rule inside are identical.

**The Microsoft Store is the main channel.** It is the least to think about: one
step to buy and install, signed by Microsoft, kept up to date by Windows, and
sold already licensed. The direct download exists for buying a `BI1-` licence key
on eBay or Gumroad and activating the application by hand.

## At a glance

| | Microsoft Store — recommended | Direct download |
| --- | --- | --- |
| Where you buy | [Microsoft Store](https://apps.microsoft.com/detail/9N8GQS365ZLM) | [eBay](https://www.ebay.es/itm/318673321758) or [Gumroad](https://xabier6.gumroad.com/l/basicinventory) |
| How it installs | **Get** in the Store — one step | Run `BasicInventory-Setup-x.y.z.exe` |
| Signed? | Yes, by Microsoft — no SmartScreen warning | Not yet code-signed — SmartScreen may warn |
| Licence | The purchase itself, tied to your Microsoft account — **no key** | A `BI1-` key you paste once, activated offline |
| Updates | Automatic, through Windows / the Store | Offered by the app, from GitHub Releases — you choose when |
| Removing it | Windows Settings → Apps | Uninstaller **asks** before deleting your data |
| Administrator rights | None | None |

## What is the same

- **The application.** Same features, same screens, same boxes-or-pallets model,
  same AI assistant on your own provider key. Nothing is held back on either
  build.
- **Your data stays on your computer.** Offline-first, a local SQLite database,
  no telemetry. See [privacy](privacy.md).
- **Backups and moving between computers.** Both build back up from inside the
  app (**Settings → Backups → Create backup now**, plus an automatic copy on
  close) into a folder you choose under your Documents. To move machines: back
  up, copy the file across, restore it — regardless of how either computer was
  installed.
- **The price.** One perpetual licence for the 1.x line, no subscription. See
  [buying a licence](../README.md#buying-a-licence).

## What is different

### Buying and licensing

On the **Store**, the purchase *is* the licence. It is tied to your Microsoft
account, so first launch goes straight to setup with nothing to activate, and
reinstalling — or installing on another PC signed in with the same account —
licenses it again from the Store. There is no key to keep or lose.

On the **direct download**, the download is free and the key is what you buy. It
arrives with your eBay or Gumroad purchase, starts with `BI1-`, and is checked
**on your computer, offline** — no account, nothing sent anywhere. Without a key
this build stays on its activation screen. The key travels with your data, so a
restored backup carries the licence with it. Lost the key? Ask through the store
you bought from; your order is there.

### Installing and the SmartScreen warning

The Store build is signed by Microsoft and installs with no warning. The direct
installer is not code-signed yet, so Windows SmartScreen may flag an unrecognised
publisher — verify the SHA-256 the release lists, then **More info → Run anyway**.
Code signing the direct installer is planned; the Store build already clears this.

### Updates

The Store build is updated by Windows in the background, like any Store app —
nothing to fetch or install by hand, and it makes no update check of its own. The
direct download checks GitHub Releases on startup and only *offers* an update;
downloading and installing are separate steps you trigger, and it never restarts
on its own. See [Updates](../README.md#updates).

### Removing it, and your data

Removing the direct download **asks** whether to delete your data, with keeping it
preselected, so a reinstall picks up where you left off. Removing the Store build
follows Windows' own rule for Store apps. Either way your backups folder, being
outside the application, is never touched — which is the real reason to set a
backup folder before entering real data ([getting started](getting-started.md)).

The live database and logs sit in `%APPDATA%\BasicInventory` on the direct
download, and in the Store build's own per-user app folder that Windows manages
for packaged apps. You rarely need the raw path — the in-app backup is the
supported way to reach your data — but **Settings → Errors and diagnostics**
always shows the exact folder in use.

## Which should I choose?

Take the **Microsoft Store** unless you have a specific reason not to: it is
signed, it updates itself, it is licensed the moment you buy, and there is nothing
to paste or verify. Reach for the **direct download** when you would rather buy on
eBay or Gumroad, or need to install without the Store. They are two different
modes — a Store purchase is not a `BI1-` key, and a key is not a Store purchase —
so pick one way to install and stay on it.

Not sure yet? [Try the browser demo](https://demo.basicinventory.app) first — the
whole application on a sample warehouse, nothing to install.
