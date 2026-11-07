# ACwing Mech A1 – print and build pack

**Project:** ACwing · **Author:** Andrea Cirillo · **Overview:** [repository README](../../README.md)

![ACwing Mech A1 with tray T400](Renders/ACwing_Mech_A1_T400_drone_raytrace.png)

**Mech A1** is the first released mechanics of the 1S mini drone. It contains:
- the frame **A1 core**;
- three interchangeable **battery trays** (T400 / T800 / T1200);
- the printed **stack spacers**;
- the **TPU motor sleeves**;
- the translucent PLA **electronics cover** with the ACwing logo (indoor and GPS versions).

It fits, all boards **1.6 mm** thick (2026-11-06):
- **ESC 1S rev A** and **FC rev A** (connector layout 2026-11-02/03);
- **Flow rev A**;
- **GPS rev A** as an option (outdoor variant).

![Stack with the cover](Renders/ACwing_Mech_A1_stack_cover.png)

Baseline: indoor flight, no GPS.

## Contents

| Path | What |
|---|---|
| `Prints/` | **print-ready STL files**, already oriented and placed on the bed (z = 0). Written by the assembly macro. |
| `ACwing_Mech_A1_BoM.xlsx` / `.csv` | mechanical bill of materials per drone and per tray, masses, print settings (sheet `Print`) |
| `STEP/` | hardware, cables and battery of the assembly (one file per tray), written by the macro |
| `Renders/` | KiCad raytracer renders (same engine as the ACwing_HW board renders, one light, 2026-11-07): drone T400, stack with the indoor / GPS cover and without it. The older per-tray renders (`*_hero`, `*_top`, …) show the frame at RM 51 |
| `Checks/` | interference checks and vibration (FE) results |
| `ACwing_frame_A1_mechanical_handoff.md` | design notes: interfaces, checks, vibration, masses |

## Regenerating the print files

The source meshes live in `01 - Frame/` and `02 - Mounts/`. The macro
`03 - Assembly/ACwing_Mech_A1/ACwing_Mech_A1.FCMacro` rewrites `Prints/` every time it runs
(`EXPORT_PRINTS = True`). It also builds the assembly in FreeCAD. See [its README](../../03%20-%20Assembly/ACwing_Mech_A1/README.md).

## What to print

| # | File (`Prints/`) | Material | Per drone | Mass |
|---|---|---|---|---|
| 1 | `ACwing_Mech_A1_01_Frame_core_PETG.stl` | PETG | 1 | 15.1 g |
| 2 | `ACwing_Mech_A1_02_Tray_T400_PETG.stl` | PETG | 1 (400 mAh pack) | 3.4 g |
| 2 | `ACwing_Mech_A1_02_Tray_T800_PETG.stl` | PETG | 1 (800 mAh pack) | 3.7 g |
| 2 | `ACwing_Mech_A1_02_Tray_T1200_PETG.stl` | PETG | 1 (1200 mAh pack) | 4.2 g |
| 3 | `ACwing_Mech_A1_03_Stack_Spacers_S1x4_S2x4_PETG.stl` | PETG | 1 plate (4 × S1; the 4 × S2 only with GPS) | 0.4 g |
| 4 | `ACwing_Mech_A1_04_Motor_Sleeves_x4_TPU95A.stl` | TPU 95A | 1 plate (4 sleeves) | 2.2 g |
| 5 | `ACwing_Mech_A1_05_Cover_indoor_PLA.stl` | PLA translucent | 1 (indoor) | 2.8 g |
| 5 | `ACwing_Mech_A1_05_Cover_GPS_PLA.stl` | PLA translucent | 1 (GPS option, instead of the indoor one) | 3.8 g |

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

- **Core A1, upside down.** The tops of the propeller-guard rings sit on the bed and the deck is about 9 mm above it.
  - Tree supports go under the deck, the stack bosses and the motor holders.
  - Upside down there is about 10 % less overhang than upright, and the supports are 9 mm tall instead of 28 mm.
- **Trays, upright.** The two flow bosses sit on the bed.
  - Tree supports go under the flow plate (2.4 mm), under the rear ends of the rails and under the four outboard tabs.
  - This keeps the battery cavity free of supports, so the pack slides on clean surfaces.
