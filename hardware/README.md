# Venue Controller: hardware concept (mainboard Rev A)

Version 0.1.0 · 2026-11-20

This is the list of main parts a manufacturer would declare in a hardware bill of materials (HBOM).
It is not a schematic. The parts are real, common types, so that manufacturer plus part number is a
valid identity. The board itself is fictional.

## Verification

The parts were checked on 2026-11-20 against manufacturer pages, distributors and the NVD API. The column
"Verified by" says how reliable an entry is:

- **manufacturer**: read on the manufacturer's own page
- **distributor**: seen at distributors only
- **open**: not confirmed

Pages of Micron and Microchip could not be retrieved, so first-hand confirmation is missing there.

## Parts

| Function | Part | Order code | Role | Security-relevant characteristics | Verified by |
|---|---|---|---|---|---|
| Application processor | NXP i.MX 8M Mini | MIMX8MM6CVTKZAA (industrial) | runs Linux | 4 x Arm Cortex-A53 plus Cortex-M4; secure boot via HABv4 possible; JTAG present | manufacturer (active); HAB and JTAG from secondary sources only |
| Memory | Micron LPDDR4, 2 GB | MT53E512M32D1ZW-046 WT:B | | | distributor; lifecycle status inconsistent between sources |
| Mass storage | Micron eMMC, 16 GB | MTFC16GAPALBH-IT | holds firmware and data | soldered, writable storage | distributor; lifecycle status inconsistent (partly listed as obsolete) |
| Power management | NXP PCA9450A | PCA9450AAHNY | | | manufacturer (active, designed for the i.MX 8M family) |
| Network (2 x) | Microchip KSZ9031RNX | KSZ9031RNXIA | building LAN and audio network | two Ethernet interfaces | distributor and datasheet copy; status open |
| Secure element | NXP EdgeLock SE050 | variant to be chosen | device key and certificate | secure element present, connected via I2C | manufacturer (active); EAL 6+ certification applies to certain variants only and "up to OS level" |
| Clock | NXP PCF85063A | PCF85063ATL/1,118 | time for certificate validation | no built-in switch-over to a backup battery | manufacturer (active) |
| USB | USB-A socket | | update from a stick, service | physically accessible interface | no part number |
| Service ports | UART header, JTAG pads | | development, production | debug access populated | no part number |
| Indicators | status LEDs, reset button | | | | |

NXP's evaluation kit for this processor (8MMINILPD4-EVK) uses the same PMIC, 2 GB LPDDR4 and 16 GB
eMMC, so the combination is common. According to its block diagram the kit uses a Qualcomm AR8031
Ethernet PHY, not the KSZ9031.

## Variants and revisions

Chosen so that each way of handling an HBOM occurs once.

| Case | What it exercises |
|---|---|
| Family "Venue Controller" with the parts above | HBOM as baseline of a product family |
| Variant "Controller W": adds Wi-Fi/Bluetooth module Murata Type 1ZM (LBEE5QD1ZM, chipset NXP 88W8987) | delta document that adds a part; a radio interface changes the threat picture. Murata lists the module as "to be discontinued" |
| Variant "Controller Lite": without secure element | delta document that removes a part |
| Rev B: eMMC from Samsung (KLMAG1JETD-B041) instead of Micron because of a supply shortage | new hardware revision |
| Manufacturing partner supplies a partial HBOM for the power-supply module only | merging a partial document |
| Correction of a wrongly recorded part number | overwriting |

## Vulnerability records for hardware

The NVD has a hardware CPE for the processor (`cpe:2.3:h:nxp:i.mx_8m_mini:-:*:*:*:*:*:*:*`). Two CVEs
are matched to it: CVE-2022-45163 (information disclosure in Serial Download Protocol mode) and
CVE-2023-39902 (U-Boot SPL; the chip is listed as platform only, not as the vulnerable item). No CPE
was found for the PMIC, the Ethernet PHY, the secure element or the clock. Memory parts were not
searched.

## What an HBOM can and cannot say

An HBOM states which part is fitted. It does not state how the part is configured in the shipped
device. Ground truth for this board: the debug ports are populated, and in production units JTAG is
locked by fuses and the UART console is disabled. A threat analysis based on the HBOM alone can only
propose "debug port present"; whether it is exposed is a human decision.

## Planned files

- `hbom/venue-controller-rev-a.cdx.json`: baseline
- `hbom/venue-controller-w.delta.cdx.json`, `hbom/venue-controller-lite.delta.cdx.json`: variants
- `hbom/venue-controller-rev-b.cdx.json`: revision
