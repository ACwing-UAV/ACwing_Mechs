# Mech A1 – STEP

All files in frame coordinates (z = 0 propeller plane, +Y forward, +X right), mm. Updated 2026-11-13 evening (1.0 mm boards,
frame A1 **rev R**, flat-roof cover, flow board cover with M2 × 6 nylon flow screws).

## Assembly hardware and cables

`ACwing_Mech_A1_<tray>_<indoor|gps>_hardware_cables.step`: battery, stack hardware (inserts, spacers S1 / S2, M2
damping balls, M2 ISO 7380 stack screws), tray and flow screws and inserts, plug housings, the JST-PH pair and every
wire of cables A, B (GPS only), C and D, as B-rep solids with names and colours. Written with OpenCASCADE from the
assembly data (`03 - Assembly/ACwing_Mech_A1/ACwing_Mech_A1_data.json`); the FreeCAD macro writes the same content.

## Printed parts

`Parts/ACwing_<part>.step`: frame A1 core, trays T400 / T800 / T1200, electronics cover (indoor, GPS), flow board cover, in assembly
position. These are **faceted solids** made from the source meshes (decimated, one planar face per triangle), for
interference checks and for fitting in other CAD tools:

| File | Facets | Max deviation from the source mesh |
|---|---|---|
| `ACwing_Frame_A1_core.step` (rev R; 87 MB) | 80 000 | 0.26 mm (p99 0.17); volume 0.2 % under the source |
| `ACwing_Flow_Cover_A1.step` (T400 / T1200 position; 1.0 mm lower on T800) | 6 000 | 0.06 mm (p99 0.04) |
| `ACwing_Tray_A1_T400/T800/T1200.step` | 12 000 | 0.24 mm (p99 0.09) |
| `ACwing_Cover_A1_indoor.step` (without the engraved logo) | 30 000 | 0.12 mm (p99 0.08) |
| `ACwing_Cover_A1_gps.step` (without the engraved logo) | 36 000 | 0.14 mm (p99 0.09) |

The source meshes (`01 - Frame/`, `02 - Mounts/`) stay the reference for printing. The parts come from mesh and
signed-distance models, so there is no feature-based native model: the native CAD of Mech A1 is the FreeCAD assembly
macro with its data file (`03 - Assembly/ACwing_Mech_A1/`), which builds the full assembly from these parts and the
ACwing_HW board STEP models.
