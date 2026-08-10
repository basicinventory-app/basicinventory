# Release notes: v1.0.5

Paste into the GitHub release, with the SHA-256 `pnpm release` prints.

---

## BasicInventory Home v1.0.5

A small fix for anyone running the application in English.

**Update:** offered in the application - **Backup recommended before updating:** no

### Fixed

- **The AI provider description now follows your language.** On the AI settings
  screen, when you pick a provider (OpenAI, Anthropic, Gemini, OpenRouter), the
  short line under each name was always shown in Spanish, even with the interface
  in English. It now matches the interface language.

  Nothing else changes: you still bring your own provider and your own key, and
  nothing about how the assistant works is affected.

### Download

| File | Purpose |
| --- | --- |
| `BasicInventory-Setup-1.0.5.exe` | Installer (Windows 10/11, 64-bit) |
| `latest.yml`, `.blockmap` | Update metadata - used by the application |

**SHA-256** of the installer:

```
<pega aqui el hash que imprime pnpm release>
```

```powershell
Get-FileHash .\BasicInventory-Setup-1.0.5.exe -Algorithm SHA256
```

### Notes

- Installing over an earlier version keeps your database, settings and licence.
- Still not code-signed, so Windows SmartScreen may warn - check the hash above.

**Full changelog:** https://github.com/basicinventory-app/basicinventory/compare/v1.0.4...v1.0.5
