# Troubleshooting

Common problems and what to do about them. If none of this helps,
[report it](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml)
with the diagnostics attached.

## First: collect the diagnostics

**Settings → Errors and diagnostics → Copy diagnostics.**

You get the version, your system details, the paths in use and the last errors,
with your Windows user name removed. Paste that into any report — it usually
saves a full round of questions.

## Installation and startup

**The application will not start, or shows "ports 3000/4000 are busy".**
Another copy is already running — check the system tray and Task Manager for
`BasicInventory.exe`, or an old process left over from a crash. End it and start
again.

**The window opens but stays empty.**
Close and reopen. If it persists, the log holds the reason:
**Settings → Errors and diagnostics** shows the log folder and copies the recent
errors. Attach that to a report.

## Data

**My stock is wrong after an exit.**
An exit with no location given takes the earliest expiry first (FEFO), then the
oldest goods — which is not always the row you had in mind. Check
**Movements** for the item: every change is recorded there, with quantity and
location. If the movements do not add up to what stock shows, that is a bug worth
reporting with the item and the dates.

**I cannot register an exit — "not enough stock".**
The quantity is not available in the location the exit points at, or it is spread
across lots the filter excludes. Look at the item's stock by location first.

**I deleted something by mistake.**
Restore the most recent backup (**Settings → Backups**), accepting that work done
after that copy is lost. This is what the automatic backup on close is for.

**I want to start over with an empty database.**
Take a backup first (**Settings → Backups → Create backup now**) so you can
return to your current data. The live database sits in the app folder shown in
**Settings → Errors and diagnostics**; close the application, rename
`basicinventory.db` there (keep it — do not delete), and start again: a fresh
database is created. Restore the backup, or the renamed file, if you change your
mind.

## Updates

**An update has not arrived.**
Windows and the Microsoft Store manage updates in the background — the
application never offers updates itself, so there is nothing to do from inside
it. To check or trigger it, open the **Microsoft Store → Library → Get updates**,
or check for Windows updates. A firewall or proxy that blocks the Microsoft Store
can hold updates back.

## Backups

**"No backup path configured".**
Set the folder in **Settings → Backups**.

**Backups stopped being created.**
The folder was renamed, deleted, or lives on a drive that is not connected.
Check **Settings → Errors and diagnostics** — the failure is logged.

**A backup will not restore.**
The file is not a BasicInventory database, or it was copied while being written
(a common outcome of grabbing a file mid-sync from a cloud folder). Try the
previous copy.

## AI assistant

**"Invalid API key".** Regenerate at the provider and paste again — keys are
often truncated on copy.

**"Model not found".** Your account lacks access to that model, or the identifier
is misspelled. Try the recommended one.

**"Quota exceeded".** Your provider account is out of credit.

**"Could not connect".** No internet, or a firewall blocks the provider domain.

**Answers mention pallets when I work with boxes** (or the reverse). Check
**Settings → Management mode**; the assistant follows it from the next question.

## Performance

**Lists are slow with a lot of data.**
Lower **Settings → Rows per page**, and use filters rather than scrolling. If a
screen takes seconds with fewer than 50.000 movements, report it with the
approximate size of your data — that is a defect, not a limitation.

**The application uses a lot of memory.**
Around 300–500 MB is normal for an Electron application. Significantly more is
worth reporting.

## Still stuck

1. [Search existing issues](https://github.com/basicinventory-app/basicinventory/issues?q=is%3Aissue).
2. Ask in [Discussions → Q&A](https://github.com/basicinventory-app/basicinventory/discussions/categories/q-a).
3. [Open a bug report](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml)
   with the diagnostics, the steps and a screenshot.

Security problems: [SECURITY.md](../SECURITY.md), never a public issue.
