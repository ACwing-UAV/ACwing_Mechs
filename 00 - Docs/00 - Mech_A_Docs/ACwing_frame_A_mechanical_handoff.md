# ACwing frame A – core + interchangeable battery trays (Mech A)

> **Revisions.** Design log of the frame used by **Mech A**. The boards it names are the rev A release (FC rev A,
> ESC 1S rev A, GPS rev A, Flow rev A). Updated 2026-10-31 for the Mech A release: masses, print orientation, files.

**Author:** Andrea Cirillo (ACwing). **From:** mechanical / frame design. **To:** electronics design and build.
**Date:** 2026-10-24. **Supersedes for the battery side:** frame C2 (`ACwing_frame_C2_mechanical_answer.md`, in ACwing_HW `00 - Docs/04 - System_Docs`). The stack
(ESC 1S rev A / FC rev A / GPS rev A option), the bosses, the inserts, the corner columns and cables A/B are unchanged from C2.
**Baseline:** 1S mini drone, indoor, no GPS (decision 2026-10-19).

## 0. Summary

The battery bay is no longer part of the printed frame. The frame becomes a **core A** with four lugs under the deck,
and the battery rides in a **screw-on tray**. There are three trays, so a bigger pack only needs a new tray (3.4–4.2 g of PETG) instead of a new frame.

| Tray | Battery (1S LiPo) | Battery size W × L × H | Tray mass | Drone mass* | T/W* | Flight time vs C2 + 400 mAh* | First frame mode |
|---|---|---|---|---|---|---|---|
| T400 | 400 mAh, 11.5 g | 20 × 40 × 8 | 3.36 g | ≈ 62.5 g | 2.24 | × 0.90 | 126 Hz |
| T800 | 800 mAh, ≈ 22 g | 25 × 45 × 9 | 3.67 g | ≈ 73.3 g | 1.91 | × 1.41 | 124 Hz |
| T1200 | 1200 mAh, ≈ 30 g | 30 × 64 × 8 | 4.18 g | ≈ 81.8 g | 1.71 | × 1.79 | 103 Hz |

\* Indoor configuration (ESC 1S rev A + FC rev A + Flow rev A, no GPS). Thrust ≈ 140 g. Hover power ∝ m^1.5, same usable fraction of the capacity. Reference is C2
with the 400 mAh pack, ≈ 58 g. Note: the 66.5 g in the C2 handoff §0 used a 20 g battery; the real 400 mAh pack is 11.5 g.

Cost of interchangeability, compared with C2 (frame 15.55 g):
- core 15.44 g;
- tray as in the table above;
- 4 brass inserts + 4 M2 × 5 A4 screws ≈ 1.2 g (estimate, see the BoM; ≈ 0.85 g with titanium screws).

Net mass overhead: **+4.5 g (T400), +4.8 g (T800), +5.3 g (T1200)**. (The first issue of this note used 0.64 g for the
tray hardware, too low.)

## 1. Core A (changes from previous draft)

| Item | A |
|---|---|
| Battery bay, latch, flow plate | removed from the frame; they are on the trays now |
| Battery envelope | box 31.2 × 66 × 9.9 mm under the deck (top at z −6.7, centred, open to the rear for insertion). Nothing of the core enters it. Blend fillets of ring and arm roots are trimmed there. |
| Tray lugs | 4 bosses Ø6 from the deck down to a flat face at **z −9.0**, at frame **(±20.0, −6.0)** and **(±20.0, +3.5)**. Each has a Hangtife HLTI-M2-001 insert in a Ø2.8 seat, open downwards. |
| Knee braces | blade braces Ø2.4 × 3 mm from each arm (radius 25, z −15) to the nearest lug. They give back the stiffness the bay rails used to provide. |
| Side spars | 3 mm wide spar on each side, joining the two lugs of that side to the deck |
| Arms | start at radius 23.5, slightly deeper (10 / 3.5 mm) |
| Rear spokes | the inner spokes of the rear rings moved to 75° / −75° to clear the T1200 corners |
| Motor leads M2 / M3 | they now leave the holder on the other side of the arm (`LEAD_SIDE`) and enter the deck slot from below. Lead z under the deck is −8.65. The ESC pads are unchanged. |
| Deck | rear notch for the old bay removed; Qwiic slot for cable C unchanged |
| Mass | 15.44 g PETG, watertight mesh |

## 2. Trays

- **Structure.** Every tray has the same outer rails, at x ±15.3…16.5 (where the 30 mm pack needs them). The four tabs
  to the lugs are therefore short and stiff on every tray. Narrower packs (T400, T800) are centred by ribs at 8 mm pitch running from
  the rail to the lip (no continuous inner wall, −0.4 g).
- **Battery.** It sits on 1.0 mm lips, top 0.5 mm under the deck (z −6.7), stopped at the front by a cross wall. It is held at the rear by a
  snap latch (tongue with a ramp, 5 mm wide). The pack slides in **from the rear** after the tray is screwed on.
- **Tabs.** 6.8 mm wide (y), from the rail out to 3.4 mm past the lug axis, 2.6 mm thick, top face at z −9.0 against the lug face. **M2 × 5 A4 (or titanium) screws from below**
  give 2.4 mm engagement in the 3 mm insert.
