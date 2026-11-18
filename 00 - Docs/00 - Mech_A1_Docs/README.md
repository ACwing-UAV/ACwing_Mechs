# ACwing Mech A1 – print and build pack

**Project:** ACwing · **Author:** Andrea Cirillo · **Overview:** [repository README](../../README.md)

![ACwing Mech A1 with tray T400](Renders/ACwing_Mech_A1_T400_drone_raytrace.png)

**Mech A1** is the first released mechanics of the 1S mini drone. Since **rev M (2026-11-15)** it contains:
- the **modular frame A1**: a central **body**, four **guard baskets** and four **motor cups** (9 parts, all printed
  without supports);
- three interchangeable **battery + flow trays** (T400 / T800 / T1200), each carrying the pack and housing the flow board;
- the printed **stack spacers** (S0 / S1 / S2);
- the **TPU motor sleeves**;
- the translucent PLA **electronics cover** with the ACwing logo (indoor and GPS versions).

Rev M replaces the one-piece rev R core, which needed about 26 cm³ of support. The electronics stack sits 4.5 mm higher
than in rev R so that the ESC USB-C (charging port) stays free (handoff §15).

It fits, all boards **1.0 mm** thick (ACwing_HW handoff §0.19–§0.20, 2026-11-08):
- **ESC 1S rev A** and **FC rev A** (ESC J1 and FC J2 on the front edge at u −10.5, both USB-C at the rear-right chamfer);
- **Flow rev A** (in the tray pocket);
- **GPS rev A** as an option (outdoor variant).

![ESC USB-C free](Renders/ACwing_Mech_A1M_ESC_USB_free.png)

Baseline: indoor flight, no GPS.

## Contents

| Path | What |
|---|---|
| `../../01 - Frame/Frame_A1/ACwing_Mech_A1M.3mf` | **Bambu Studio project** (A1, PETG Matte): frame set and trays on 4 plates with the print settings below |
| `../../01 - Frame/Frame_A1/ACwing_Mech_A1M_print_test.3mf` | **print test** with the same settings, one plate (≈ 51 min, 5.5 g); print it before the frame, see "Before the first full print". `Prints/Print_test/`: its 6 STL files |
| `Prints/` | **print-ready STL files**, already oriented and placed on the bed (z = 0). Written by the assembly macro (the whole-set plate file by the design scripts). |
| `ACwing_Mech_A1_BoM.xlsx` / `.csv` | mechanical bill of materials per drone and per tray, masses, print settings (sheet `Print`) |
| `STEP/` | hardware, cables and battery of the assembly (one file per tray); `Parts/`: faceted STEP of the printed parts |
| `Renders/` | path-traced renders (Blender Cycles, one light, boards from the ACwing_HW KiCad models with silkscreen). Rev M (2026-11-15): drone T400 and T1200 (3/4), side, ESC USB-C side, pod with rods and strut, pod from below, underside with the tray (T400, T1200), guard ear with the lead drop and cable A, stack with the indoor / GPS cover and without it, concept sheet. Files named `A1R_*`, `*_flow_cover*`, `*_holder_foot*` and the per-tray `*_hero`, `*_3D_overview`, `*_cables` show earlier frames |
| `Checks/` | interference checks, vibration (FE) and print-study results |
| `ACwing_frame_A1_mechanical_handoff.md` | design notes: interfaces, checks, vibration, masses (§15 = rev M) |

## Regenerating the print files

The source meshes live in `01 - Frame/` and `02 - Mounts/`. The macro
`03 - Assembly/ACwing_Mech_A1/ACwing_Mech_A1.FCMacro` rewrites `Prints/` every time it runs
(`EXPORT_PRINTS = True`). It also builds the assembly in FreeCAD. See [its README](../../03%20-%20Assembly/ACwing_Mech_A1/README.md).

## What to print

