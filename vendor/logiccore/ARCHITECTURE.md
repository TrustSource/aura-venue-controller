# Architecture: LogicCore runtime

Part of [aura-venue-controller](../../ARCHITECTURE.md) · 2026-11-20 · Diagram: [ARCHITECTURE.drawio](ARCHITECTURE.drawio)

## Overview and purpose

The runtime executes the control application of an installation. It is purchased from the fictional supplier LogicCore as a binary without source code, together with a supplier SBOM and supplier advisories.

## Components and responsibilities

| Component | Responsibility | Origin |
|---|---|---|
| Runtime binary | no source code; contains open-source components that are not visible from outside | purchased, no source code |
| Supplier SBOM | CycloneDX, in the supplier's naming | purchased, no source code |
| Supplier advisory | CSAF with VEX statements | purchased, no source code |
| Release notes | version and changes as text | purchased, no source code |

## Key interfaces and data flows

| From | To | What |
|---|---|---|
| Venue Studio | Runtime | download of the control application, online diagnosis |
| Runtime | Controller services | commands resulting from the control logic |
| Supplier | Aurelia Audio | binary, SBOM (CycloneDX), advisories (CSAF with VEX) |

## Infrastructure and deployment

Shipped as part of the controller's firmware image. Nothing is deployed from this repository.

## Architecture decision records

Decisions for this part are recorded in the ADR section of the repository's
[ARCHITECTURE.md](../../ARCHITECTURE.md). None is specific to this part yet.

## Open decisions

- Which open-source components the stand-in binary is packaged from.
- How far the supplier SBOM deliberately deviates from the real content.

## Status

Concept only; no product code yet.
