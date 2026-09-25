# BMS-EV

Controllers that let a **complete EV battery pack** be reused as home energy storage — keeping the manufacturer's own battery management system in place instead of replacing it.

---

## Why keep the original BMS

A traction pack from an electric car has already passed **UN ECE R100** before the vehicle could be sold: mechanical shock at 28 g, open flame for 130 seconds, water immersion for an hour, a vibration profile equivalent to 200 000 km, and full thermal-propagation testing since 2022.

A typical home battery certified to IEC 62619 goes through none of those.

The factory BMS monitors every cell, controls the contactors, and was developed as part of that safety case. Most failures in DIY second-life builds come from what gets *added* around the pack — not from the pack itself. So the controller translates between the vehicle's BMS and a hybrid inverter, rather than taking over its protective role.

Written up in [pv magazine Deutschland](https://www.pv-magazine.de/2026/07/17/warum-gebrauchte-elektroauto-batterien-sicherer-sein-koennen-als-manche-kommerzielle-heimspeicher-wenn-die-steuerung-stimmt/) (July 2026).

---

## Repositories

| Repository | What's in it |
|---|---|
| **[bms-ev-docs](https://github.com/BMS-EV/bms-ev-docs)** | Compatibility dataset — 70 battery/BMS profiles × 56 hybrid inverters = 3 768 documented pairings, each with verification status and source. CSV + JSON. |
| **[supported-batteries](https://github.com/BMS-EV/supported-batteries)** | Battery profile list: Tesla, BMW, Nissan, VW MEB, Hyundai/Kia E-GMP, Renault, Stellantis, MG, BYD and others. |
| **[supported-inverters](https://github.com/BMS-EV/supported-inverters)** | Hybrid inverters with DC voltage windows and battery protocols: Deye, SOFAR, GoodWe, SolaX, SMA, Fronius, Sungrow, Solis and more. |
| **[bms-ev-home-assistant](https://github.com/BMS-EV/bms-ev-home-assistant)** | Home Assistant integration over MQTT auto-discovery. HACS compatible. |
| **[bms-ev-mqtt-examples](https://github.com/BMS-EV/bms-ev-mqtt-examples)** | MQTT topic reference, Node-RED flows, Grafana dashboards, Python subscriber. |

---

## On the data

The compatibility dataset states how each pairing was verified, because "supported" on its own does not tell you much:

| Level | What it means | Count |
|---|---|---|
| `field_verified` | Observed in a running installation | 2 |
| `protocol_verified` | Both protocols documented and implemented, firmware bench-tested against them | 2 265 |
| `engineering_validated` | Translation implemented and reviewed, not bench-tested as a pair | 1 501 |

**3 768 pairings are combinations we ship firmware for — not 3 768 tested installations.** Only two carry field evidence, and the dataset says so.

Figures that could not be sourced are marked `NEEDS VERIFICATION` rather than estimated. When a published number turned out to be wrong, the correction is recorded in the repository history — including why it was wrong.

---

## Built on Battery-Emulator

The firmware builds on [dalathegreat/Battery-Emulator](https://github.com/dalathegreat/Battery-Emulator), an open-source project for talking to EV battery packs over CAN. Credit where it is due — that project made this practical.

---

📖 **[docs.bms-ev.com](https://docs.bms-ev.com/)** · 🛒 [bms-ev.com](https://bms-ev.com/) · ✉️ office@bms-ev.com
