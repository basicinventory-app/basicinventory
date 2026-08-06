# Release notes: v1.0.4

Paste into the GitHub release, with the SHA-256 `pnpm release` prints.

---

## BasicInventory Home v1.0.4

Two fixes for anyone running the application in English.

**Update:** offered in the application - **Backup recommended before updating:** no

### Fixed

- **Movement types are no longer shown in Spanish.** Entries, exits, adjustments
  and moves live in a table that is written in one language, and the application
  was showing that stored name — so an English copy read "Salida" and "Ajuste"
  in the movements list, on the dashboard and in the file it exported. The
  interface now translates them itself.

  Your own data is untouched. Product names, reasons and lots stay exactly as you
  typed them, in whatever language you typed them: they are yours, not ours to
  translate.

- **Exported files are named in your language.** An English copy was downloading
  `movimientos.csv` and `productos.csv`; now it gets `movements.csv` and
  `products.csv`.

### Download

| File | Purpose |
| --- | --- |
| `BasicInventory-Setup-1.0.4.exe` | Installer (Windows 10/11, 64-bit) |
| `latest.yml`, `.blockmap` | Update metadata - used by the application |

**SHA-256** of the installer:

```
<pega aqui el hash que imprime pnpm release>
```

```powershell
Get-FileHash .\BasicInventory-Setup-1.0.4.exe -Algorithm SHA256
```

### Notes

- Installing over an earlier version keeps your database, settings and licence.
- Still not code-signed, so Windows SmartScreen may warn - check the hash above.

**Full changelog:** https://github.com/basicinventory-app/basicinventory/compare/v1.0.3...v1.0.4
