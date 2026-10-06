# Third-party components

BasicInventory is proprietary software built on open-source components. Their
licences are honoured, their notices ship with the application, and they are
listed here so you know what is inside what you installed.

This page names the principal components and their licences. The complete,
authoritative list — every transitive dependency with its full licence text —
is generated at build time from the real dependency graph and installed with
the application at:

```
%LOCALAPPDATA%\Programs\BasicInventory\LICENSES.chromium.html
%LOCALAPPDATA%\Programs\BasicInventory\resources\THIRD-PARTY-NOTICES.txt
```

## Runtime and platform

| Component | Licence | What it does here |
| --- | --- | --- |
| [Electron](https://www.electronjs.org/) | MIT | Desktop application shell |
| [Chromium](https://www.chromium.org/) | BSD-3-Clause and others | Rendering engine inside Electron |
| [Node.js](https://nodejs.org/) | MIT | JavaScript runtime |
| [SQLite](https://www.sqlite.org/) | Public domain | The local database engine |

## Application

| Component | Licence | What it does here |
| --- | --- | --- |
| [React](https://react.dev/) | MIT | User interface |
| [Next.js](https://nextjs.org/) | MIT | Application framework for the interface |
| [Express](https://expressjs.com/) | MIT | Local HTTP layer between interface and data |
| [Prisma](https://www.prisma.io/) | Apache-2.0 | Database access and migrations |
| [Tailwind CSS](https://tailwindcss.com/) | MIT | Styling |
| [Radix UI](https://www.radix-ui.com/) | MIT | Accessible interface primitives |
| [Lucide](https://lucide.dev/) | ISC | Icons |
| [three.js](https://threejs.org/) | MIT | 3D rendering of the warehouse map |
| [React Three Fiber](https://r3f.docs.pmnd.rs/) | MIT | React bindings for the 3D map |
| [TanStack Query / Table](https://tanstack.com/) | MIT | Data fetching and tables |
| [Zod](https://zod.dev/) | MIT | Input validation |
| [pino](https://getpino.io/) | MIT | Logging |
| [electron-updater](https://www.electron.build/) | MIT | Checking for and installing updates |

## Fonts

| Font | Licence |
| --- | --- |
| [Manrope](https://fonts.google.com/specimen/Manrope) | SIL Open Font License 1.1 |
| [Sora](https://fonts.google.com/specimen/Sora) | SIL Open Font License 1.1 |
| [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) | SIL Open Font License 1.1 |

Fonts are bundled with the application; no font is fetched from the internet at
runtime.

## Optional AI providers

Connecting an AI provider uses that provider's own API under **your** account and
their terms. No provider software is bundled with BasicInventory beyond the
official Anthropic SDK (MIT); the other providers are reached over plain HTTPS.

## Notes

- Including these components does not place BasicInventory itself under their
  licences: they are used as libraries and dependencies, and BasicInventory's own
  source remains proprietary and private.
- Nothing here grants rights in BasicInventory. See [LICENSE.md](../LICENSE.md).
- Think a component is missing or mis-attributed? Please
  [tell us](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml)
  — attribution mistakes are treated as defects.
