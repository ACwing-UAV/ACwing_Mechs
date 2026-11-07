# ACwing frame A1 – core + interchangeable battery trays (Mech A1)

> **Revisions.** A1 is the first released mechanics of the 1S mini drone. Earlier frames were **preliminary drafts**:
> internal design iterations, never released. The boards named here are the rev A release (FC rev A, ESC 1S rev A,
> GPS rev A, Flow rev A).

**Author:** Andrea Cirillo (ACwing). **From:** mechanical / frame design. **To:** electronics design and build.
**Date:** 2026-11-01, **updated 2026-11-06** (§9: rev A stack with 1.6 mm boards, ACwing_Mechs issue #2; electronics cover)
and **2026-11-07** (§10: ESC J1 on the front edge then toward the front corner, cable C and flow board per the HW handoff §0.14–§0.17,
motors back at RM 51; weight study).
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
| T400 | 400 mAh, 11.5 g | 20 × 40 × 8 | 3.44 g | ≈ 71.1 g | 1.97 | × 0.74 | 127 Hz |
| T800 | 800 mAh, ≈ 22 g | 25 × 45 × 9 | 3.61 g | ≈ 81.8 g | 1.71 | × 1.19 | (124 Hz)** |
| T1200 | 1200 mAh, ≈ 30 g | 30 × 64 × 8 | 4.11 g | ≈ 90.3 g | 1.55 | × 1.54 | (103 Hz)** |

\* Indoor configuration (ESC 1S rev A + FC rev A + Flow rev A, no GPS), boards 1.6 mm, electronics cover (2.8 g),
2026-11-07. Mass budget and lightening options: `ACwing_Mech_A1_weight_study.md`.
\** T800 / T1200 modes from the 1.0 mm stack (§5); only T400 was rerun on 2026-11-07.
- Thrust ≈ 140 g.
- Hover power ∝ m^1.5, with the same usable fraction of the capacity.
- The reference is the preliminary draft (battery bay fused to the frame) with the 400 mAh pack, ≈ 58 g.

Cost of interchangeability, compared with the preliminary draft (frame 15.55 g):
- core 14.95 g (thinner motor holders since 2026-11-07; 15.44 g before);
- tray as in the table above;
- 4 brass inserts + 4 M2 × 5 A4 screws ≈ 1.2 g (estimate, see the BoM; ≈ 0.85 g with titanium screws).

Net mass overhead: **+4.1 g (T400), +4.3 g (T800), +4.8 g (T1200)**.

## 1. Core A1 (changes from the preliminary draft)

| Item | A1 |
|---|---|
| Battery bay, latch, flow plate | not on the frame: they are on the trays |
| Battery envelope | box 31.2 × 66 × 9.9 mm under the deck (top at z −6.7, centred, open to the rear for insertion). Nothing of the core enters it. Blend fillets of ring and arm roots are trimmed there. |
| Tray lugs | 4 bosses Ø6 from the deck down to a flat face at **z −9.0**, at frame **(±20.0, −6.0)** and **(±20.0, +3.5)**. Each has a Hangtife HLTI-M2-001 insert in a Ø2.8 seat, open downwards. |
| Knee braces | blade braces Ø2.4 × 3 mm from each arm (radius 25, z −15) to the nearest lug. They give back the stiffness the bay rails provided in the preliminary draft. |
| Side spars | 3 mm wide spar on each side, joining the two lugs of that side to the deck |
| Motors | at RM 51 from the frame centre (frame (±36.06, ±36.06)); RM 53 for a few hours on 2026-11-07, dropped when ESC J1 moved toward the corner (§10) |
| Arms | start at radius 23.5, 10 / 3.5 mm deep |
| Rear spokes | the inner spokes of the rear rings are at 75° / −75°, clear of the T1200 corners |
| Motor leads M2 / M3 | they leave the holder on the other side of the arm (`LEAD_SIDE`) and enter the deck slot from below. Lead z under the deck is −8.65. The ESC pads are unchanged. |
| Deck | no rear notch; cable C slot behind the rear grommets, board (u 20.5 … 23.7, v −13.5 … −10.1) |
| Motor holders | walls 0.8 mm, floor 1.0 mm (weight study, 2026-11-07) |
| Mass | 14.95 g PETG, watertight mesh; 131.5 × 131.5 × 37.8 mm |

## 2. Trays

- **Structure.** Every tray has the same outer rails, at x ±15.3…16.5 (where the 30 mm pack needs them). The four tabs
  to the lugs are therefore short and stiff on every tray. Narrower packs (T400, T800) are centred by ribs at 8 mm pitch running from
  the rail to the lip (no continuous inner wall, −0.4 g).
- **Battery.** It sits on 1.0 mm lips, top 0.5 mm under the deck (z −6.7), stopped at the front by a cross wall. It is held at the rear by a
  snap latch (tongue with a ramp, 5 mm wide). The pack slides in **from the rear** after the tray is screwed on.
- **Tabs.** 6.8 mm wide (y), from the rail out to 3.4 mm past the lug axis, 2.6 mm thick, top face at z −9.0 against the lug face. **M2 × 5 A4 (or titanium) screws from below**
  give 2.4 mm engagement in the 3 mm insert.
- **Flow board.** A plate under the tray carries the ACwing Flow rev A board on 2 bosses Ø4.8 × 2.4 with M2 inserts,
  plus a lightening window. Since 2026-11-07 the board is **turned 90°, connector (top) edge toward the frame right
  (+X)**, as the HW handoff §0.14 asks. The bosses are at frame (6.6, ±8.0), the board spans x −6.3 … 18.7 and
  y ±10.5, and the PMW3901 optical axis stays on the frame centre. The plate reaches y −11.6 on every tray.
  - Lens tip above the ground with the drone landed, 1.6 mm board: **10.7 mm (T400, T1200), 9.7 mm (T800)**. The 9 mm pack sits 1 mm lower.
  - The flow board screws stay M2 × 4 nylon (1.6 mm board + 2.4 mm in the insert).
- **Lead notches.** The motor leads cross over the rail tops at |y| 12.1…13.3. The rails have 0.9 mm deep notches there.
- **T1200 note.** The front and rear corners of the 64 mm pack sit partly under the propeller discs, about 2 % of
  the disc area. This gives a slight blockage of the downwash. It is accepted for the endurance tray.

## 3. Cables

- **C (FC J4 → Flow J1).** Per the HW handoff §0.14: not straight down the right edge, where the M2 motor pads sit.
  The cable runs back along the FC right edge and drops through the deck slot behind the rear grommets as a round,
  twisted 4-wire bundle. It goes down outside the tray rail, past the front tray tab, and into Flow J1, which faces
  +X. Wire lengths between housings: 49–53 mm, make the cable 60 mm.
  - Distance from the M2 motor pads: ≥ 10 mm.
  - Distance from the M2 leads where they rise beside the ESC edge: 6.4 mm. This is the limit set by the FC J1 USB-C
    plug envelope at the rear-right corner.
- **D (battery pigtail).** Leaves the core past the rear deck tip. The JST-PH pair is at (0, −40.5, −9.6), behind the
  tray, so it is plugged after the pack is inserted. The insertion path is clear of it.
- **A (ESC J1 → FC J2).** Both connectors are on the front board edge, with pin 1 at the +u end, so the cable is a 1:1
  U-loop. ESC J1 is at (+13.3, +16.08) since the ESC change of 2026-11-07, toward the front corner.
  - It rises right behind the ESC plug, below the front-left guard top ring, bulges 2.5 mm out above the ring and
    enters FC J2 from the front. It shifts 9.7 mm along u, in the upper half.
  - Wire 15.4 mm between the housings; make all 8 wires 20 mm.
  - Clearances: guard ring 0.42 mm, propeller disc 2.8 mm.
- **B (GPS option).** GPS rev A J1 sits right above FC J3 (layout 2026-10-24): short straight loop, 13 mm of wire.

## 4. Checks (SDF sampling, mm³, h = 0.06–0.15 mm)

Rerun on 2026-11-07 (§10: RM 51, ESC J1 toward the front corner, new cable C, turned flow board, 0.8 mm cover):
T400 indoor, T400 GPS, T800 indoor, T1200 indoor.
- **0** for every pair: frame, tray, battery, insertion path, propellers, stack boards and parts, plugs and plug
  envelopes, wires, hardware, optical cones, cover.
- **Tray × battery: 0.003 (T400), 0.036 (T800), 0 (T1200) mm³.** This is the pack resting on the lips.
- Details: `Checks/ACwing_Mech_A1_assembly_checks_<tray>_<indoor|gps>.json` and `Checks/README.md`.

## 5. Vibration (voxel FE, hex8, h 0.8 mm, PETG E 2000 MPa, lumped motors / stack / battery / flow)

| Case | Frame + tray | First global mode ("saddle", diagonal motors in phase) |
|---|---|---|
| Preliminary draft (bay fused) | 15.65 g | 100.8 Hz |
| A1 + T400 | 18.3 g | 125.8 Hz |
| A1 + T800 | 17.8 g | 123.9 Hz |
| A1 + T1200 | 18.5 g | 102.6 Hz |
| **A1, 0.8 mm motor holders, rev A stack 1.6 mm + cover (19 g lumped), T400 (2026-11-07)** | **18.4 g** | **127.0 Hz** |

The 2026-11-07 run has a heavier stack (19 g instead of 12 g) and lighter motor holders: +1.2 Hz for T400. With the
motors at RM 53 it was 121.2 Hz. Weight variants
are in `ACwing_Mech_A1_weight_study.md`. Local motor-holder / leg modes sit at about 123 Hz in all cases. Everything is far below the propeller bands (≥ 326 Hz).

The first modes still fall inside the 60–130 Hz band that matters for the FC soft mount. Do a bench **tap test** on the
printed core with a tray fitted, and set the gyro notch from it.

## 6. Hardware per drone

| Part | Qty | Note |
|---|---|---|
| Hangtife HLTI-M2-001 insert (M2 × 3 × Ø3.0) | 4 (stack) + 4 (lugs) + 2 (flow bosses, per tray) | Ø2.8 seats |
| M2 × 5 screw, A4 or titanium | 4 | tray to core, from below |
| Silicone grommets M2, H 6.0, OD 5.0, groove Ø3.0 × 1.6 | 4 | FC soft mount (bumpers), for 1.6 mm boards |
| Stack screws M2 × 14 ISO 7380 (M2 × 25 with GPS) | 4 | titanium (recommended, −0.6 g) or A4, from the cover top, as requested by electronics |
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
| `00 - Docs/00 - Mech_A1_Docs/` | print files, BoM, STEP, renders, checks, weight study, this note |

## 9. Rev A stack, 1.6 mm boards (ACwing_Mechs issue #2, 2026-11-06)

**Boards.** All four rev A boards are 1.6 mm (ACwing_HW PR "Boards rev A: 1.6 mm PCB thickness"). Connector layout
2026-11-02/03:
- ESC J1 on the rear edge;
- FC J2 and J6 on the front edge, J5 (ELRS) on the rear edge, J3 / J4 on the right edge, J1 USB-C at the chamfer;
- GPS J1 / J2 on the right edge;
- Flow J1 / J2 on the top edge.

**Stack (frame z).**

| Item | z | Note |
|---|---|---|
| ESC 1S | −2.0 … −0.4 | on the bosses (unchanged) |
| S1 spacer | −0.4 … 2.4 | 2.8 mm (was 2.57) |
| Silicone grommet | 2.4 … 8.4 | H 6.0, OD 5.0, groove Ø3.0 × 1.6, 2.2 mm above / below the board |
| FC | 4.6 … 6.2 | 5.0 mm above the ESC (handoff: ≥ 4.5, 5 recommended) |
| S2 spacer (GPS) | 8.4 … 12.2 | 3.8 mm (was 3.57) |
| GPS | 12.2 … 13.8 | 6 mm above the FC |
| Cover, indoor | 5.0 … 12.45 | screws M2 × 14, heads at 9.9, tips at −4.1 (2026-11-07; was M2 × 16 to 13.5) |
| Cover, GPS | 5.0 … 22.3 | screws M2 × 25, heads at 20.6, tips at −4.4 |

**Issue #2 checklist.**
- *Import the frame: native CAD + STEP.* The frame A1 core, trays, spacers, sleeves and cover are in `01 - Frame/`
  and `02 - Mounts/` (source meshes). Faceted STEP solids of the core, trays and covers are in `STEP/Parts/`. The
  assembly STEP (hardware and cables) is in `STEP/`. The parts come from signed-distance models, so the native CAD is
  the FreeCAD assembly macro with its data file.
- *Holes, stack heights, connector access.* The 20 × 20 holes and the bosses are unchanged. The stack heights are in
  the table above. Every connector stays reachable:
  - USB-C FC J1 through the cover notch at +X; ESC J4 USB-C at −X, outside the cover;
  - ESC link B (FC J6) on the front edge and FC J5 (ELRS) on the rear edge, through the cover openings, clear of the
    frame;
  - checks in §4.
- *Flow board mount.* On the tray plate, as before. The 1.6 mm board puts the lens 0.6 mm lower (10.7 mm above the
  ground, T400). Cable C now enters Flow J1 from the front of the board.
- *Print and fit-check.* Still to do on the bench: print the core, a tray and the cover, fit the boards and check the
  grommet preload, the screw lengths and the cable routing.

**Frame.** No change to the core and trays: all checks pass with the rev A stack. Only the spacers changed (S1, S2),
plus the new cover.

**Cables.** A: 67–70 mm of wire, make 75 mm. C: 53–64 mm, make 70 mm. B: 13.5 mm. D: unchanged. (Superseded on
2026-11-07, see §3 and §10: A 20 mm, C 60 mm.)

**Mass.** +8.6 g in the indoor configuration (boards +4.2 g, cover 4.4 g, screws). Drone T400 ≈ 71.1 g (66.7 g
without the cover). The FE modes in §5 were computed with the 1.0 mm stack; the heavier stack lowers them slightly.
The tap test on the first build settles it.

## 10. ESC J1 on the front edge, cable C, flow board, weight (2026-11-07)

Answer to the ACwing_HW mechanical handoff §0.14–§0.17: ESC 1S J1 on the front edge, then moved toward the front corner;
cable C route; flow board connector edge to the right.

**Guard ring and RM.** The board front edge faces the front-left motor. With J1 at (+9.6, +16.88), the top ring of its
prop guard (z 2.5 … 3.9, radius 28.5 … 29.5 from the motor axis) passed right above the J1 plug back:
- the plug fitted under the ring with 0 mm to spare;
- the 8 wires had no room to rise between the plug and the ring.

A first answer moved the motors out to RM 53. The electronics then moved **J1 toward the front corner, to (+13.3,
+16.08)** (HW handoff §0.17). There the ring is further from the plug, so **the frame goes back to RM 51**: 131.5 mm,
lighter and stiffer than at RM 53. Cable A clears the ring by 0.42 mm.

**Cable A and cable C:** see §3. **Flow board:** see §2.

**Cover:** the indoor roof is 0.6 mm lower, because no cable crosses the FC any more. It clears the FC L3 inductor
(z 10.2) by 0.85 mm. Walls and roof are 0.8 mm (weight study). Stack screws: M2 × 14 indoor, M2 × 25 GPS.

**Checks:** all zero (§4). Smallest clearances:

| Cable | Clearance |
|---|---|
| A | guard ring 0.42 mm, propeller disc 2.8 mm |
| C | frame 0.49 mm, tray 0.69 mm, FC J1 USB-C plug envelope 2.4 mm, M2 motor leads 6.4 mm |

**Frame:** first free-free mode with T400 **127 Hz**, against 121 Hz at RM 53.

**Weight:** −2.2 g against 2026-11-06 (motor holders −0.5 g, cover −1.6 g, shorter screws −0.1 g). The other options
and their effect on the first mode are in `ACwing_Mech_A1_weight_study.md`.

**For HW rev B:** the board edge centres face the guard rings. Keep low connectors on the ESC toward the board corners.
