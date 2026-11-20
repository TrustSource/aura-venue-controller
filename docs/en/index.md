# Aura Venue

Aura Venue is a **fictional** fixed-installation audio system by the equally fictional Aurelia Audio
GmbH: a controller in the equipment room, network amplifiers throughout the building and an
engineering tool on the planner's PC. TrustSource builds it as a worked example.

This site documents the whole procedure and every design decision along the way. It is meant as a
teaching piece: what does the documentation of a product with digital elements look like when it is
kept from the first day, as the Cyber Resilience Act expects?

![System overview](assets/system-overview.svg)

## Where to start

- [The products](products.md): what the three devices do and who is involved.
- Components, each with a short technical description, an architecture sketch and links to the
  architecture files in its repository:
  [Venue Studio](components/studio.md), [Venue Controller](components/controller.md),
  [Venue OS](components/os.md), [Venue Amp firmware](components/firmware.md).

## The repositories

| Repository | Content | Runs on |
|---|---|---|
| [aura-venue-studio](https://github.com/trustsource/aura-venue-studio) | Engineering software, sample control application | Engineering PC (Windows) |
| [aura-venue-controller](https://github.com/trustsource/aura-venue-controller) | Web UI, controller services, purchased runtime, controller hardware concept | Venue Controller |
| [aura-venue-os](https://github.com/trustsource/aura-venue-os) | Embedded Linux of the controller, in several variants | Venue Controller |
| [aura-venue-firmware](https://github.com/trustsource/aura-venue-firmware) | Bare-metal firmware, amplifier hardware concept | Venue Amp |

## Status

The project has just started. The repositories contain structure and concepts, no product code yet.

## Good to know

The files in the repositories do not have to build or run. They have to look like a real development
project, so that scanning, component identification, vulnerability matching, hardware bills of
materials and device threat analysis can be exercised on realistic input and measured against a
known ground truth.

Aurelia Audio and Aura Venue do not exist. Third-party products and parts named in this
documentation are real and are used as examples only.
