# Release notes: v1.0.3

Paste into the GitHub release, with the SHA-256 `pnpm release` prints.

---

## BasicInventory Home v1.0.3

A small addition for anyone who downloaded the application before buying it.

**Update:** offered in the application - **Backup recommended before updating:** no

### Added

- **A "Buy a licence" button on the activation screen.** If you installed
  BasicInventory before buying a licence, the screen that asks for your key used
  to be a dead end. It now has a button that opens the listing - the Spanish one
  if the application is in Spanish, the English one if it is in English.

### Download

| File | Purpose |
| --- | --- |
| `BasicInventory-Setup-1.0.3.exe` | Installer (Windows 10/11, 64-bit) |
| `latest.yml`, `.blockmap` | Update metadata - used by the application |

**SHA-256** of the installer:

```
<pega aqui el hash que imprime pnpm release>
```

```powershell
Get-FileHash .\BasicInventory-Setup-1.0.3.exe -Algorithm SHA256
```

### Notes

- Installing over an earlier version keeps your database, settings and licence.
- Still not code-signed, so Windows SmartScreen may warn - check the hash above.

**Full changelog:** https://github.com/basicinventory-app/basicinventory/compare/v1.0.2...v1.0.3
