# ACwing Mech A – print and build pack

**Project:** ACwing · **Author:** Andrea Cirillo · **Overview:** [repository README](../../README.md)

![ACwing Mech A with tray T400](Renders/ACwing_Mech_A_T400_hero.png)

**Mech A** is the first released mechanics of the 1S mini drone. It contains:
- the frame **C3 core**;
- three interchangeable **battery trays** (T400 / T800 / T1200);
- the printed **stack spacers**;
- the **TPU motor sleeves**.

It fits:
- **ESC 1S rev A** and **FC rev A** (layout 2026-10-24);
- **Flow rev A**;
- **GPS rev A** as an option (outdoor variant).

Baseline: indoor flight, no GPS.

## Contents

| Path | What |
|---|---|
| `Prints/` | **print-ready STL files**, already oriented and placed on the bed (z = 0). Written by the assembly macro. |
| `ACwing_Mech_A_BoM.xlsx` / `.csv` | mechanical bill of materials per drone and per tray, masses, print settings (sheet `Print`) |
| `STEP/` | hardware, cables and battery of the assembly (one file per tray), written by the macro |
| `Renders/` | assembly renders per tray |
| `Checks/` | interference checks and vibration (FE) results |
| `ACwing_frame_C3_mechanical_handoff.md` | design notes: interfaces, checks, vibration, masses |

## Regenerating the print files

The source meshes live in `01 - Frame/` and `02 - Mounts/`. The macro
`04 - Assembly/ACwing_Mech_A/ACwing_Mech_A.FCMacro` rewrites `Prints/` every time it runs
(`EXPORT_PRINTS = True`). It also builds the assembly in FreeCAD. See [its README](../../04%20-%20Assembly/ACwing_Mech_A/README.md).

## What to print

| # | File (`Prints/`) | Material | Per drone | Mass |
|---|---|---|---|---|
| 1 | `ACwing_Mech_A_01_Frame_C3_core_PETG.stl` | PETG | 1 | 15.4 g |
| 2 | `ACwing_Mech_A_02_Tray_C3_T400_PETG.stl` | PETG | 1 (400 mAh pack) | 3.4 g |
| 2 | `ACwing_Mech_A_02_Tray_C3_T800_PETG.stl` | PETG | 1 (800 mAh pack) | 3.7 g |
| 2 | `ACwing_Mech_A_02_Tray_C3_T1200_PETG.stl` | PETG | 1 (1200 mAh pack) | 4.2 g |
| 3 | `ACwing_Mech_A_03_Stack_Spacers_S1x4_S2x4_PETG.stl` | PETG | 1 plate (4 × S1; the 4 × S2 only with GPS) | 0.4 g |
| 4 | `ACwing_Mech_A_04_Motor_Sleeves_x4_TPU95A.stl` | TPU 95A | 1 plate (4 sleeves) | 2.2 g |

Masses are for solid parts (mesh volume × density); the printed mass depends on walls and infill.

### Print settings (0.4 mm nozzle)

| | Core and trays (PETG) | Spacers (PETG) | Sleeves (TPU 95A) |
|---|---|---|---|
| Line width | 0.42–0.45 mm, Arachne walls | 0.42 mm | 0.45 mm |
| Layer | 0.12–0.16 mm | 0.12 mm | 0.16 mm |
| Perimeters | 3 | solid | 3 |
| Infill | 30–40 % gyroid | 100 % | 20 % |
| Bed | 3–5 mm brim on the core (only the ring tops touch the bed) | – | – |

The 0.2 mm nozzle gives no gain at these wall thicknesses (rails 1.2 mm, arms Ø2.2 mm). With PETG its lines also bond less well between layers.

### Orientation and supports

The files are exported in the orientation below. It comes from an overhang analysis of the meshes, so check the supports in your slicer.

- **Core C3, upside down.** The tops of the propeller-guard rings sit on the bed and the deck is about 9 mm above it.
  - Tree supports go under the deck, the stack bosses and the motor holders.
  - Upside down there is about 10 % less overhang than upright, and the supports are 9 mm tall instead of 28 mm.
