# Repository setup

Maintainer notes: how this repository is configured and why. Public on purpose —
there is nothing secret here, and it documents the promises made to users.

## 1. Before anything else

This repository is the **public face** of a closed-source product. One rule
governs everything below:

> Nothing that reveals the application's source, its internal structure or a
> customer's data ever gets committed here.

The `.gitignore` blocks installers, databases and logs, but the real safeguard is
habit: this repository contains Markdown, YAML and images. Nothing else.

## 2. Repository settings

**Settings → General**

| Setting | Value | Why |
| --- | --- | --- |
| Visibility | **Public** | Users must reach releases and issues without an account barrier. |
| Default branch | `main` | — |
| Issues | **On** | Bug reports and feature requests. |
| Discussions | **On** | Questions, ideas, announcements. |
| Projects | **Off** | Milestones plus the `planned` label already say what is coming; a board would be a third place to keep in sync. Turn on only if you actually work a board daily. |
| Wiki | **Off** | Documentation belongs in `docs/`, versioned with the repository and reviewable. |
| Sponsorships | **On** | `.github/FUNDING.yml` points the button at the Microsoft Store listing — buying a licence is how this is funded, so the button is a buy button. |
| Preserve this repository | On | Cheap insurance. |
| Allow merge commits / squash / rebase | Irrelevant | There are no pull requests. |

**Settings → General → Features → Releases**: on. This is the distribution
channel and the update feed the application reads.

**Settings → Branches → Branch protection for `main`**

- Require a pull request before merging: **off** (you are the only writer).
- Restrict who can push: yourself and the release automation only.
- Do not allow force pushes: **on** — release tags must stay stable, because
  installed applications resolve updates against them.

**Settings → Actions → General**

- Actions permissions: allow actions created by GitHub plus the specific verified
  actions used in `.github/workflows`.
- Workflow permissions: **read repository contents**, and grant `issues: write`
  per workflow (already declared in each file).

**Settings → Code security**

- Private vulnerability reporting: **on**. This powers the "Report a
  vulnerability" link in `SECURITY.md`.
- Secret scanning: **on**.

**Settings → Moderation**

- Interaction limits are a useful emergency brake if a thread goes bad.
- Community rules live in `CONTRIBUTING.md`; they are what you point at when moderating a thread.

## 3. Repository description and topics

- **Description**: "Desktop inventory management for small businesses. Releases,
  documentation and support — the source is private."
- **Website**: your store or product page.
- **Topics**: `inventory`, `inventory-management`, `warehouse`, `stock-control`,
  `desktop-app`, `windows`, `electron`, `small-business`, `closed-source`.
- Pin nothing that suggests source code is available.

## 4. Labels

Defined in [`labels.yml`](labels.yml) and applied by the
[sync-labels](workflows/sync-labels.yml) workflow. The set, in short:

| Group | Labels |
| --- | --- |
| Type | `bug`, `enhancement`, `documentation`, `question`, `support`, `security` |
| Pipeline | `needs triage`, `needs info`, `confirmed`, `planned`, `in progress`, `fixed` |
| Resolution | `duplicate`, `invalid`, `wontfix`, `stale` |
| Area | `area/inventory`, `area/ai-assistant`, `area/backups`, `area/installer`, `area/ui`, `area/performance` |
| Priority | `priority/critical`, `priority/high`, `priority/low` |
| Community | `good first issue`, `help wanted` |

Two habits make labels worth having: every open issue carries exactly one **type**
label, and every issue you have looked at loses `needs triage`.

## 5. Milestones

One per release, created when the version is decided, not when it ships.

| Milestone | Contents |
| --- | --- |
| `v1.0.0` | First public release. |
| `v1.1.0` | Whatever the first weeks of feedback promote, plus code signing. |
| `Backlog` | Accepted but unscheduled — keeps `planned` issues out of the version milestones. |

Give each version milestone a target date even if it slips: an empty date reads
as an abandoned project.

Milestones plus the `planned` label are the whole public plan. There is no
`ROADMAP.md` on purpose: a file promising features is a file that goes stale and
turns into a list of things you did not do.

## 6. Discussion categories

Create these, delete GitHub's defaults you will not use:

| Category | Format | Purpose |
| --- | --- | --- |
| 📣 Announcements | Announcement | Releases, maintenance windows, policy changes. Maintainer only. |
| 💬 Q&A | Question / answer | "How do I…?" — mark an answer as accepted; it becomes the searchable result. |
| 💡 Ideas | Open discussion | Improvements before they become feature requests. Upvotes set priority. |
| 🛠️ Show and tell | Open discussion | How people actually run their warehouse with it. |
| 🧭 General | Open discussion | Everything else. |

