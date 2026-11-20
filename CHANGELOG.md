# Changelog

All notable changes to this project are documented in this file. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), versions follow
[Semantic Versioning](https://semver.org/).

## [Unreleased]

## [0.2.0] - 2026-11-20

### Added

- Documentation site in English and German (`docs/en`, `docs/de`, `mkdocs.yml`, `mkdocs.de.yml`),
  with language switch.
- Pages "Products" and one technical description per component with architecture sketch and links
  to the architecture files in the repositories.
- Architecture files for the building blocks of the controller: `webui/`, `services/`,
  `vendor/logiccore/` (each `ARCHITECTURE.md` and `ARCHITECTURE.drawio`).

### Changed

- Documentation assets moved to `docs/en/assets` and `docs/de/assets`.
- Site address is `https://aura-venue.trustsource.io`.
- README reduced to a pointer to the central documentation, the demo status and the licence
  statement.

## [0.1.0] - 2026-11-20

### Added

- Repository structure: README, CHANGELOG, VERSION, ARCHITECTURE.md with ADR section,
  ARCHITECTURE.drawio.
- `truth.yaml` skeleton for the ground truth of this repository.
- Licence statement (CC BY-SA 4.0 for our own work), `NOTICE.md` and `SBOM.cdx.json` (CycloneDX, no
  third-party components yet).
- Hardware concept of the controller mainboard Rev A (`hardware/README.md`).
- Placeholder for the purchased runtime (`vendor/logiccore/README.md`).
- System overview diagram (`docs/en/assets/system-overview.svg`).
- Documentation site for the whole Aura Venue example: `mkdocs.yml`, `docs/index.md`, workflow
  `docs.yml` publishing to GitHub Pages, Dependabot for GitHub Actions. Design taken from ts-scan.
