# Release notes: v1.0.1

Ready to paste into the GitHub release. Replace the SHA-256 with the one
`pnpm release` prints for the build you actually publish.

---

## BasicInventory Home v1.0.1

A first round of fixes from using 1.0.0 in earnest. Small, and all of it about
being clearer.

**Update:** offered in the application · **Backup recommended before updating:** no

### 🔧 Improved

- **The assistant says it can be wrong.** A permanent line under the message
  box: AI can get things wrong, so check anything you are about to act on
  against your data. Worth saying out loud, and now always visible.

### 🐞 Fixed

- **"Check for updates" no longer shows a raw 404.** When the updates
  repository cannot be reached — no internet, a company firewall, a proxy with
  its own certificate — you now get a sentence in your own language saying so,
  with the suggestion to check the connection and a reminder that the installer
  can always be downloaded by hand. The technical detail still goes to the log,
  where support can read it.
- **Attached technical information stayed inside the dialog.** In "Report a
  problem", pressing "See what is attached" used to push the dialog sideways
  when a path or a stack trace had no spaces to break at. It wraps now. The same
  fix went into the error details in **Settings → Errors and diagnostics** and
  into the crash screen.

### 📦 Download

| File | Purpose |
| --- | --- |
| `BasicInventory-Setup-1.0.1.exe` | Installer (Windows 10/11, 64-bit) |
| `latest.yml`, `.blockmap` | Update metadata — used by the application, not for manual download |

**SHA-256** of the installer:

```
<pega aquí el hash que imprime pnpm release>
```

```powershell
Get-FileHash .\BasicInventory-Setup-1.0.1.exe -Algorithm SHA256
```

### 🧾 Notes

- Installing over 1.0.0 keeps your database, your settings and your licence.
- The installer is still not code-signed, so Windows SmartScreen may warn —
  check the hash above.

**Full changelog:** https://github.com/basicinventory-app/basicinventory/compare/v1.0.0...v1.0.1
