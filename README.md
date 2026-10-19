# Lumen Updates

Signed in-place updates for Lumen OS. No ISO download, no reinstall, no partition change.

## Repository layout

- `repo/` — signed APT repository used by the Lumen updater (current package: **1.2.0**).
- `activation/` — one-time activation package for a V1 installation that has never been configured.
- `SIGNING-KEY.asc` — public signing key. Fingerprint `EDEF2384E284EE81BA30859935FF6549F7CAE0C4`, valid until 2028-10-18.
- `SHA256SUMS` — checksums of the published files.
- `TESTS-FR.md` — what was tested, and what was not.

The signing private key is not in this repository and must never be published.

## For an already configured installation (V1.1)

Nothing to download manually: open **Updates**, click **Check for updates**, then install the proposed version. The signature, the repository origin and the package checksum are verified before installation.

## For a V1 installation that is not configured yet

Install `activation/lumen-release_0.4.1_all.deb` once with `apt`, then use **Updates**. This is the only manual step; later releases arrive through the same button.

## V1.2 content

- Liquid Glass visual language for Lumen windows, panel and dock.
- Lumen Spotlight: instant search over installed applications and system settings, with quick Wi-Fi, sound and battery tiles.
- `Super + Space` opens Spotlight from a preloaded process; `Super + A` opens the full application menu.
- The panel entry "LUMEN" is now labelled **Applications** and still opens the same application catalogue.
- Simplified Updates window: one state, one main button, details folded away.
- Animations can be reduced in Personalize; the existing compositor settings are respected.

## Maintenance

This repository is a static, signed APT repository. It has no short-lived metadata expiry, but the owner must keep it updated and renew the signing key before 2028-10-18. Nothing is published automatically. The updater never installs anything without administrator approval.