| # | File (`Prints/`) | Material | Per drone | Mass |
|---|---|---|---|---|
| 1 | `ACwing_Mech_A1_01_Frame_set_plate_256x256_PETG.stl` | PETG | the whole frame on one 256 × 256 plate (or print 1a–1c separately) | 19.0 g |
| 1a | `ACwing_Mech_A1_01a_Frame_body_PETG.stl` | PETG | 1 | 5.2 g |
| 1b | `ACwing_Mech_A1_01b_Frame_basket_<FL\|FR\|RL\|RR>_PETG.stl` | PETG | 1 of each | 1.92 g each |
| 1c | `ACwing_Mech_A1_01c_Frame_cup_<FL\|FR\|RL\|RR>_PETG.stl` | PETG | 1 of each | 1.55 g each |
| 2 | `ACwing_Mech_A1_02_Tray_T400_PETG.stl` | PETG (black or grey) | 1 (400 mAh pack) | 3.4 g |
| 2 | `ACwing_Mech_A1_02_Tray_T800_PETG.stl` | PETG (black or grey) | 1 (800 mAh pack) | 3.8 g |
| 2 | `ACwing_Mech_A1_02_Tray_T1200_PETG.stl` | PETG (black or grey) | 1 (1200 mAh pack) | 4.4 g |
| 3 | `ACwing_Mech_A1_03_Stack_Spacers_S0x4_S1x4_S2x4_PETG.stl` | PETG | 1 plate (4 × S0, 4 × S1; the 4 × S2 only with GPS) | 0.6 g |
| 4 | `ACwing_Mech_A1_04_Motor_Sleeves_x4_TPU95A.stl` | TPU 95A | 1 plate (4 sleeves) | 2.2 g |
| 5 | `ACwing_Mech_A1_05_Cover_indoor_PLA.stl` | PLA translucent | 1 (indoor) | 2.9 g |
| 5 | `ACwing_Mech_A1_05_Cover_GPS_PLA.stl` | PLA translucent | 1 (GPS option, instead of the indoor one) | 4.5 g |

The baskets and cups come in four versions (FL, FR, RL, RR): the lead rod and the cup strut are mirrored. Masses are for
solid parts (mesh volume × density); the printed mass depends on walls and infill. The flow board cover of rev R is
no longer used (the tray pocket replaces it).

### Print settings (Bambu Lab A1, 0.4 mm nozzle, Bambu PETG Matte)

**Bambu Studio project:** `01 - Frame/Frame_A1/ACwing_Mech_A1M.3mf` (2026-11-16) has 4 plates with these settings:
- plate 1: the frame set;
- plate 2: tray T400 and the spacers;
- plate 3: tray T800;
- plate 4: tray T1200.

Open it and keep the project settings.

| | Value | Why |
|---|---|---|
| Process | 0.12 mm Fine @BBL A1, 3 walls, 25 % infill (cups and spacers 100 %), supports **off** | the parts are designed without supports |
| Fan | min 40 %, max 90 % (layers under 30 s), **100 % on overhangs and bridges** | PETG at 30–50 % sags on bridges and droops on overhangs |
| Layer cooling | slow down below 12 s per layer, down to 10 mm/s | the rods and claw legs have tiny layers |
| Bridges | flow 0.85, 20 mm/s, thick bridges on | tighter, less sag |
| Overhangs | 50 / 30 / 15 / 10 mm/s (10–25 / 25–50 / 50–75 / 75–100 %) | |
| Walls | outer 60 mm/s, inner 100 mm/s | |
| Stringing | 235 °C, retraction 0.8 mm at 40 mm/s, wipe, spiral Z-hop 0.4 mm, avoid crossing walls, seam at the back away from overhangs | |
| First layer | 0.20 mm high, 0.5 mm lines, 30 mm/s walls / 40 mm/s infill, nozzle 245 °C, textured PEI plate 75 °C, fan off for 3 layers | 0.12 mm × 0.3 mm lines did not fill the texture and stuck poorly (2026-11-16) |
| Brim | 3 mm outer brim on the baskets, the cups and the spacers | baskets touch the bed with the guard top only; cups and spacers are small |

Wash the plate with warm water and dish soap before printing (no fingers on it afterwards). Dry the PETG (65 °C, 6–8 h) before printing: wet PETG strings and blobs whatever the settings. PETG Basic / HF bond
better between layers than PETG Matte; with Matte, go to 240 °C if the rods break when removing the parts.

### Orientation (no supports)

The files are exported in the orientation below; the overhang analysis of the meshes finds no area that needs support
(`Checks/ACwing_Mech_A1_print_study.json`, entry `M_2026-11-15`). Check the preview in your slicer and keep supports off.

- **Body: deck on the bed.** Everything grows upward from the flat deck.
- **Baskets: upside down,** guard top on the bed. The ears print on their 45° shoulders, the rods as 45° columns, the claw
  legs straight up.
- **Cups: upright,** foot flange on the bed. A 45° cone under the floor; the strut rises at 45°, its foot has a 45°
  underside and the locating pin on top.
- **Trays: upside down,** wall tops, lugs and posts on the bed. The box floor (2.4 mm strips) and the pocket floor with
  the sensor windows print as bridges. Black or grey PETG (no stray light on the flow sensors).
- **Spacers and sleeves:** flat, no supports.
- **Cover, roof down.** Natural (translucent) PLA, walls fully solid.

