# Architecture: Controller services

Part of [aura-venue-controller](../ARCHITECTURE.md) · 2026-11-20 · Diagram: [ARCHITECTURE.drawio](ARCHITECTURE.drawio)

## Overview and purpose

The controller services are the software Aurelia Audio writes for the device itself: device management, update and audio routing.

## Components and responsibilities

| Component | Responsibility | Origin |
|---|---|---|
| Device management | identity, configuration, state | built by Aurelia Audio |
| Update service | checks and installs firmware images, also for the amplifiers | built by Aurelia Audio |
| Audio routing | distributes sources to zones and amplifiers | built by Aurelia Audio |
| Libraries | from the operating system or bundled | open source |

## Key interfaces and data flows

| From | To | What |
|---|---|---|
| Web UI | Device management | configuration |
| Update service | Amplifiers | firmware images |
| Audio routing | Amplifiers | audio and control over the audio network |
| Device management | Secure element | device key and certificate |

## Infrastructure and deployment

Shipped as part of the controller's firmware image. Nothing is deployed from this repository.

## Architecture decision records

Decisions for this part are recorded in the ADR section of the repository's
[ARCHITECTURE.md](../ARCHITECTURE.md). None is specific to this part yet.

## Open decisions

- Programming language and package ecosystem.
- Protocol between controller and amplifiers.

## Status

Concept only; no product code yet.
