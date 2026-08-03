# Backups and restore

Your inventory lives in a single file on your computer. That makes backups both
simple and entirely your responsibility.

## What is backed up

A complete copy of `basicinventory.db`: items, locations, stock, movements,
settings — everything except the log file and your AI provider key, which stays
encrypted with a machine-local key that is deliberately **not** part of the copy.

The copy is taken with SQLite's `VACUUM INTO`, so it is consistent even if you
happen to be working while it runs, and it is compacted on the way out.

## Automatic backups

A copy is written **every time you close the application**. Nothing to remember,
nothing to schedule.

Configure it in **Settings → Backups**:

| Setting | What it does |
| --- | --- |
| Backups folder | Where copies are written. Starts at `Documents\BasicInventory\Copias de seguridad`; move it to a synced folder (OneDrive, Drive) or an external drive if you can. |
| Backups to keep | Older copies beyond this number are deleted after each new one. |

Files are named `basicinventory-YYYYMMDD-HHMMSS.db`, so they sort
chronologically.

## Manual backup

**Settings → Backups → Create backup now.** Do this before anything risky: a bulk
adjustment, a stock count, an application update, or trying something out.

## Restoring

**Settings → Backups** lists the copies in your folder. **Restore** on any of
them:

1. The file is validated first — a corrupt or unrelated `.db` is refused.
2. Your current database is replaced.
3. The application reloads with the restored data.

> **Restoring replaces everything.** Work done after that copy was taken is gone.
> Take a manual backup first if the current state has anything worth keeping.

To restore a file from elsewhere — a USB stick, another computer — use
**Upload backup…**, which stores it in your backups folder and validates it
before it appears in the list.

## Moving to another computer

1. On the old machine: **Create backup now**.
2. Copy the `.db` file across.
3. On the new machine: install BasicInventory, complete the initial setup
   (anything you type is about to be replaced), then **Upload backup… → Restore**.

Your AI provider key does not travel: re-enter it on the new machine. That is by
design — a copied database carries no usable credential.

## The 3-2-1 rule, adapted

For a business that would struggle to reconstruct its stock from memory:

- **3 copies** — the live database, the automatic local copies, and one more.
- **2 media** — the computer's disk, plus an external drive or cloud folder.
- **1 off-site** — a synced folder counts, as long as you have checked it is
  actually syncing.

Pointing the backups folder at a synced folder covers most of this in one
setting.

## Test a restore

An untested backup is a hope, not a backup. Once, after setting things up:

1. Create a backup.
2. Change something harmless (add a test item).
3. Restore the backup.
4. Confirm the test item is gone.

Now you know the whole path works, and you have used the restore screen before
the day you need it in a hurry.

## Common problems

**"No backup path configured"** — set the folder in **Settings → Backups**.

**Backups are not being created on close** — check that the folder still exists
and is writable. A disconnected external drive or a renamed synced folder is the
usual cause. The application logs the failure in **Settings → Errors and
diagnostics**.

**The folder is filling up** — lower **Backups to keep**. Each copy is roughly
the size of your database.

**"The backup is not valid"** — the file is not a BasicInventory database, or it
was copied while being written (from a synced folder mid-upload, for example).
Try another copy.