- **Flow board.** A plate under the front part of the tray carries the ACwing Flow rev A board on 2 bosses Ø4.8 × 2.4 with
  M2 inserts (same as C2), plus a lightening window. Lens tip above the ground with the drone landed:
  **11.3 mm (T400, T1200), 10.3 mm (T800)** with a 1.0 mm board (handoff), because the 9 mm pack sits 1 mm lower. The Flow rev A
  STEP in ACwing_HW has a 1.6 mm PCB: then 10.7 / 9.7 mm. To be confirmed by electronics.
- **Lead notches.** The motor leads cross over the rail tops at |y| 12.1…13.3. The rails have 0.9 mm deep notches there.
- **T1200 note.** The front and rear corners of the 64 mm pack sit partly under the propeller discs, about 2 % of
  the disc area. This gives a slight blockage of the downwash. It is accepted for the endurance tray.

## 3. Cables (changes from previous draft)

- **C (FC J4 → Flow J1).** Through the deck slot, then **down outboard of the M2 knee brace and under it**, outside the
  tray rail and below the flow plate, into Flow J1. Wire lengths between housings: GND 42, 3V3 40, SDA 38, SCL 38 mm (T800: +1 mm, flow board 1 mm lower).
  Make the cable 45 mm.
- **D (battery pigtail).** Leaves the core past the rear deck tip. The JST-PH pair is at (0, −40.5, −9.6), behind the
  tray, so it is plugged after the pack is inserted. The insertion path is clear of it.
- **A.** Unchanged (17 mm of wire between the housings).
- **B (GPS option).** GPS rev A J1 now sits right above FC J3 (layout 2026-10-24): short straight loop, 13 mm of wire.

## 4. Checks (SDF sampling, mm³, h = 0.06–0.15 mm)

All three trays, with the rerouted cable C:
- **0** for every pair:
  - core × battery, core × insertion path, core × tray;
  - tray × motor leads, wires, flow board, housings, propellers;
  - optical cones × core, tray, battery, wires;
  - frame × stack, plugs, wires, hardware;
  - pigtail and PH pair × insertion path.
- **Tray × battery: 0.003 (T400), 0.031 (T800), 0 (T1200) mm³.** This is the pack resting on the lips; a finer locator finds no
  penetration.
- Tray screws M2 × 5 × frame, tray, wires, battery, flow board, housings: 0 on all trays.
- Details: `assembly_checks_<tray>.json`.

## 5. Vibration (voxel FE, hex8, h 0.8 mm, PETG E 2000 MPa, lumped motors / stack / battery / flow)

| Case | Core + tray | First global mode ("saddle", diagonal motors in phase) |
|---|---|---|
| C2 (bay fused) | 15.65 g | 100.8 Hz |
| C3 + T400 | 18.3 g | 125.8 Hz |
| C3 + T800 | 17.8 g | 123.9 Hz |
| C3 + T1200 | 18.5 g | 102.6 Hz |

Local motor-holder / leg modes sit at about 123 Hz in all cases. Everything is far below the propeller bands (≥ 326 Hz).

The first modes still fall inside the 60–130 Hz band that matters for the FC soft mount. Do a bench **tap test** on the
printed core with a tray fitted, and set the gyro notch from it.

## 6. Hardware per drone

| Part | Qty | Note |
|---|---|---|
| Hangtife HLTI-M2-001 insert (M2 × 3 × Ø3.0) | 4 (stack) + 4 (lugs) + 2 (flow bosses, per tray) | Ø2.8 seats |
| M2 × 5 screw, A4 or titanium | 4 | tray to core, from below |
| Stack screws | as C2 | titanium or A4, as requested by electronics |
| Flow board screws M2 × 4 | 2 | as C2 |

## 7. Printing

PETG with a **0.4 mm nozzle** for core and trays:
- 0.42–0.45 mm lines, Arachne walls;
- 0.12–0.16 mm layers, 3 perimeters;
- 30–40 % gyroid infill.

Sleeves in TPU 95A with the same nozzle. Print a test coupon for the Ø2.8 insert seats.

- **Core:** upside down, guard-ring tops on the bed, 3–5 mm brim; tree supports under the deck (≈ 9 mm), the stack bosses and
  the motor holders. About 10 % less overhang than upright, and much shorter supports (upright the deck is 28 mm up).
- **Trays:** upright, flow bosses on the bed; tree supports under the plate, under the rear rail ends (behind the plate)
  and under the four outboard tabs. The battery cavity stays free of supports.
- The print files in `Prints/` are already exported in these orientations.

## 8. Files (repository ACwing_Mechs)

| Path | What |
|---|---|
| `01 - Frame/Frame_C3/ACwing_Frame_C3_core.stl` | core, source mesh (assembly position) |
| `02 - Mounts/Battery_Trays_C3/ACwing_Tray_C3_T400/T800/T1200.stl` | trays, source meshes |
| `02 - Mounts/Stack_Spacers/`, `02 - Mounts/Motor_Sleeves/` | spacers S1/S2, TPU sleeves |
| `04 - Assembly/ACwing_Mech_A/ACwing_Mech_A.FCMacro` | FreeCAD assembly; writes the print files to `00 - Docs/00 - Mech_A_Docs/Prints/` |
| `00 - Docs/00 - Mech_A_Docs/` | print files, BoM, STEP, renders, checks, this note |
