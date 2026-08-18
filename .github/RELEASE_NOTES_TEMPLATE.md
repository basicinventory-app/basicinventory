<!--
  Template for a GitHub Release. Copy it, fill it in, delete what does not apply.

  Rules that keep releases trustworthy:
  - Write for the person using the product, not for the developer who wrote it.
  - Every line answers "what changes for me?".
  - Always publish the SHA-256 of the installer.
  - Always state whether a backup is advisable and whether the update is automatic.
  - Credit the people who reported what you fixed.
  - Mirror this content into CHANGELOG.md before publishing.
-->

## BasicInventory vX.Y.Z

One or two sentences: the headline of this release, in plain language.

**Update:** automatic — the application offers it on startup · **Manual download:** installer below
**Backup recommended before updating:** yes / no (say why if yes)

### ✨ New

- **Short title** — what it does for you, in one or two sentences. (#123)

### 🔧 Improved

- **Short title** — what is better now, and where you will notice it. (#124)

### 🐞 Fixed

- **Short title** — what was broken, and when it happened. Thanks @user for the report. (#125)

### ⚠️ Important

- Anything that changes behaviour you relied on, needs a manual step, or removes
  something. Delete this section when it does not apply.

### 📦 Download

Installed from the **[Microsoft Store](https://apps.microsoft.com/detail/9N8GQS365ZLM)**?
Windows updates you automatically — there is nothing to download here. The files
below are the **direct download**, which updates itself and is verified by hand.

| File | Purpose |
| --- | --- |
| `BasicInventory-Setup-X.Y.Z.exe` | Installer (Windows 10/11, 64-bit) |
| `latest.yml` | Update metadata — used by the application, not for manual download |

**SHA-256** of the installer:

```
<paste the hash>
```

Verify it before running:

```powershell
Get-FileHash .\BasicInventory-Setup-X.Y.Z.exe -Algorithm SHA256
```

### 🧾 Notes

- Requires Windows 10 or 11, 64-bit. See the [system requirements](https://github.com/basicinventory-app/basicinventory#system-requirements).
- Installing over an existing version keeps your database and settings.
- The direct-download installer is not code-signed yet, so Windows SmartScreen may warn — check the hash above. The Microsoft Store build is signed and skips this.
- Something wrong? [Report it](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml) with **Settings → Errors and diagnostics → Copy diagnostics**.

**Full changelog:** https://github.com/basicinventory-app/basicinventory/compare/vA.B.C...vX.Y.Z
