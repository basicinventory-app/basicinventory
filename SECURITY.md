# Security Policy

Thank you for taking the time to report a security problem responsibly. It is
genuinely appreciated.

## Supported versions

| Version | Security fixes |
| --- | --- |
| Latest release (1.x) | ✅ Yes |
| Previous minor version | ✅ Critical only |
| Anything older | ❌ No — please update |

## Reporting a vulnerability

**Do not open a public issue, discussion or pull request for a security
problem.** A public report exposes every installation until a fix ships.

Use GitHub's private reporting:

**[Report a vulnerability](https://github.com/basicinventory-app/basicinventory/security/advisories/new)**

The report is private between you and the maintainer, needs no email exchange,
and becomes a published advisory with credit to you once a fix ships. A GitHub
account is required; creating one is free.

If you cannot use GitHub at all, open a
[Discussion](https://github.com/basicinventory-app/basicinventory/discussions)
saying only that you have a security report — **no details** — and you will be
given a private channel.

### What to include

- The version of BasicInventory and your operating system.
- What the vulnerability allows an attacker to do, and what access they need
  first (local user, network, a file the victim opens…).
- Step-by-step reproduction, ideally with a minimal proof of concept.
- Any log excerpts or screenshots — with your business data removed.

### What happens next

| When | What |
| --- | --- |
| Within 48 hours | Acknowledgement that the report arrived. |
| Within 7 days | An initial assessment: confirmed or not, and a severity. |
| Ongoing | Progress updates at least every two weeks. |
| On release | A fixed version, an advisory, and credit to you unless you prefer to stay anonymous. |

Target fix windows, from confirmation: **critical** 14 days, **high** 30 days,
**medium or low** with the next scheduled release.

## Scope

**In scope** — the BasicInventory desktop application distributed from this
repository's Releases:

- Remote or local code execution, privilege escalation.
- Extraction of the encrypted AI provider key, or of inventory data, by another
  user or process on the same machine.
- Tampering with the update mechanism (serving a forged update).
- Injection into the AI assistant's read-only data layer that reaches tables or
  files it must not reach.
- Anything that sends user data off the machine other than the two documented
  cases (update check, and the AI provider *you* configured).

**Out of scope**:

- Vulnerabilities that require an attacker to already be an administrator on the
  machine, or physical access to an unlocked session.
- The unsigned installer triggering a SmartScreen warning — known and planned.
- The AI provider's own service, its models or its billing.
- Reports produced only by an automated scanner, with no demonstrated impact.
- Denial of service against your own local installation.
- Social engineering of the maintainer or of users.

## Safe harbour

Research done in good faith under this policy will not be met with legal action.
Please: test only against your own installation, do not access, modify or
exfiltrate anyone else's data, do not degrade a third party's service, and give
a reasonable window to fix before disclosing.

## A note on how the product is built

Some things people report as vulnerabilities are deliberate properties, and are
documented so you can check them:

- Your inventory never leaves the machine. There is no telemetry, no analytics
  and no crash upload.
- The AI assistant is off until you configure it, is strictly read-only, and its
  data access is an allowlist of inventory tables — configuration, keys and the
  file system are unreachable.
- Your AI provider key is encrypted (AES-256-GCM) with a machine-local key kept
  outside the database, so a copy of the database file carries no usable
  credential.

If you can demonstrate that any of those statements is false, that is exactly
the kind of report this policy exists for.