Category form templates live in [`DISCUSSION_TEMPLATE/`](DISCUSSION_TEMPLATE) and
must be named after the category slug (`q-a.yml`, `ideas.yml`,
`show-and-tell.yml`).

Announce every release in **Announcements** with a link to the release. Users
watch discussions more reliably than they watch releases.

## 7. Release process

BasicInventory ships **only through the Microsoft Store**; this repository holds
no installer, no `latest.yml` and no GitHub Releases.

1. Build the MSIX package from the **private** source repository
   (`pnpm package:store`) and submit it to the Microsoft Store through Partner
   Center. The Store signs, distributes and updates it — there is nothing to
   upload here.
2. Write the user-facing notes with
   [`RELEASE_NOTES_TEMPLATE.md`](RELEASE_NOTES_TEMPLATE.md) for the CHANGELOG and
   the announcement (Partner Center also shows its own per-version notes).
3. Mirror the same content into [`CHANGELOG.md`](../CHANGELOG.md).
4. Close the milestone; comment on every issue in it saying which version fixed
   it, and label them `fixed`. Closing them is what removes them from the
   public "what's next" list — there is no roadmap file to edit, on purpose.
5. Post the announcement discussion.

Never delete or re-tag a published release: installed applications resolve
updates against those tags. Publish a patch instead.

Mark a release as **pre-release** whenever it should not reach the auto-updater.

## 8. Triage routine

Once or twice a week, not continuously:

1. New issues: add a type label, an area label, and `needs triage` comes off.
2. Missing information → ask, and label `needs info`. The
   [stale](workflows/stale.yml) workflow closes those that go quiet; nothing
   else is auto-closed.
3. Reproduced → `confirmed` plus a priority.
4. Accepted feature → `planned` and a milestone. That label **is** the public roadmap, so it has to mean something: only apply it to work you intend to do.
5. Declining is fine, and always comes with a reason and a `wontfix` label. An
   unanswered request is worse than a declined one.

## 9. Best practices for a public repository of commercial software

- **Say what it is, immediately.** The README states in its first screen that the
  product is closed source and where to buy it. Discovering that after cloning
  wastes someone's evening and earns real resentment.
- **Never leak the source by accident.** No stack traces with file paths from the
  private repository, no internal architecture documents, no screenshots of the
  editor.
- **Let the Store carry the trust.** Shipping only through the Microsoft Store
  means Windows signs and delivers every copy — the single biggest trust signal
  for an app from an unknown vendor, with no unsigned `.exe` for anyone to
  second-guess.
- **Answer, even when the answer is no.** A tracker where every issue gets a
  human reply within a week reads as a maintained product regardless of its size.
- **Write the changelog for users.** "Fixed a race condition in the stock
  service" means nothing; "Stock no longer shows the old quantity after a fast
  double adjustment" does.
- **Protect user data in the open.** Templates warn against posting keys,
  invoices and backups; enforce it by editing posts that contain them and saying
  why.
- **Do not fake activity.** No sock-puppet issues, no inflated star counts. A
  small, honest tracker beats a padded one.
- **Keep the promises documented.** Privacy claims in the README and SECURITY.md
  are commitments; if the product changes, change them in the same release.
- **Automate the boring parts only.** Labels and stale handling are automated
  here; triage and answers are not, because that is where trust is actually
  built.

## 10. Launch checklist

- [x] Microsoft Store URL in `README.md`, `SUPPORT.md` and
      `.github/FUNDING.yml`. The Store is the only sales channel.
- [ ] Confirm the licence text fits how you actually sell (jurisdiction,
      one-device wording) in `LICENSE.md`, and that it matches the copies shown
      during setup (`assets/license_es.txt`, `license_en.txt` in the private
      repository).
- [ ] Add real screenshots to `docs/images/`.
- [ ] Turn on Issues, Discussions and private vulnerability reporting; turn off
      Wiki and Projects.
- [ ] Create the discussion categories, then run the label sync workflow.
- [ ] Create the `v1.0.0` milestone.
- [ ] Publish v1.0.0 through the Microsoft Store (Partner Center), then post the
      announcement discussion.
- [ ] Test the whole path yourself on a clean Windows machine: install from the
      Store → get a Store update → report a bug from inside the application.
