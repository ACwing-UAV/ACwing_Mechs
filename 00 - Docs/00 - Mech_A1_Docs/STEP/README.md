# Mech A1 – STEP

All files in frame coordinates (z = 0 propeller plane, +Y forward, +X right), mm.

## Assembly hardware and cables

`ACwing_Mech_A1_<tray>_<indoor|gps>_hardware_cables.step`, written by the assembly macro: battery, stack hardware
(inserts, spacers, silicone grommets, M2 ISO 7380 stack screws), tray and flow screws, plug housings and every wire of
cables A, B (GPS only), C and D. Boards: 1.6 mm rev A stack, ESC J1 on the front edge, frame at RM 53, flow board turned (2026-11-07).

## Printed parts

`Parts/ACwing_<part>.step`: frame A1 core, trays T400 / T800 / T1200, electronics cover (indoor, GPS), in assembly
position. These are **faceted solids** made from the source meshes (decimated, then sewn and closed in FreeCAD), for
interference checks and for fitting in other CAD tools:

| File | Facets | Max deviation from the source mesh |
|---|---|---|
| `ACwing_Frame_A1_core.step` (RM 53, 2026-11-07) | 37 500 | 0.16 mm (p99 0.07) |
| `ACwing_Tray_A1_T400/T800/T1200.step` | 12 000 | 0.14 mm (p99 0.05) |
| `ACwing_Cover_A1_indoor.step` (0.8 mm walls) | 24 000 | 0.08 mm (p99 0.04) |
| `ACwing_Cover_A1_gps.step` (0.8 mm walls) | 16 000 | 0.19 mm (p99 0.08) |

The source meshes (`01 - Frame/`, `02 - Mounts/`) stay the reference for printing. The parts are generated from
signed-distance models, so there is no feature-based native model: the native CAD of Mech A1 is the FreeCAD assembly
macro with its data file (`03 - Assembly/ACwing_Mech_A1/`), which builds the full assembly from these parts and the
ACwing_HW board STEP models.