### Before the first full print

Print `01 - Frame/Frame_A1/ACwing_Mech_A1M_print_test.3mf` (2026-11-16): 6 small parts with the critical features of the
frame, sliced with the same settings as the frame project (Bambu Studio CLI: no warnings, ≈ 51 min, 5.5 g of PETG Matte).
Render: `Renders/ACwing_Mech_A1M_print_test.png`.

| # | Part | What it checks | Good result | If not |
|---|---|---|---|---|
| 1 | First layer 30 × 30 × 0.44 | adhesion and Z offset on the textured PEI plate | lines fused, no gaps, flat corners; measures 30.0 ± 0.15 mm | gaps or round lines: run the bed levelling, wash the plate; ridges: nozzle too low |
| 2 | Bridges 6 / 10 / 15 / 20 mm, 1.2 mm thick | bridges of the nut pockets, insert seats, tray floor windows | 6 and 10 mm flat underneath; 15 mm sag ≤ 0.5 mm | more cooling on bridges, bridge flow 0.80, nozzle 230 °C |
| 3 | Overhangs 30 / 45 / 55 / 65° from vertical, 6 mm tall | rods, claw legs, cup flanges (45° and less) | 30° and 45° clean; 55° slightly rough; 65° shows the limit | slower overhang speeds, check the PETG is dry |
| 4 | Rods at 45° (Ø2.4 solid, Ø3.2 with Ø1.9 bore), Ø2.4 pin 12 mm, 0.8 mm wall | basket rods and the lead bore; stringing; layer bond | rods round, bore open over the whole length (a motor lead passes), few strings between the rods and the pin; the wall tears with a rough break when bent | stringing: dry the PETG, retraction 1.0 mm; clean break along a layer: nozzle 240–245 °C |
| 5 | Joint pad: 2.4 mm ear pad with Ø2.2 hole and the M2 nut hex pocket (AF 4.25 × 0.9) on the bed face; 4.0 mm boss with the blind Ø2.8 × 3.4 insert seat | body pads (ear nuts, tray inserts) | the nut presses in by hand and does not turn; an M2 screw passes freely; the insert sets flush at 220–240 °C without breaking the 0.6 mm roof | tight hole or nut: X-Y hole compensation +0.05 mm; loose insert: −0.05 mm |
| 6 | Ear tab 1.2 mm with Ø2.2 hole, 0.8 mm wall to the edge | basket ear | screw tab 6 onto pad 5 with an M2 × 6 and the nut: the wall does not crack | more walls on the ears (4), or 245 °C for the bond |

Then print one basket and one cup: the cup must snap into the claw legs, and the strut pin must sit in the deck hole of
the body.

**MakerWorld.** The test project can be uploaded as a print profile. Open it in Bambu Studio, slice the plate (this adds
the plate thumbnail) and save it, then upload it from the MakerWorld page or with *Publish* in Bambu Studio. MakerWorld
asks for at least one real photo of the printed parts, and the profile name must not contain claims such as "best",
"perfect" or "fast".

## Hardware (per drone)

The full list is in `ACwing_Mech_A1_BoM.xlsx`.

| Part | Qty | Note |
|---|---|---|
| Hot-melt insert M2 × 3 × Ø3.0 (Hangtife HLTI-M2-001) | 10 | 4 stack bosses, 4 tray pads of the body (from the deck underside), 2 tray flow bosses (+ 2 per spare tray) |
| Nut M2, carbon steel (from the M2 kit) | 8 | in the hex pockets under the deck, below the ear screws |
| Damping ball M2 (QUARKZMAN), H 6.0, OD 4.9, slot Ø3.03 × 1.14, bore Ø2.0 | 4 | FC soft mount |
| Stack screw M2 × 20, **nylon** DIN 84 cheese head (Enkotrade, non-magnetic: it passes through the FC next to its compass) | 4 | from the cover top, head in the Ø4.4 counterbore; M2 × 30 nylon or A4 with the GPS option. A steel M2 × 20 from the kit fits too, but it is magnetic: calibrate the compass |
| Ear screw M2 × 6 button head, carbon steel black (Moqinai M2 kit, 1520 pcs) | 8 | 2 per basket, from the top through the head bore of the shoulder (Ø3.9: head ≤ 3.7 mm, measure it), ear and body pad into the nut; tip 1.4 mm clear below |
| Tray screw M2 × 6 button head, carbon steel black (same M2 kit) | 4 | from below through the tray posts into the body inserts |
| Flow board screw M2 × 6, nylon | 2 | from below through the tray pocket floor |

