# Changelog

Release history for the VORYN launcher, published through this channel. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versions follow [Semantic Versioning](https://semver.org/).

## [0.1.4] - 2026-04-20

### Security
- Signed auto-update pubkey and endpoint wired in (updater activates once the first signed release is published here)
- Upgraded the WebSocket TLS stack to resolve certificate-validation CVEs
- Bundled dependency security bumps for archive extraction and template handling

### Added
- Signed release pipeline producing the NSIS installer plus `latest.json` and its signature
- Crash reporting: unhandled panics write a log to `%APPDATA%\VORYN\crashes\`

### Changed
- Installers are distributed through GitHub Releases only, no longer tracked in source

[0.1.4]: https://github.com/Doombringerz/voryn-releases/releases/tag/v0.1.4