- **Spacers and sleeves:** flat, no supports.
- **Cover, upright.** Open bottom on the bed, logo up. Tree supports from the bed under the roof (inside only), or a
  bridged roof with slow bridge settings. Natural (translucent) PLA, walls fully solid (3 perimeters of 0.4 mm).

### Before the first full print

1. Print a small coupon with a few Ø2.8 holes. Set one Hangtife M2 insert and tune the XY hole compensation of the slicer.
2. Check the tray fit on the core lugs: the four lug faces (z −9.0) and tab faces must sit flat against each other.

## Hardware (per drone)

The full list is in `ACwing_Mech_A1_BoM.xlsx`.

| Part | Qty | Note |
|---|---|---|
| Hot-melt insert M2 × 3 × Ø3.0 (Hangtife HLTI-M2-001) | 10 | 4 stack bosses, 4 tray lugs, 2 flow bosses (+ 2 per spare tray) |
| Silicone grommet (bumper) M2, H 6.0, OD 5.0, groove Ø3.0 × 1.6, bore Ø2.0 | 4 | FC soft mount, for 1.6 mm boards (Ø3.2 holes) |
| Stack screw M2 × 14 ISO 7380 (button head), titanium (recommended) or A4 | 4 | from the cover top; M2 × 25 with the GPS option |
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
4. **Stack.** Per corner: S1 spacer (2.8 mm), silicone grommet with the FC rev A in its groove. With the GPS option:
   S2 spacer (3.8 mm) and the GPS rev A on top.
5. **Cables.**
   - Cable A (ESC J1 → FC J2, both on the front edge, 20 mm, 1:1): plug ESC J1, rise right behind the plug under
     the front-left guard ring, out over the ring, into FC J2.
   - Cable C (FC J4 → Flow J1, 60 mm, wires twisted): back along the FC right edge, down through the deck slot behind
     the rear grommets, outside the tray rail and past the front tray tab, into Flow J1 (its connector edge faces +X).
6. **Cover.** Put the cover on (posts on the grommets, or on the GPS board) and drive the four M2 × 14 (GPS: M2 × 25)
   screws from the top into the boss inserts. Stop when the heads seat in the counterbores: do not crush the grommets.
7. **Flow rev A on the tray**, sensor side down, with 2 nylon screws.
8. **Tray on the core** with 4 × M2 × 5 screws from below. Plug cable C.
9. **Battery.** Slide the pack in from the rear until the latch clicks, then plug the JST-PH lead.
10. **Propellers.** The front pair is green.

## Configurations

| Tray | Pack | Drone mass* | T/W* | Flight time vs the preliminary draft + 400 mAh* | First frame mode (FE) |
|---|---|---|---|---|---|
| T400 | 400 mAh, 11.5 g | ≈ 71.3 g | 1.96 | × 0.73 | 121 Hz |
| T800 | 800 mAh, ≈ 22 g | ≈ 82.0 g | 1.71 | × 1.19 | (124 Hz, RM 51) |
| T1200 | 1200 mAh, ≈ 30 g | ≈ 90.5 g | 1.55 | × 1.54 | (103 Hz, RM 51) |

\* Indoor (no GPS), 1.6 mm boards, motors at RM 53, with the cover (2.8 g). Mass budget and lightening options:
`ACwing_Mech_A1_weight_study.md`.
- thrust ≈ 140 g;
- hover power ∝ m^1.5;
- tray hardware estimated at 1.2 g (BoM);
- reference is the preliminary draft (battery bay fused to the frame) with the 400 mAh pack, ≈ 58 g.

## Open points

- **2026-11-07: ESC 1S J1 on the front edge** → motors at RM 53, new cables A / C, flow board turned (handoff §10).
- **Board thickness: settled at 1.6 mm** for all boards (2026-11-06). Flow lens 10.7 mm above the ground with
  T400 / T1200, 9.7 mm with T800.
- **Weight.** The 1.6 mm boards and the cover add 8.6 g. The FE modes (§ handoff 5) were computed with the 1.0 mm stack:
  the heavier stack lowers them slightly; the tap test settles it.
- **ELRS receiver.** In the preliminary draft it sat on the battery-bay rail; its mount on A1 is not modelled yet.
- **Tap test.** Do it on the first build and set the gyro notch from it. The frame modes are 103–126 Hz, inside the band that matters for the FC soft mount.
