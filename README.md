# VORYN Releases

Public release and auto-update channel for the **VORYN launcher**, the official desktop launcher for Doombringerz.

This repository contains **no source code**. It hosts only the release artifacts that the launcher's built-in updater consumes: the update manifest (`latest.json`), the packaged installer, and its signature. The launcher itself is developed in a separate private repository.

## Download the launcher

Grab the latest Windows installer from the [Releases](https://github.com/Doombringerz/voryn-releases/releases/latest) page:

- `VORYN_x.x.x_x64-setup.exe`: the full installer. Download and run it.

On first launch, Windows SmartScreen may warn about an unknown publisher. Choose **More info -> Run anyway** to continue.

## How auto-update works

VORYN is built with [Tauri](https://tauri.app), and its updater checks this repository for new versions on launch.

1. The updater fetches the manifest at:
   ```
   https://github.com/Doombringerz/voryn-releases/releases/latest/download/latest.json
   ```
2. `latest.json` reports the newest version, release notes, and a signed download URL for the update bundle.
3. If a newer version is available, the updater downloads the bundle and verifies its **minisign** signature against the public key embedded in the launcher. An update is applied only if the signature is valid.
4. The user is prompted, and the update installs on next launch.

Because every update is cryptographically signed and verified against a pinned public key, a tampered or unofficial build cannot be delivered through this channel.

## Release assets

Each published release contains:

| Asset | Purpose |
|---|---|
| `latest.json` | Update manifest the Tauri updater reads |
| `VORYN_x.x.x_x64-setup.exe` | Full Windows installer for new users |
| `VORYN_x.x.x_x64-setup.nsis.zip` | Update bundle applied by the updater |
| `VORYN_x.x.x_x64-setup.nsis.zip.sig` | minisign signature for the update bundle |

## Versioning

Releases follow [Semantic Versioning](https://semver.org/). See [CHANGELOG.md](CHANGELOG.md) for the release history.

## Support

For issues with the launcher, contact Doombringerz through the official channels at [doombringerz.com](https://doombringerz.com).

---

(c) Doombringerz - All Rights Reserved.
