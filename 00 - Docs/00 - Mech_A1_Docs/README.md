# ACwing Mech A1 – print and build pack

**Project:** ACwing · **Author:** Andrea Cirillo · **Overview:** [repository README](../../README.md)

![ACwing Mech A1 with tray T400](Renders/ACwing_Mech_A1_T400_drone_raytrace.png)

**Mech A1** is the first released mechanics of the 1S mini drone. It contains:
- the frame **A1 core**;
- three interchangeable **battery trays** (T400 / T800 / T1200);
- the printed **stack spacers**;
- the **TPU motor sleeves**;
- the translucent PLA **electronics cover** with the ACwing logo (indoor and GPS versions).

Since 2026-11-12 the core is **print-first**: wave propeller guards that print upside down with no support inside
the guards and spokes, wire holes in the arms, and a flat-roof cover that prints roof-down without supports
(handoff §12).

It fits, all boards **1.0 mm** thick (ACwing_HW handoff §0.19–§0.20, 2026-11-08):
- **ESC 1S rev A** and **FC rev A** (layout of 2026-11-08: ESC J1 and FC J2 on the front edge at u −10.5, both USB-C at
  the rear-right chamfer);
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
| `Renders/` | path-traced renders (Blender Cycles, one light, boards from the ACwing_HW KiCad models with silkscreen, 2026-11-13): drone T400 (3/4 and side), stack with the indoor / GPS cover and without it, front-left guard with cable A, motor holder with the foot ring and the wire channel (bare core). The older per-tray renders (`*_hero`, `*_3D_overview`, `*_cables`) show the earlier frame and cable routes |
| `Checks/` | interference checks and vibration (FE) results |
| `ACwing_frame_A1_mechanical_handoff.md` | design notes: interfaces, checks, vibration, masses |

## Regenerating the print files

The source meshes live in `01 - Frame/` and `02 - Mounts/`. The macro
`03 - Assembly/ACwing_Mech_A1/ACwing_Mech_A1.FCMacro` rewrites `Prints/` every time it runs
(`EXPORT_PRINTS = True`). It also builds the assembly in FreeCAD. See [its README](../../03%20-%20Assembly/ACwing_Mech_A1/README.md).

## What to print

| # | File (`Prints/`) | Material | Per drone | Mass |
|---|---|---|---|---|
| 1 | `ACwing_Mech_A1_01_Frame_core_PETG.stl` | PETG | 1 | 16.7 g |
| 2 | `ACwing_Mech_A1_02_Tray_T400_PETG.stl` | PETG | 1 (400 mAh pack) | 3.3 g |
| 2 | `ACwing_Mech_A1_02_Tray_T800_PETG.stl` | PETG | 1 (800 mAh pack) | 3.5 g |
| 2 | `ACwing_Mech_A1_02_Tray_T1200_PETG.stl` | PETG | 1 (1200 mAh pack) | 4.0 g |
| 3 | `ACwing_Mech_A1_03_Stack_Spacers_S1x4_S2x4_PETG.stl` | PETG | 1 plate (4 × S1; the 4 × S2 only with GPS) | 0.4 g |
| 4 | `ACwing_Mech_A1_04_Motor_Sleeves_x4_TPU95A.stl` | TPU 95A | 1 plate (4 sleeves) | 2.2 g |
| 5 | `ACwing_Mech_A1_05_Cover_indoor_PLA.stl` | PLA translucent | 1 (indoor) | 2.8 g |
| 5 | `ACwing_Mech_A1_05_Cover_GPS_PLA.stl` | PLA translucent | 1 (GPS option, instead of the indoor one) | 4.3 g |

Masses are for solid parts (mesh volume × density); the printed mass depends on walls and infill. The first print
of the 2026-11-08 core (15.55 g solid) weighed 13 g, so expect about 15 g for this core.

### Print settings (Bambu Lab A1, 0.4 mm nozzle)

| | Core and trays (PETG) | Spacers (PETG) | Sleeves (TPU 95A) |
|---|---|---|---|
| Line width | 0.42–0.45 mm, Arachne walls | 0.42 mm | 0.45 mm |
| Layer | 0.12–0.16 mm | 0.12 mm | 0.16 mm |
| Perimeters | 3 | solid | 3 |
| Infill | 30–40 % gyroid | 100 % | 20 % |
| Material | **PETG Basic or PETG HF** (not PETG Matte: weaker layer bonding, the 2026-11-08 guards broke) | PETG | TPU 95A |
| Bridges | 100 % fan, thick bridges on: the window sills are 6.2 mm bridges, the spokes 18.6 mm | – | – |
| Bed | textured PEI; 3–5 mm brim on the core (only the guard top lips touch the bed) | – | – |

The 0.2 mm nozzle gives no gain at these wall thicknesses (guard wall 0.86 mm = 2 lines, rails 1.2 mm, arms Ø2.2 mm).
With PETG its lines also bond less well between layers. The print sheet of the BoM (`Print`) has the full settings.

### Orientation and supports

The files are exported in the orientation below. It comes from an overhang analysis of the meshes, so check the supports in your slicer.

- **Core A1, upside down.** The top lips of the four guards sit on the bed and the deck is about 9 mm above it.
  - Tree (organic) supports, on the build plate only, threshold 40°: they grow under the deck, the stack bosses,
    the motor holders and the arms (about 21 cm³ of support envelope).
  - **No support in the guards and spokes**: every window sill is a 45° slope or a short bridge, the bulge leans at
    most 32° from vertical, the spokes are straight bridges. If the slicer adds any there, block it with a support
    blocker: removing supports broke the guards of the 2026-11-08 print.
