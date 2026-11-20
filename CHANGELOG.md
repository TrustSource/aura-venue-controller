# Changelog

All notable changes to this project are documented in this file. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), versions follow
[Semantic Versioning](https://semver.org/).

## [Unreleased]

## [0.1.0] - 2026-11-20

### Added

- Repository structure: README, CHANGELOG, VERSION, ARCHITECTURE.md with ADR section,
  ARCHITECTURE.drawio.
- `truth.yaml` skeleton for the ground truth of this repository.
- Licence statement (CC BY-SA 4.0 for our own work), `NOTICE.md` and `SBOM.cdx.json` (CycloneDX, no
  third-party components yet).
- Hardware concept of the controller mainboard Rev A (`hardware/README.md`).
- Placeholder for the purchased runtime (`vendor/logiccore/README.md`).
- System overview diagram (`docs/assets/system-overview.svg`).
- Documentation site for the whole Aura Venue example: `mkdocs.yml`, `docs/index.md`, workflow
  `docs.yml` publishing to GitHub Pages, Dependabot for GitHub Actions. Design taken from ts-scan.
