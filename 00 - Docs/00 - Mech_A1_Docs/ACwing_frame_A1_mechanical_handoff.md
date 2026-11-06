# ACwing frame A1 – core + interchangeable battery trays (Mech A1)

> **Revisions.** A1 is the first released mechanics of the 1S mini drone. Earlier frames were **preliminary drafts**:
> internal design iterations, never released. The boards named here are the rev A release (FC rev A, ESC 1S rev A,
> GPS rev A, Flow rev A).

**Author:** Andrea Cirillo (ACwing). **From:** mechanical / frame design. **To:** electronics design and build.
**Date:** 2026-11-01, **updated 2026-11-06** (§9: rev A stack with 1.6 mm boards, ACwing_Mechs issue #2; electronics cover).
**Follows:** the preliminary-draft mechanical answer and electronics reply, in ACwing_HW `00 - Docs/04 - System_Docs`. The stack
(ESC 1S rev A / FC rev A / GPS rev A option), the bosses, the inserts, the corner columns and cables A/B come from
the preliminary draft unchanged.
**Baseline:** 1S mini drone, indoor, no GPS (decision 2026-10-19).

## 0. Summary

The battery bay is not part of the printed frame. Frame A1 is a **core** with four lugs under the deck, and the
battery rides in a **screw-on tray**. There are three trays, so a bigger pack only needs a new tray (3.4–4.2 g of PETG),
not a new frame.

| Tray | Battery (1S LiPo) | Battery size W × L × H | Tray mass | Drone mass* | T/W* | Flight time vs the preliminary draft + 400 mAh* | First frame mode |
|---|---|---|---|---|---|---|---|
| T400 | 400 mAh, 11.5 g | 20 × 40 × 8 | 3.36 g | ≈ 71.1 g | 1.97 | × 0.74 | 126 Hz |
| T800 | 800 mAh, ≈ 22 g | 25 × 45 × 9 | 3.67 g | ≈ 81.9 g | 1.71 | × 1.19 | 124 Hz |
| T1200 | 1200 mAh, ≈ 30 g | 30 × 64 × 8 | 4.18 g | ≈ 90.4 g | 1.55 | × 1.54 | 103 Hz |

\* Indoor configuration (ESC 1S rev A + FC rev A + Flow rev A, no GPS), **boards 1.6 mm and electronics cover**
(2026-11-06): + 8.6 g over the 1.0 mm stack without cover (boards + 4.2 g, cover 4.4 g, screws). Without the cover:
71.1 → 66.7 g (T400), flight time × 0.81. The frame modes were computed with the 1.0 mm stack (§5).
- Thrust ≈ 140 g.
- Hover power ∝ m^1.5, with the same usable fraction of the capacity.
- The reference is the preliminary draft (battery bay fused to the frame) with the 400 mAh pack, ≈ 58 g.

Cost of interchangeability, compared with the preliminary draft (frame 15.55 g):
- core 15.44 g;
- tray as in the table above;
- 4 brass inserts + 4 M2 × 5 A4 screws ≈ 1.2 g (estimate, see the BoM; ≈ 0.85 g with titanium screws).

Net mass overhead: **+4.5 g (T400), +4.8 g (T800), +5.3 g (T1200)**.

## 1. Core A1 (changes from the preliminary draft)

| Item | A1 |
|---|---|
| Battery bay, latch, flow plate | not on the frame: they are on the trays |
| Battery envelope | box 31.2 × 66 × 9.9 mm under the deck (top at z −6.7, centred, open to the rear for insertion). Nothing of the core enters it. Blend fillets of ring and arm roots are trimmed there. |
| Tray lugs | 4 bosses Ø6 from the deck down to a flat face at **z −9.0**, at frame **(±20.0, −6.0)** and **(±20.0, +3.5)**. Each has a Hangtife HLTI-M2-001 insert in a Ø2.8 seat, open downwards. |
| Knee braces | blade braces Ø2.4 × 3 mm from each arm (radius 25, z −15) to the nearest lug. They give back the stiffness the bay rails provided in the preliminary draft. |
| Side spars | 3 mm wide spar on each side, joining the two lugs of that side to the deck |
| Arms | start at radius 23.5, 10 / 3.5 mm deep |
| Rear spokes | the inner spokes of the rear rings are at 75° / −75°, clear of the T1200 corners |
| Motor leads M2 / M3 | they leave the holder on the other side of the arm (`LEAD_SIDE`) and enter the deck slot from below. Lead z under the deck is −8.65. The ESC pads are unchanged. |
| Deck | no rear notch; Qwiic slot for cable C |
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
  M2 inserts, plus a lightening window.
  - Lens tip above the ground with the drone landed, 1.6 mm board: **10.7 mm (T400, T1200), 9.7 mm (T800)**. The 9 mm pack sits 1 mm lower.
  - The flow board screws stay M2 × 4 nylon (1.6 mm board + 2.4 mm in the insert).
- **Lead notches.** The motor leads cross over the rail tops at |y| 12.1…13.3. The rails have 0.9 mm deep notches there.
- **T1200 note.** The front and rear corners of the 64 mm pack sit partly under the propeller discs, about 2 % of
  the disc area. This gives a slight blockage of the downwash. It is accepted for the endurance tray.

## 3. Cables

- **C (FC J4 → Flow J1).** FC J4 is on the right board edge, Flow J1 on the board top edge (rev A layout 2026-11-02).
  Through the deck slot, then **down outboard of the M2 knee brace and under it**, outside the tray rail and under the
  flow plate, round to the front of the flow board and into J1. Wire lengths between housings: GND 63, 3V3 58, SDA 54,
  SCL 53 mm (T800 +0.7 mm). Make the cable 70 mm.
- **D (battery pigtail).** Leaves the core past the rear deck tip. The JST-PH pair is at (0, −40.5, −9.6), behind the
  tray, so it is plugged after the pack is inserted. The insertion path is clear of it.
- **A (ESC J1 → FC J2).** ESC J1 is on the rear board edge, FC J2 on the front edge (rev A layout 2026-11-02). The
  cable rises in the rear corridor, crosses behind the FC rear edge as a round bundle (this reverses the pin order, so
  the cable is 1:1 pin 1 → pin 1), runs flat over the FC top at z 10.4 under the cover, and turns down into FC J2 in a
  U-loop. Wire lengths 64–67 mm: make all 8 wires 75 mm.
- **B (GPS option).** GPS rev A J1 sits right above FC J3 (layout 2026-10-24): short straight loop, 13 mm of wire.

## 4. Checks (SDF sampling, mm³, h = 0.06–0.15 mm)

All three trays:
- **0** for every pair:
  - core × battery, core × insertion path, core × tray;
  - tray × motor leads, wires, flow board, housings, propellers;
  - optical cones × core, tray, battery, wires;
  - frame × stack, plugs, wires, hardware;
  - pigtail and PH pair × insertion path.
- **Tray × battery: 0.003 (T400), 0.031 (T800), 0 (T1200) mm³.** This is the pack resting on the lips; a finer locator finds no
  penetration.
- Tray screws M2 × 5 × frame, tray, wires, battery, flow board, housings: 0 on all trays.
- Details: `Checks/ACwing_Mech_A1_assembly_checks_<tray>.json`.

## 5. Vibration (voxel FE, hex8, h 0.8 mm, PETG E 2000 MPa, lumped motors / stack / battery / flow)

| Case | Frame + tray | First global mode ("saddle", diagonal motors in phase) |
|---|---|---|
| Preliminary draft (bay fused) | 15.65 g | 100.8 Hz |
| A1 + T400 | 18.3 g | 125.8 Hz |
| A1 + T800 | 17.8 g | 123.9 Hz |
| A1 + T1200 | 18.5 g | 102.6 Hz |

Local motor-holder / leg modes sit at about 123 Hz in all cases. Everything is far below the propeller bands (≥ 326 Hz).

The first modes still fall inside the 60–130 Hz band that matters for the FC soft mount. Do a bench **tap test** on the
printed core with a tray fitted, and set the gyro notch from it.

## 6. Hardware per drone

| Part | Qty | Note |
|---|---|---|
| Hangtife HLTI-M2-001 insert (M2 × 3 × Ø3.0) | 4 (stack) + 4 (lugs) + 2 (flow bosses, per tray) | Ø2.8 seats |
| M2 × 5 screw, A4 or titanium | 4 | tray to core, from below |
| Silicone grommets M2, H 6.0, OD 5.0, groove Ø3.0 × 1.6 | 4 | FC soft mount (bumpers), for 1.6 mm boards |
| Stack screws M2 × 16 ISO 7380 (M2 × 25 with GPS) | 4 | titanium or A4, from the cover top, as requested by electronics |
| Flow board screws M2 × 4, nylon | 2 | from the sensor side |

Full list: `ACwing_Mech_A1_BoM.xlsx`.

## 7. Printing

PETG with a **0.4 mm nozzle** for core and trays:
- 0.42–0.45 mm lines, Arachne walls;
- 0.12–0.16 mm layers, 3 perimeters;
- 30–40 % gyroid infill.

Sleeves in TPU 95A with the same nozzle. Print a test coupon for the Ø2.8 insert seats.

Electronics cover in translucent PLA, upright (open bottom on the bed, logo up), tree supports inside under the roof:
see `02 - Mounts/Electronics_Cover_A1/README.md`.

- **Core:** print it upside down, with the guard-ring tops on the bed and a 3–5 mm brim.
  - Tree supports go under the deck (≈ 9 mm), the stack bosses and the motor holders.
  - Upside down there is about 10 % less overhang than upright, and the supports are much shorter (upright, the deck is 28 mm up).
- **Trays:** print them upright, with the flow bosses on the bed.
  - Tree supports go under the plate, under the rear rail ends (behind the plate) and under the four outboard tabs.
  - The battery cavity stays free of supports.
- The print files in `Prints/` are already exported in these orientations.

## 8. Files (repository ACwing_Mechs)

| Path | What |
|---|---|
| `01 - Frame/Frame_A1/ACwing_Frame_A1_core.stl` | core, source mesh (assembly position) |
| `02 - Mounts/Battery_Trays_A1/ACwing_Tray_A1_T400/T800/T1200.stl` | trays, source meshes |
| `02 - Mounts/Stack_Spacers/`, `02 - Mounts/Motor_Sleeves/` | spacers S1/S2 (1.6 mm boards), TPU sleeves (A1) |
| `02 - Mounts/Electronics_Cover_A1/ACwing_Cover_A1_indoor/gps.stl` | electronics cover, translucent PLA, source meshes |
| `03 - Assembly/ACwing_Mech_A1/ACwing_Mech_A1.FCMacro` | FreeCAD assembly; writes the print files to `00 - Docs/00 - Mech_A1_Docs/Prints/` |
| `00 - Docs/00 - Mech_A1_Docs/` | print files, BoM, STEP, renders, checks, this note |