2026-11-18: screws from cheap kits (see `ACwing_Mech_A1_screws_kit.xlsx`). The kit has no M2 × 5 and no M2 × 18, so the ears take
M2 × 6 and the stack M2 × 20 (cover counterbore 0.4 mm higher and Ø4.4). Keep steel and cheap "304" screws (often slightly
magnetic) away from the compasses: the stack screws are nylon.

## Build order

1. **Inserts.** Set the 4 stack inserts (from the top of the bosses), the 4 tray inserts (from the deck underside, in the
   tray pads) and the 2 flow inserts in the tray bosses with a soldering iron at 220–240 °C, flush.
2. **Baskets on the body.** Put an M2 nut in each hex pocket under the deck, then 2 × M2 × 6 per basket from the top
   through the head bore of the shoulder, the ear and the pad.
3. **Motors.** Push the TPU sleeves on the motors and put them in the cups (2 CW + 2 CCW). The motors have no connector:
   before soldering, thread the two leads out of the cup floor hole, along the channel under the floor, out of the cup
   slot into the lead leg, up the **closed channel of the lead rod**, down through the ear into the **deck gutter** and
   up at the ESC corner to the pads (about 80 mm per wire). Then push the cup up into the claw legs until it snaps: the
   strut pin goes into the hole under the deck.
4. **Stack.** Per corner: S0 spacer (4.0 mm), ESC 1S rev A, S1 spacer (2.57 mm), damping ball with the FC rev A in its slot.
   With the GPS option: S2 spacer (3.57 mm) and the GPS rev A on top.
5. **Cables.**
   - Cable A (ESC J1 → FC J2, 10 mm, 1:1), as before.
   - Cable C (FC J4 → Flow J1, 60 mm, wires twisted): down through the deck slot to Flow J1 (connector edge to +X).
   - Cable D (battery pigtail, 30 mm): through the slot in the rear lobe, then through the notch of the tray rear wall.
6. **Cover.** Put it on and drive the four M2 × 20 nylon (GPS: M2 × 30) screws from the top into the boss inserts. Stop when
   the heads seat in the counterbores: do not crush the balls.
7. **Flow board in the tray.** Slide Flow rev A in from the +X side, sensor side down, until it stops; 2 × M2 × 6 nylon from
   below through the pocket floor.
8. **Battery.** Put the pack in the tray box (pigtail through the rear notch), 0.5 mm foam on top, then screw the tray
   to the body with 4 × M2 × 6 from below. Plug cable C and the JST-PH lead. To change the pack, unscrew the tray.
9. **Propellers.** The front pair is green.

## Configurations

| Tray | Pack | Drone mass* | T/W* | Flight time vs the preliminary draft + 400 mAh* | First frame mode (FE) |
|---|---|---|---|---|---|
| T400 | 400 mAh, 11.5 g | ≈ 71.7 g | 1.95 | × 0.73 | 85.9 Hz |
| T800 | 800 mAh, ≈ 22 g | ≈ 82.7 g | 1.69 | × 1.17 | 85.6 Hz |
| T1200 | 1200 mAh, ≈ 30 g | ≈ 91.1 g | 1.54 | × 1.52 | 91.1 Hz |

\* Indoor (no GPS), 1.0 mm boards, with the cover (2.9 g), rev M of 2026-11-15, kit screws of 2026-11-18 (nylon stack). FE model of the handoff §5; the first
two modes are the motor pods bouncing (handoff §15). Mass budget: `ACwing_Mech_A1_weight_study.md`.
- thrust ≈ 140 g;
- hover power ∝ m^1.5;
- reference is the preliminary draft (battery bay fused to the frame) with the 400 mAh pack, ≈ 58 g.

## Open points

- **2026-11-08 … 11-13:** A2 guard rings, print-first wave guards, one-piece holders, rev R parametric core (handoff §11–§14).
- **2026-11-15: rev M** → the rev R core needed about 26 cm³ of support and was hard to print: the frame is now
  **modular** (body, 4 baskets, 4 cups) and prints without supports; per motor 2 rods to the body ears + 1 strut from
  the cup to the deck; stack 4.5 mm higher (ESC USB-C free for charging); one-piece battery + flow tray, the pack goes in
  with the tray off the frame (handoff §15).
- **Tap test.** Do it on the first build and set the gyro notch from it: the motor pods are the first modes (86–96 Hz).
- **Fit of the snaps.** The cup snap bumps (0.3 mm) and the strut pin depend on the printer: check them on the first
  basket + cup before printing the set.
- **ELRS receiver.** Its mount on A1 is not modelled yet (FC J5 plug envelope checked).