- **Trays, upright.** The two flow bosses sit on the bed.
  - Tree supports go under the flow plate (2.4 mm), under the rear ends of the rails and under the four outboard tabs.
  - This keeps the battery cavity free of supports, so the pack slides on clean surfaces.
- **Spacers and sleeves:** flat, no supports.

### Before the first full print

1. Print a small coupon with a few Ø2.8 holes. Set one Hangtife M2 insert and tune the XY hole compensation of the slicer.
2. Check the tray fit on the core lugs: the four lug faces (z −9.0) and tab faces must sit flat against each other.

## Hardware (per drone)

The full list is in `ACwing_Mech_A_BoM.xlsx`.

| Part | Qty | Note |
|---|---|---|
| Hot-melt insert M2 × 3 × Ø3.0 (Hangtife HLTI-M2-001) | 10 | 4 stack bosses, 4 tray lugs, 2 flow bosses (+ 2 per spare tray) |
| Damping ball M2, H 6, OD 4.9, slot Ø3.03 × 1.14 | 4 | FC soft mount |
| Stack screw M2 × 12, titanium or A4 | 4 | M2 × 16 with the GPS option |
| Washer M2 Ø5 × 0.3, A4 | 4 | not with the GPS option |
| Tray screw M2 × 5, A4 or titanium | 4 | from below into the lug inserts |
| Flow board screw M2 × 4, nylon | 2 | from the sensor side |

Do not use plain steel or A2 / 304 screws near the compasses: ferromagnetic.

## Build order

1. **Inserts.** Set the 10 inserts with a soldering iron at 220–240 °C, flush with the face:
   - 4 in the stack bosses (from the top);
   - 4 in the tray lugs (from below);
   - 2 in the tray flow bosses.
2. **Motors.** Push the TPU sleeves on the motors and snap them into the holders (2 CW + 2 CCW).
   - Lead the M2 / M3 motor wires out on the side shown in the renders, then through the deck slots.
3. **ESC 1S rev A** on the bosses.
4. **Stack.** Per corner: S1 spacer, damping ball with the FC rev A in its slot, washer, M2 × 12 screw. Do not crush the balls.
5. **Cables.**
   - Cable A (ESC J1 → FC J2) in the rear corridor.
   - Cable C (FC J4 → Flow J1) down through the Qwiic slot, outboard of the M2 knee brace and under it, then outside the tray rail.
6. **Flow rev A on the tray**, sensor side down, with 2 nylon screws.
7. **Tray on the core** with 4 × M2 × 5 screws from below. Plug cable C.
8. **Battery.** Slide the pack in from the rear until the latch clicks, then plug the JST-PH lead.
9. **Propellers.** The front pair is green.

## Configurations

| Tray | Pack | Drone mass* | T/W* | Flight time vs C2 + 400 mAh* | First frame mode (FE) |
|---|---|---|---|---|---|
| T400 | 400 mAh, 11.5 g | ≈ 62.5 g | 2.24 | × 0.90 | 126 Hz |
| T800 | 800 mAh, ≈ 22 g | ≈ 73.3 g | 1.91 | × 1.41 | 124 Hz |
| T1200 | 1200 mAh, ≈ 30 g | ≈ 81.8 g | 1.71 | × 1.79 | 103 Hz |

\* Indoor (no GPS):
- thrust ≈ 140 g;
- hover power ∝ m^1.5;
- tray hardware estimated at 1.2 g (BoM);
- reference is C2 with the 400 mAh pack, ≈ 58 g.

## Open points

- **Flow rev A board thickness.** The STEP in ACwing_HW has a 1.6 mm PCB; the mechanical handoff says 1.0 mm.
  - The tray works with both.
  - With 1.6 mm the lens sits 0.6 mm lower: 10.7 mm above the ground with T400 / T1200, 9.7 mm with T800.
  - The cable C end in the model is drawn for 1.0 mm.
- **ELRS receiver.** In C2 it sat on the battery-bay rail; its mount on C3 is not modelled yet.
- **Tap test.** Do it on the first build and set the gyro notch from it. The frame modes are 103–126 Hz, inside the band that matters for the FC soft mount.
