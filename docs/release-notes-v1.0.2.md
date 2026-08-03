# Release notes: v1.0.2

Paste into the GitHub release, with the SHA-256 `pnpm release` prints.

---

## BasicInventory Home v1.0.2

One fix, and a good one if it ever bit you.

**Update:** offered in the application - **Backup recommended before updating:** no

### Fixed

- **BasicInventory no longer fights over ports 3000 and 4000.** It used to serve
  itself on those two, which are the first ports any development tool grabs. If
  something else on your computer was already using one, the application simply
  would not open.

  It now uses a single, uncommon port, chosen when it starts, and quietly moves
  to another if that one is taken. There is nothing to configure and nothing to
  remember.

### Download

| File | Purpose |
| --- | --- |
| `BasicInventory-Setup-1.0.2.exe` | Installer (Windows 10/11, 64-bit) |
| `latest.yml`, `.blockmap` | Update metadata - used by the application |

**SHA-256** of the installer:

```
<pega aqui el hash que imprime pnpm release>
```

```powershell
Get-FileHash .\BasicInventory-Setup-1.0.2.exe -Algorithm SHA256
```

### Notes

- Installing over an earlier version keeps your database, settings and licence.
- Still not code-signed, so Windows SmartScreen may warn - check the hash above.

**Full changelog:** https://github.com/basicinventory-app/basicinventory/compare/v1.0.1...v1.0.2
