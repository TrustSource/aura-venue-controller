# Architecture: Web UI

Part of [aura-venue-controller](../ARCHITECTURE.md) · 2026-11-20 · Diagram: [ARCHITECTURE.drawio](ARCHITECTURE.drawio)

## Overview and purpose

The web UI is the configuration interface served by the controller itself. It consists of pages written by Aurelia Audio and of open-source server software that is packed into the firmware image as ready-made binaries.

## Components and responsibilities

| Component | Responsibility | Origin |
|---|---|---|
| Configuration pages | zones, sources, network, users | built by Aurelia Audio |
| Script interpreter | bundled binary, version visible only in the binary | open source |
| Web server | bundled binary | open source |
| TLS library | bundled binary, encrypts the connection | open source |

## Key interfaces and data flows

| From | To | What |
|---|---|---|
| Browser in the building LAN | Web server | HTTPS |
| Web server | Script interpreter | page requests |
| Configuration pages | Controller services | reads and changes device configuration |

## Infrastructure and deployment

Shipped as part of the controller's firmware image. Nothing is deployed from this repository.

## Architecture decision records

Decisions for this part are recorded in the ADR section of the repository's
[ARCHITECTURE.md](../ARCHITECTURE.md). None is specific to this part yet.

## Open decisions

- Which web server, interpreter and TLS library are bundled, and in which versions (candidates are named in the project concept, not decided).
- Whether the binaries are stored as files or inside a file-system image.

## Status

Concept only; no product code yet.