- **Trays, upright.** The two flow bosses sit on the bed.
  - Tree supports go under the flow plate (2.4 mm), under the rear ends of the rails and under the four outboard tabs.
  - This keeps the battery cavity free of supports, so the pack slides on clean surfaces.
- **Spacers and sleeves:** flat, no supports.
- **Cover, roof down.** The flat roof sits on the bed (engraved logo on the bed side), the 45° chamfer and the walls
  rise without supports. Natural (translucent) PLA, walls fully solid (2 perimeters of 0.4 mm).

### Before the first full print

1. Print a small coupon with a few Ø2.8 holes. Set one Hangtife M2 insert and tune the XY hole compensation of the slicer.
2. Check the tray fit on the core lugs: the four lug faces (z −9.0) and tab faces must sit flat against each other.

## Hardware (per drone)

The full list is in `ACwing_Mech_A1_BoM.xlsx`.

| Part | Qty | Note |
|---|---|---|
| Hot-melt insert M2 × 3 × Ø3.0 (Hangtife HLTI-M2-001) | 10 | 4 stack bosses, 4 tray lugs, 2 flow bosses (+ 2 per spare tray) |
| Damping ball M2 (QUARKZMAN), H 6.0, OD 4.9, slot Ø3.03 × 1.14, bore Ø2.0 | 4 | FC soft mount, for 1.0 mm boards (Ø3.2 holes) |
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
   - The motors have no connector. Before soldering, thread the two leads: out of the **floor hole** of the holder,
     into the recess inside the foot ring, through the tunnel into the **channel of the rib** under the arm, out of
     its teardrop hole, then **woven through the 3 holes** of the arm blade and up through the deck slot to the ESC
     pads (handoff §13).
3. **ESC 1S rev A** on the bosses.
4. **Stack.** Per corner: S1 spacer (2.57 mm), damping ball with the FC rev A in its slot. With the GPS option:
   S2 spacer (3.57 mm) and the GPS rev A on top.
5. **Cables.**
   - Cable A (ESC J1 → FC J2, both at u −10.5 on the front edge, 10 mm, 1:1): plug ESC J1, bend the wires up right
     behind the plug (the guard is open toward the body), into FC J2 from the front. Keep the loop tight: 1.4 mm to the
     propeller disc.
   - Cable C (FC J4 → Flow J1, 60 mm, wires twisted): back along the FC right edge, down through the deck slot behind
     the rear grommets, outside the tray rail and past the front tray tab, into Flow J1 (its connector edge faces +X).
6. **Cover.** Put the cover on (posts on the damping balls, or on the GPS board) and drive the four M2 × 14 (GPS: M2 × 25)
   screws from the top into the boss inserts. Stop when the heads seat in the counterbores: do not crush the balls.
7. **Flow rev A on the tray**, sensor side down, with 2 nylon screws.
8. **Tray on the core** with 4 × M2 × 5 screws from below. Plug cable C.
9. **Battery.** Slide the pack in from the rear until the latch clicks (keep the pigtail aside), then plug the JST-PH lead.
10. **Propellers.** The front pair is green.

## Configurations

| Tray | Pack | Drone mass* | T/W* | Flight time vs the preliminary draft + 400 mAh* | First frame mode (FE) |
|---|---|---|---|---|---|
| T400 | 400 mAh, 11.5 g | ≈ 68.3 g | 2.05 | × 0.78 | 91.7 Hz |
| T800 | 800 mAh, ≈ 22 g | ≈ 79.1 g | 1.77 | × 1.26 | 84.9 Hz |
| T1200 | 1200 mAh, ≈ 30 g | ≈ 87.5 g | 1.60 | × 1.62 | 90.3 Hz |

\* Indoor (no GPS), 1.0 mm boards, with the cover (2.8 g), 2026-11-13. FE model of 2026-11-08 (handoff §5): the
A2 core of 2026-11-08 gives 98.8 Hz in the same model. Mass budget and lightening options:
`ACwing_Mech_A1_weight_study.md`.
- thrust ≈ 140 g;
- hover power ∝ m^1.5;
- tray hardware estimated at 1.2 g (BoM);
- reference is the preliminary draft (battery bay fused to the frame) with the 400 mAh pack, ≈ 58 g.

## Open points

- **2026-11-08: boards back to 1.0 mm, ESC J1 at u −10.5** → new **A2 guard rings** (top ring open toward the body,
  ramps down to the bottom ring), motors at **RM 52**, cable A 10 mm, new cover (handoff §11).
- **2026-11-12: first print of the A2 core** (PETG Matte, upside down) failed: the guard top rings broke while the
  supports were removed. → **print-first redesign**: wave guards with no support inside, straight spokes, closed wire
  eyelets for the connector-less motors, flat-roof cover (handoff §12).
- **2026-11-13: review in the slicer** → one-piece motor holders (the collar was a separate body), L1 foot ring and
  a closed wire channel instead of the landing loop (frame 28.0 mm tall), spokes flush with the rims and in line with
  the bridges, wire holes in the arms, arm roots cleaned up (handoff §13).
- **Tap test.** Do it on the first build and set the gyro notch from it. The first frame modes are 85–92 Hz in the
  2026-11-08 model, inside the band that matters for the FC soft mount.
- **ELRS receiver.** In the preliminary draft it sat on the battery-bay rail; its mount on A1 is not modelled yet
  (FC J5 plug envelope checked).
- **Core mesh.** The core is made by mesh booleans from the 2026-11-07 core (guards and spokes replaced); the old
  bottom bridges stay merged with the new ones (≈ 0.1 g that a regenerated core could save).
