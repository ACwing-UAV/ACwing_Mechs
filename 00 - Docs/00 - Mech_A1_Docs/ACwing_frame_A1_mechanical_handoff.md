# ACwing frame A1 – core + interchangeable battery trays (Mech A1)

> **Revisions.** A1 is the first released mechanics of the 1S mini drone. Earlier frames were **preliminary drafts**:
> internal design iterations, never released. The boards named here are the rev A release (FC rev A, ESC 1S rev A,
> GPS rev A, Flow rev A).

**Author:** Andrea Cirillo (ACwing). **From:** mechanical / frame design. **To:** electronics design and build.
**Date:** 2026-11-01, **updated 2026-11-06** (§9: rev A stack with 1.6 mm boards, ACwing_Mechs issue #2; electronics cover)
**2026-11-07** (§10: ESC J1 on the front edge then toward the front corner, cable C and flow board per the HW handoff §0.14–§0.17,
motors back at RM 51; weight study) and **2026-11-08** (§11: boards back to 1.0 mm, ESC J1 at (−10.5, +16.85) per the HW
handoff §0.19–§0.20; new **A2 guard rings**, motors at **RM 52**, new electronics cover) and **2026-11-12** (§12: print-first
redesign after the first print: **wave guards**, straight spokes, closed wire eyelets, flat-roof cover) and **2026-11-13**
(§13: one-piece motor holders with foot ring and wire channel, no landing loop, aligned spokes and bridges, wire holes;
**§14 rev R**: core redrawn as one parametric body, ring beam under the stack, foot at z −30, flow board cover).
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
| T400 | 400 mAh, 11.5 g | 20 × 40 × 8 | 3.30 g | ≈ 70.4 g | 1.99 | × 0.75 | 90.5 Hz** |
| T800 | 800 mAh, ≈ 22 g | 25 × 45 × 9 | 3.55 g | ≈ 81.2 g | 1.72 | × 1.21 | 76.7 Hz*** |
| T1200 | 1200 mAh, ≈ 30 g | 30 × 64 × 8 | 4.04 g | ≈ 89.6 g | 1.56 | × 1.56 | 62.7 Hz*** |

\* Indoor configuration (ESC 1S rev A + FC rev A + Flow rev A with its cover, no GPS), boards 1.0 mm, electronics cover (2.8 g),
rev R of 2026-11-13. Mass budget and lightening options: `ACwing_Mech_A1_weight_study.md`.
\** FE model of 2026-11-08 (§5, battery lumped on the tray lips): the A1 design of 2026-11-01 gives 102.5 Hz in the
same model, so these values are not comparable with the 127 Hz of the older model.
\*** Tray-local mode: the rear end of the long tray with the battery (frame saddle mode above it). Lower bound: the model
carries the pack as mass only. See §5 and §14.
- Thrust ≈ 140 g.
- Hover power ∝ m^1.5, with the same usable fraction of the capacity.
- The reference is the preliminary draft (battery bay fused to the frame) with the 400 mAh pack, ≈ 58 g.

Cost of interchangeability, compared with the preliminary draft (frame 15.55 g):
- core 18.12 g (rev R, §14): 2.6 g more than the frame of the preliminary draft
  (16.67 g in §13, 17.63 g on 2026-11-12, 15.55 g with the A2 rings of 2026-11-08, 14.95 g at RM 51 with the closed rings);
- tray as in the table above;
- 4 brass inserts + 4 M2 × 5 A4 screws ≈ 1.2 g (estimate, see the BoM; ≈ 0.85 g with titanium screws).

Net mass overhead: **+7.0 g (T400), +7.3 g (T800), +7.9 g (T1200)** (1.1 g of it is the print-first guards, 1.45 g the
rev R ring beam and longer holders). The flow board cover (0.67 g) is an added part and is not counted here.

## 1. Core A1 (changes from the preliminary draft)

| Item | A1 |
|---|---|
| Battery bay, latch, flow plate | not on the frame: they are on the trays |
| Battery envelope | box 31.2 × 66 × 9.9 mm under the deck (top at z −6.7, centred, open to the rear for insertion). Nothing of the core enters it. Blend fillets of ring and arm roots are trimmed there. |
| Tray lugs | 4 bosses Ø6 from the deck down to a flat face at **z −9.0** (planed flat, rev R), at frame **(±20.0, −6.0)** and **(±20.0, +3.5)**. Each has a Hangtife HLTI-M2-001 insert in a Ø2.8 seat, open downwards. |
| Ring beam (rev R) | two **side rails** at x ±20 carry the lugs: 3 mm wide, top z −4.1 (−5.6 inside the propeller discs), bottom z −9.0 → −15.5 toward the arms, flared to 6 mm and closed by a round cap 2.5 mm past each arm root; **deck ribs** 1.6 mm wide, top z −4.1, tie each stack boss to the rails. No knee braces, no side spars (§14) |
| Motors | at **RM 52** from the frame centre (frame (±36.77, ±36.77)) since 2026-11-08 (§11); RM 51 before |
| Guards | **wave guards** (2026-11-12, §12): 0.86 mm wall bulged 1.2 mm outward, top lip 1.2 × 0.8, lower rim 1.28 × 1.6 (360°), S ribbon 2.2 mm between them with 15 windows; open toward the body for φ ±46° (φ = 0 toward the frame centre) with 45° ramps and a 1.2 mm rim; bottom bridges between neighbouring guards. Before: A2 rings (2026-11-08, §11) |
| Arms | 2.2 mm blades on the diagonals, from the motor holder into the rail cap; top z −6.2 → −5.6, bottom z −14.75 → −15.0 (rev R) |
| Spokes | straight, 1.28 × 2.5 mm, top flush with the lower rim, 45° gusset on the holder, three per guard; on the rear guards one inner spoke is turned away to clear the T1200 corners; the ±45° spokes line up with the bridges between the guards (2026-11-13) |
| Motor leads path | the motors have no connector: floor hole → recess in the foot ring → channel Ø2.0 in the rib under the arm → teardrop exit → woven through 3 teardrop holes Ø1.9 in the arm blade → once under the blade at the root → hole through the rail cap → deck slot; thread before soldering (2026-11-13; closed eyelets on 2026-11-12) |
| Motor leads M2 / M3 | they run along the arm (path above) and enter the deck slot from below. The ESC pads are unchanged. |
| Deck | no rear notch; cable C slot behind the rear grommets, board (u 20.5 … 23.7, v −13.5 … −10.1) |
| Motor holders | one revolved body (2026-11-13): wall 0.85 mm from the foot to z −4.3 with a 45° top chamfer, floor 0.7 mm with the Ø3.4 lead hole, oval snap windows at ±90°; **L1 foot ring**, foot at **z −30.0** (rev R; −25.5 in §13) |
| Mass | **18.12 g** PETG (solid); 134.8 × 134.8 × **32.5 mm** (rev R) |
| Body | one smooth body generated from a parametric plan (§14): 1 shell, watertight, 0 non-manifold edges after the STL round trip |

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
  - Ground clearance with the drone landed (foot at z −30, rev R): flow cover plate **6.3 mm (T400, T1200), 5.3 mm (T800)**; PMW3901 lens 7.4 / 6.4 mm. The 9 mm pack sits 1 mm lower. (The values printed here before rev R, 11.3 / 10.3 mm, were wrong for §13: with the §13 foot the lens was 2.9 mm above the ground.)
  - **Flow board cover** (rev R, §14): the sensor side is covered, only the PMW3901 lens, the VL53L1X window and the LED are open. The flow screws become **M2 × 6 nylon** from below through the cover (head 2.0 mm under the sensor face, ≈ 3 mm in the insert).
  - 2026-11-08: the plate reaches y −11.6 with a 0.9 mm plate under the latch tongue (0.2 mm gap), lightening window
    x −10…3.2, y −5.2…17.2.
- **Lead notches.** The motor leads cross over the rail tops at |y| 12.1…13.3. The rails have 0.9 mm deep notches there.
- **T1200 note.** The front and rear corners of the 64 mm pack sit partly under the propeller discs, about 2 % of
  the disc area. This gives a slight blockage of the downwash. It is accepted for the endurance tray.

## 3. Cables

Since 2026-11-08 (§11), boards 1.0 mm.

- **A (ESC J1 → FC J2).** Both connectors are at (−10.5, +16.85) on the front edge, mouth +v, pin 1 at u −7.0: a straight
  1:1 loop. The 8 wires leave the ESC plug, bend up with a 1 mm radius right behind it, lean 2.3 mm toward the board
  corner (−u) on the way up and enter FC J2 from the front.
  - Wire **10 mm between the housings** (8 mm is the shortest that closes the loop): make all 8 wires 10 mm.
  - Clearances: propeller disc 1.37 mm (pin 1), frame 4.5 mm (the A2 top ring is open there), cover 0.5 mm.
- **B (GPS option).** GPS rev A J1 right above FC J3: short loop, 12.8 mm of wire. Make it 15 mm.
- **C (FC J4 → Flow J1).** Per the HW handoff §0.14: not straight down the right edge, where the M2 motor pads sit.
  The cable runs back along the FC right edge and drops through the deck slot behind the rear grommets as a round,
  twisted 4-wire bundle. It goes down outside the tray rail, past the front tray tab, and into Flow J1, which faces
  +X. Wire lengths between housings: 48–51 mm, make the cable 60 mm.
  - Clearances: frame 0.5 mm, tray 0.5 mm, FC USB-C plug envelope 5.4 mm, propeller disc 4.0 mm.
- **D (battery pigtail).** The ESC 1S battery pads sit across the rear-left corner (§0.20 of the HW handoff, frame
  (∓2.1, −22.5)). The two wires run along the diagonal over the rear deck tip and down behind the tray to the JST-PH
  pair at (0, −40.5, −9.6). 22 mm of route: make both wires 25 mm. Plug the pack after inserting it (the pair sits
  behind the tray, in line with the insertion path).
- The FC has no battery pads any more (HW §0.20): no battery lead goes to the FC.

## 4. Checks (mesh booleans, mm³; clearances as minimum distance between the models)

Rerun on 2026-11-13 for rev R (§14: 1.0 mm boards, RM 52, rev R core, flat-roof cover, flow board cover), configurations T400 indoor, T400 GPS,
T800 indoor, T1200 indoor. Parts: core, tray, flow board cover, battery and its insertion path, sleeves, motors, propeller discs, ESC /
FC / GPS / Flow from the ACwing_HW STEP models (every part), plug housings, J5 / J6 and both USB-C plug envelopes,
every wire, hardware (inserts, spacers, damping balls, screws), optical cones of the flow board, cover.
- **0** for every pair that is not an assembly interface (sleeve in holder, screw in insert, board on spacer, …).
- Details: `Checks/ACwing_Mech_A1_assembly_checks_<tray>_<indoor|gps>.json` and `Checks/README.md`.


## 5. Vibration (voxel FE, hex8, h 0.6 mm, PETG E 2000 MPa, lumped motors / stack / battery / flow)

2026-11-08 model: motors 4 × 4.0 g on the holders, stack + cover 15.0 g on the four bosses, battery on the tray lips
and rails (the latch tongue carries none), flow board 1.5 g on its bosses.

| Case | First mode ("saddle", diagonal motors in phase) | 2nd mode |
|---|---|---|
| A1 2026-11-01 (RM 51, closed rings) + T400, same model | 102.5 Hz | 152.9 Hz |
| A1 RM 52, A2 guard rings + T400 | 98.8 Hz | 153.5 Hz |
| A1 RM 52, A2 + T800 | 91.8 Hz | 142.7 Hz |
| A1 RM 52, A2 + T1200 | 97.6 Hz | 152.7 Hz |
| A1 RM 52, wave guards (2026-11-12) + T400 | 93.9 Hz | 141.1 Hz |
| A1 RM 52, wave guards + T800 | 87.2 Hz | 134.5 Hz |
| A1 RM 52, wave guards + T1200 | 92.8 Hz | 143.4 Hz |
| **A1 RM 52, 2026-11-13 (§13) + T400** | **91.7 Hz** | 135.8 Hz |
| A1 RM 52, 2026-11-13 + T800 | 84.9 Hz | 129.7 Hz |
| A1 RM 52, 2026-11-13 + T1200 | 90.3 Hz | 137.7 Hz |
| **A1 rev R (§14) + T400** | **90.5 Hz** | 139.7 Hz |
| A1 rev R + T800 | 76.7 Hz (tray rear) | 119.0 Hz |
| A1 rev R + T1200 | 62.7 Hz (tray rear) | 75.7 Hz |

2026-11-12: the wave guards are heavier (+2.1 g) and the first mode drops 4.9 Hz (§12). On 2026-11-08: −3.7 Hz from the 2026-11-01 design: about −1.4 Hz from the open top rings and the rest from the 1 mm longer arms
(guard-ring study, `Checks/ACwing_Mech_A1_guard_ring_study.json`). Up to 2026-11-07 the battery was lumped on the
whole tray and h was 0.8 mm; that model gave 127 Hz for the RM 51 frame, so only the differences matter.

Rev R (§14): the tray is modelled screwed to the lugs (bonded on Ø5.2 pads at z −9.0). In §13 the knee braces sat
0.6 mm from the tray rails and the voxel model (h 0.6) joined them, so the T800 / T1200 values of §13 were optimistic.
With rev R the tray rear end with the battery is free, as in the real part: on T800 / T1200 the first mode is that
overhang (the pack is mass only in the model, so this is a lower bound). The frame saddle mode is 90.5 Hz with T400.

The first modes stay inside the 60–130 Hz band that matters for the FC soft mount. Do a bench **tap test** on the
printed core with a tray fitted, and set the gyro notch from it.

## 6. Hardware per drone

| Part | Qty | Note |
|---|---|---|
| Hangtife HLTI-M2-001 insert (M2 × 3 × Ø3.0) | 4 (stack) + 4 (lugs) + 2 (flow bosses, per tray) | Ø2.8 seats |
| M2 × 5 screw, A4 or titanium | 4 | tray to core, from below |
| Damping ball M2 (QUARKZMAN), H 6.0, OD 4.9, slot Ø3.03 × 1.14 | 4 | FC soft mount for the 1.0 mm board (2.43 mm above / below) |
| Stack spacers S1 2.57 mm (S2 3.57 mm with GPS) | 4 (+4) | printed PETG |
| Stack screws M2 × 14 ISO 7380 (M2 × 25 with GPS) | 4 | titanium (recommended) or A4, from the cover top; tip 2.6 mm (GPS 3.0 mm) into the insert |
| Flow board screws M2 × 6, nylon | 2 | from below through the flow board cover (rev R; M2 × 4 without the cover) |
| Flow board cover A1 | 1 | printed PETG, 0.67 g, `02 - Mounts/Flow_Cover_A1/` |

Full list: `ACwing_Mech_A1_BoM.xlsx`.

## 7. Printing

Bambu Lab A1 (or similar), **PETG Basic or PETG HF** (not Matte) with a **0.4 mm nozzle** for core and trays (§12):
- 0.42–0.45 mm lines, Arachne walls;
- 0.12–0.16 mm layers, 3 perimeters;
- 30–40 % gyroid infill.

Sleeves in TPU 95A with the same nozzle. Print a test coupon for the Ø2.8 insert seats.

Electronics cover in translucent PLA, roof down (flat roof on the bed), no supports (2026-11-12):
see `02 - Mounts/Electronics_Cover_A1/README.md`.

- **Core:** print it upside down, with the guard top lips on the bed and a 3–5 mm brim.
  - Tree supports (build plate only, 40°) go under the deck (≈ 9 mm), the stack bosses, the motor holders and the arms
    (rev R estimate: 24 cm³ of support envelope).
  - **None in the guards and spokes** (§12, §13): block them if the slicer adds any. Bridges at 100 % fan, thick
    bridges on (the spokes bridge 21 mm from the supported holder top to the 45° gusset at the rim).
- **Mesh.** Since rev R (§14) the core STL is one closed body with 0 non-manifold edges; Bambu Studio should report no
  errors. If it does, send the message: do not let it "repair" the mesh.
- **Flow board cover:** PETG black or grey, plate on the bed, 0.12 mm layers, 100 % infill, no supports.
- **Trays:** print them upright, with the flow bosses on the bed.
  - Tree supports go under the plate, under the rear rail ends (behind the plate) and under the four outboard tabs.
  - The battery cavity stays free of supports.
- The print files in `Prints/` are already exported in these orientations.

## 8. Files (repository ACwing_Mechs)

| Path | What |
|---|---|
| `01 - Frame/Frame_A1/ACwing_Frame_A1_core.stl` | core, source mesh (assembly position) |
| `02 - Mounts/Battery_Trays_A1/ACwing_Tray_A1_T400/T800/T1200.stl` | trays, source meshes |
| `02 - Mounts/Stack_Spacers/`, `02 - Mounts/Motor_Sleeves/` | spacers S1/S2 (1.0 mm boards), TPU sleeves (RM 52) |
| `02 - Mounts/Electronics_Cover_A1/ACwing_Cover_A1_indoor/gps.stl` | electronics cover, translucent PLA, source meshes |
| `02 - Mounts/Flow_Cover_A1/ACwing_Flow_Cover_A1.stl` | flow board cover, PETG, source mesh (T400 position; rev R) |
| `03 - Assembly/ACwing_Mech_A1/ACwing_Mech_A1.FCMacro` | FreeCAD assembly; writes the print files to `00 - Docs/00 - Mech_A1_Docs/Prints/` |
| `00 - Docs/00 - Mech_A1_Docs/` | print files, BoM, STEP, renders, checks (incl. the guard-ring and print studies), weight study, this note |

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

## 11. 1.0 mm boards, A2 guard rings, RM 52, new cover (2026-11-08)

Answer to the ACwing_HW mechanical handoff §0.19–§0.20: all boards back to 1.0 mm; ESC 1S J1 at (−10.5, +16.85) on
the front edge, with FC J2 right above it; ESC USB-C at the rear-right chamfer; ESC battery pads across the rear-left
corner; no FC battery pads; FC corner LEDs.

**Guard ring.** J1 sits closer to the front-edge centre than before. Its plug back (v +22.63) lies right under the top
ring of the front-left guard (z 2.5…3.9, r 28.5…29.5), and the 8 wires of cable A have to rise through it. With a closed
top ring the frame needed RM 53 again.

New guard design **A2** (proposed by Andrea Cirillo), on all four rings:
- the top ring stays only on the outer half (φ 90…270°, φ = 0 toward the frame centre);
- from φ ±90° it ramps down and lands on the bottom ring at φ ±32°: on the side of the body there is only the bottom
  ring, below the stack;
- the inner ribs (±30°) and the top bridges go; ribs at ±90° and ±150° stay;
- ramp section 1.2 × 1.7 mm (A2; 1.0 × 1.4 like the top ring makes the end of the top ring 44 % softer, see below).

The inner arc of the guard faces the body, so it does not protect anything. Around the outer half nothing changes.

| Variant (guard-ring study, RM 51, core + T400) | Core | 1st mode | 2nd mode | Side push 5 N at 90° | Outer push 5 N at 180° |
|---|---|---|---|---|---|
| Closed rings (A1) | 15.44 g | 118.5 Hz | 152.3 Hz | 9.0 mm | 9.0 mm |
| Open, ramps 1.0 × 1.4 | −0.34 g | 116.7 Hz | 145.0 Hz | +44 % | +0.5 % |
| Open, steep ramps, top bridges kept | −0.22 g | 117.4 Hz | 147.8 Hz | +7 % | 0 % |
| **A2: open, ramps 1.2 × 1.7** | **−0.17 g** | **117.1 Hz** | 146.0 Hz | **−6 %** | **−3 %** |

(FE as in §5 with the battery on the whole tray; static loads on the front-left ring with the stack bosses clamped.
Raw data: `Checks/ACwing_Mech_A1_guard_ring_study.json`.)

**RM 52.** With the open ring the guard no longer limits cable A; the propeller disc does. At RM 51 the wire of pin 1
would pass about 0.4 mm from the propeller tip circle. At **RM 52** it is **1.37 mm**. Frame 132.9 mm.

**How the core was made.** The core is the 2026-11-01 mesh with:
- the old rings removed, the motor pods (holder, legs, spokes, outer arm) moved 1 mm out along their diagonals, the
  gaps closed by sweeping the cut faces (arms, knee braces, deck edge);
- the A2 rings and the bottom bridges added at RM 52;
- the motor holder wall 0.2 mm thinner where nothing is attached;
- the cable C slot of 2026-11-07 (board u 20.5…23.7, v −13.5…−10.1);
- the battery envelope kept free (T1200 pack + margins).

Mass 15.55 g. The old bottom bridges stay merged with the new ones, so the side bridges are 2.2 mm wide.

**Stack, 1.0 mm boards.**

| Item | z | Note |
|---|---|---|
| ESC 1S | −2.0 … −1.0 | on the bosses |
| S1 spacer | −1.0 … 1.57 | 2.57 mm |
| Damping ball (QUARKZMAN M2) | 1.57 … 7.43 | H 6.0, slot Ø3.03 × 1.14, 2.43 mm above / below the board |
| FC | 4.0 … 5.0 | 5.0 mm above the ESC |
| S2 spacer (GPS) | 7.43 … 11.0 | 3.57 mm |
| GPS | 11.0 … 12.0 | SAM-M10Q top 18.2 |
| Cover, indoor | 6.2 … 12.0 (logo 12.6) | M2 × 14, head seat 9.4, tip −4.6 (2.6 mm in the insert) |
| Cover, GPS | 6.2 … 21.95 (logo 22.55) | M2 × 25, head seat 20.0, tip −5.0 (3.0 mm in the insert) |

**Cover.** Redrawn after the frame:
- the plan is the 52 mm square with **concave sides** 28 mm from the motor axes (0.5 mm outside the propeller discs),
  like the deck between the rings;
- crowned roof (+0.7 mm), 3 mm roof fillet, 0.8 mm walls;
- **wavy skirt**: low at the corners (z 6.2) and high at the side centres (z 9.0; 17.0 on the GPS cover), the same
  smoothstep curve as the guard ramps;
- the front and rear FC corner LEDs show under the skirt; the right corner has the notch for the FC USB-C plug (the ESC
  USB-C plug passes under the cover). One USB plug at a time, as the HW handoff says;
- indoor 3.0 g, GPS 4.5 g.

**Answers to the HW handoff §0.19 / §0.20 "what we need back".**
- Guard ring with ESC J1 at u −10.5: A2 rings and RM 52 (above).
- Cable A: straight 1:1 loop, 10 mm of wire.
- Spacers, balls and screws for 1.0 mm boards: table above; flow screws M2 × 6 nylon with the flow board cover (rev R).
- Both USB-C ports at +X: FC plug through the cover notch, ESC plug under the cover; frame clearance 4.0 / 1.1 mm.
- Corner LEDs: visible under the cover skirt at the front and rear corners.
- Battery lead: from the ESC corner pads over the rear deck tip, down behind the tray (cable D).

**Mass:** drone T400 indoor ≈ 67.4 g (−3.7 g from 2026-11-07: boards −4.2 g, core +0.6 g, cover +0.2 g, tray
−0.1 g, cables −0.2 g). See `ACwing_Mech_A1_weight_study.md`.

**For HW rev B:** keep the low connectors near the board corners; the A2 rings leave room above the board edges, but the
propeller disc is 27.5 mm from each motor axis.

## 12. Print-first redesign: wave guards, closed wire eyelets, flat-roof cover (2026-11-12)

**Why.** The first print of the 2026-11-08 core (Bambu Lab A1, Bambu PETG Matte, upside down) failed: the top rings
of the A2 guards hung over air and needed supports, and they broke when the supports were removed. Printed masses: core
13 g, tray T400 4 g. The rear side has no bracket between the arms and the deck on purpose: it is the insertion path of
the battery. Goals of the redesign, for a Bambu Lab A1 with a 0.4 mm nozzle: no supports inside the guards, the same
or better stiffness, the same look. Three proposals were compared; the adopted guard is the wave proposed by Andrea
Cirillo.

**Wave guards** (all four, φ = 0 toward the frame centre):
- **wall**: one 0.86 mm shell (2 lines), from the lower rim (z −6.45) to the top lip (z 2.5), **bulged 1.2 mm outward**
  with a sine meridian (at most 32° from vertical, so it prints without support). The bulge fades to a straight wall for
  |φ| 75 → 55° (clearance to the ESC USB-C plug);
- **top lip** 1.2 × 0.8 mm (r 28.6…29.8): the first layer on the bed; **lower rim** 1.28 × 1.6 mm, 360°, with the
  bottom bridges to the neighbouring guards;
- **S ribbon**, 2.2 mm tall, between them: it rests on the lower rim (low plateaus, one on the 180° spoke) and merges
  into the top lip (high plateaus), with smoothstep flanks like the cover skirt. Period 19.3 mm: 7 upper and 8 lower
  windows per guard;
- **print rule**: with the core upside down every window sill is either a 45° slope or a straight **6.2 mm bridge**
  anchored at both ends; small 45° gussets at the foot of the lower windows shorten their bridge from 12 to 6.2 mm;
- **open toward the body** for |φ| < 46°: the last flank of the ribbon is the ramp, straightened to 45°, with a
  **1.2 mm deep rim** (r 28.5…29.7). Only the lower rim stays above the board edges, as with the A2 rings;
- **spokes**: straight, 1.28 × 2.5 mm at the level of the lower rim, printed as 18.6 mm bridges; the motor-holder
  collars are raised to meet them.

![Front-left guard with cable A](Renders/ACwing_Mech_A1_guard_cable_A.png)

**Closed wire eyelets.** The 8520 motors have no connector, so the open wire clips are closed: 12 eyelets, 3 per arm,
each with a 45° roof from the arm side to the clip finger (hole about 1.6 mm). Thread both leads through them before
soldering the leads to the ESC pads.

**Cover.** Flat roof with a 1.8 mm 45° chamfer, logo engraved 0.4 mm; it prints roof-down with no support (indoor
2.79 g, GPS 4.27 g). Concave sides, wavy skirt, posts and screws unchanged.

**Results** (FE as in §5; statics: 5 N on a 1.6 mm patch of the front-left guard, stack bosses clamped; supports:
45° overhang analysis of the core upside down, straight strips up to 2.6 × 22 mm anchored at both ends count as
bridges). Raw data: `Checks/ACwing_Mech_A1_print_study.json`.

| | A2 (2026-11-08) | **Wave (2026-11-12)** |
|---|---|---|
| Core, solid | 15.55 g | **17.63 g** |
| Frame | 132.9 × 132.9 × 38.0 mm | 134.8 × 134.8 × 36.4 mm |
| First / second mode, T400 | 98.8 / 153.5 Hz | **93.9 / 141.1 Hz** |
| First mode, T800 / T1200 | 91.8 / 97.6 Hz | 87.2 / 92.8 Hz |
| Outer push 5 N (φ 180) | 7.96 mm, 25.8 MPa | **3.57 mm, 13.0 MPa** |
| Side push 5 N (φ 90) | 7.89 mm | 4.99 mm |
| Vertical 5 N at φ 90 / φ 60 | 13.65 / 3.87 mm | 9.06 / 3.52 mm |
| Bottom push 5 N | 1.60 mm | 0.97 mm |
| Push 5 N on the ramp | 0.16 mm | 1.97 mm |
| Motor thrust 2 N | 1.04 mm | 1.07 mm |
| Support envelope in the guards + spokes | 2.9 cm³ | **0.06 cm³** |
| Support envelope, whole core | 28.2 cm³ | 20.8 cm³ |

The guards are stiffer than the A2 rings everywhere (×2.2 at the outer side, ×1.1 at φ 60) except at the ramp (a 5 N push bends it less than 2 mm). The
first mode drops 4.9 Hz with the heavier guards and stays in the 60–130 Hz band of the FC soft mount: do the tap test.
Proposal P1 (band guard with pointed arches and a 45° flare, 18.17 g) was stiffer at the side (3.57 mm) but heavier;
see the weight study §2b.

**Checks** (§4, rerun 2026-11-12, T400 indoor / GPS, T800, T1200): 0 unexpected overlaps. Clearances: cable A – propeller disc 1.37 mm, – frame 4.55 mm, – cover 0.51 mm; cable C – frame 0.51 mm, – tray 0.47–0.53 mm; cable D – frame 0.48 mm; frame – propeller disc 1.00 mm; FC USB-C plug – frame 1.20 mm, ESC USB-C plug – frame 0.77 mm (the bulge fades to a straight wall near the plugs); cover – FC 1.36 mm.

**Printing (Bambu Lab A1, 0.4 mm nozzle).** PETG Basic or PETG HF, not Matte. Core upside down as exported, guard top
lips on the plate, textured PEI, 3–5 mm brim; tree supports on the build plate only (40°) under the deck, holders and
arms; none in the guards and spokes (block them if the slicer adds any); bridges at 100 % fan with thick bridges on.
Full settings in the `Print` sheet of the BoM.

**Mass.** Drone T400 indoor ≈ 69.3 g (+1.9 g: core +2.08 g, cover −0.23 g), T/W 2.02. The printed core should weigh
about 15 g.

## 13. Frame fixes: one-piece motor holders, foot ring and wire channel, aligned spokes (2026-11-13)

**Why.** Review of the 2026-11-12 core in the slicer (Andrea Cirillo, 6 points):
1. the collar of the motor holder (the part the spokes attach to, z −9.6 … −4.6) was a separate body: it stopped
   0.1 mm above the old holder (2026-11-07), so the two only touched along a few edges (3 non-manifold edges and
   inverted faces in the slicer). The two parts also had different shapes (plain ring on a beaded holder);
2. the landing loop under each holder was too bulky;
3. the spokes hung 2.5 mm below the lower rim and their 45° ends stuck out under it; the bridges between the guards
   (two old rods) sat on another level;
4. the wire eyelets were square boxes on the arm;
5. the arm root at the deck showed the seam of the 2026-11-08 mesh surgery (motor pod cut at r 28.6 and moved 1 mm):
   a vertical step with stair-stepped faces and a pit;
6. small bumps on the inner face of the guards: leftovers of the A2 ribs.

**Motor holder** (one revolved body, all four motors):
- wall r 4.9 … 5.75 mm (0.85 mm, 2 lines) from the foot to z −4.3, **45° chamfer** 0.6 mm at the top (the cover
  motif); the TPU sleeve and the motor fit as before (sleeve z −23.0 … −2.2, snap bumps in the windows);
- floor z −24.0 … −23.3 with the Ø3.4 mm hole for the motor leads; the two **oval windows** at ±90° (4.9 × 7.5 mm,
  z −21.1 … −13.6) for the snap bumps of the sleeve, as before;
- the old bead, the collar and the stubs of the old spokes are gone (the "notch" was one of these stubs).

**Landing gear: L1 foot ring.** The loop (0.46 g for four) is replaced by a foot ring r 4.6 … 5.75 mm, 1.5 mm below
the floor, with a 45° outer chamfer. The drone stands on the four rings; the frame is **28.0 mm** tall (36.4 mm before).
The battery pack stays ≥ 8.9 mm above the ground.

**Motor leads.** The leads leave the motor through the floor hole into the recess inside the foot ring (protected by
the ring), go through a 2 × 1 mm tunnel into a **closed channel** (Ø2.0 mm) in a tapered rib under the arm, and come out
under the arm through a teardrop hole on the side of the leads. Then they weave through **3 teardrop holes** (Ø1.9 mm)
in the 2.2 mm arm blade (ρ 11, 16, 20.5 mm from the motor axis) and go up through the deck slot to the ESC pads.
Thread them before soldering.

**Spokes, rims, bridges.** Spokes 1.28 mm wide, 2.5 mm deep, **top flush with the lower rim** (z −4.85), 45° gusset on
the holder underneath, 45° under the rim and a 45° rise to the guard wall at the rim end (no stub outside the guard).
The bridges between neighbouring guards have the rim section (1.28 × 1.6 mm) on the line between the motor axes, in
line with the ±45° spokes: spoke – rim – bridge – rim – spoke read as one straight member.

**Arm root.** The zone ρ 25.5 … 34.5 mm, |τ| ≤ 12.5 mm around each root was remeshed on a 0.06 mm voxel grid: under
the deck the arm bulb is lofted into the strut and the tray lug (ρ 25.2 → 32.8 mm), the stair steps of the old sweeps
are smoothed (0.3 mm), the lower rim is kept exact and the deck wire slot is re-cut.

![Motor holder, foot ring and wire channel](Renders/ACwing_Mech_A1_holder_foot.png)

**Results** (FE as in §5, statics as in §12, supports as in §12). Raw data: `Checks/ACwing_Mech_A1_print_study.json`.

| | Wave 2026-11-12 | **2026-11-13** |
|---|---|---|
| Core, solid | 17.63 g | **16.67 g** |
| Frame | 134.8 × 134.8 × 36.4 mm | 134.8 × 134.8 × 28.0 mm |
| First / second mode, T400 | 93.9 / 141.1 Hz | **91.7 / 135.8 Hz** |
| First mode, T800 / T1200 | 87.2 / 92.8 Hz | 84.9 / 90.3 Hz |
| Outer push 5 N (φ 180) | 3.57 mm, 13.0 MPa | **4.53 mm, 14.1 MPa** |
| Side push 5 N (φ 90) | 4.99 mm | 5.63 mm |
| Vertical 5 N at φ 90 / φ 60 | 9.06 / 3.52 mm | 10.33 / 4.25 mm |
| Bottom push 5 N | 0.96 mm | 0.87 mm |
| Push 5 N on the ramp | 1.97 mm | 2.30 mm |
| Motor thrust 2 N | 1.07 mm | 1.15 mm |
| Support envelope, guards + spokes | 0.06 cm³ | 0.04 cm³ |
| Support envelope, whole core | 20.8 cm³ | 20.2 cm³ |

**Checks** (§4, rerun 2026-11-13, T400 indoor / GPS, T800, T1200): 0 unexpected overlaps; clearances as in §12 (cable A – propeller disc 1.37 mm, frame – propeller disc 1.00 mm, FC / ESC USB-C plug – frame 1.20 / 0.77 mm), cable D – frame 1.10 mm (0.48 mm before, after the arm-root remesh). The holder keeps the sleeve and motor positions (sleeve z −23.0 … −2.2).

The frame is 0.96 g lighter than on 2026-11-12. The guards are a little softer (the spokes are 2.5 mm deep along their whole length, where the old ones were 4.9 mm deep at the collar, and the bridges are one bar instead of two rods), still 1.4–1.8 times stiffer than the A2 rings at the side and the outer point; the first mode drops 2.2 Hz and stays in the 60–130 Hz band. Peak stress stays under 25 MPa for every 5 N case.

**Mesh.** One body, watertight, 0 non-manifold edges, consistent normals (checked before export).

## 14. Rev R: frame core redrawn as one parametric body, flow board cover (2026-11-13)

**Why.** Review of the §13 core (Andrea Cirillo, 5 images): the core still showed the leftovers of six rounds of mesh
booleans on the 2026-11-07 mesh: cut remnants of the old eyelets on the arms, stubs of old spokes and bridges at the
rims, the blocks of the old deck notch, lumps where the rims meet the deck, and 41 non-manifold edges in Bambu Studio.
The body read as separate pieces put together, not as one part.

**How.** The core is no longer edited: it is generated from scratch by one script (`frameR.py`, kept with the design
files), **plan first, then 3D**:
1. **Plan** (2D, exact): deck = 64 mm square minus the four guard discs (r 28.6 around each motor), tips rounded R3;
   stack window, lead slots, cable C slot; stack bosses on the 20 × 20 diamond; two side rails (x ±20); the four arms on
   the diagonals, from the motor axis to the rail end (±20, ±20).
2. **Central body** (deck, bosses, deck ribs, rails, tray lugs, arms, holder proxies) as one signed-distance field with
   smooth union (0.8 mm blend radius) on a 0.1 mm grid: every branch grows out of the next one with a fillet, there is
   no seam and no face of an older mesh.
3. **Exact parts** added to it: motor holders (one revolved body, as in §13), the rib with the closed wire channel,
   spokes, wave guards, top lips, lower rims and bridges (same shapes as §12–§13).
4. **Voids** cut once, at the end: holder bores and windows, wire channel and teardrop holes, insert seats, stack window,
   slots, battery envelope.

![Plan of the rev R core](Renders/ACwing_Mech_A1R_plan.png)

**What changed in the shape.**
- **Ring beam under the stack.** The stack bosses are tied to the rails by **deck ribs** (1.6 mm wide, top z −4.1,
  0.96 mm under the lowest ESC part above them): from each front / rear boss to both rails, from each side boss straight
  to its rail. The **rails** rise to z −4.1 where they are outside the propeller discs (|y| ≤ 11), flare to 6 mm wide
  toward the arm roots and end in a round cap 2.5 mm past the root. Deck ribs + rails form one closed frame that carries
  the arms; the old knee braces and side spars are gone.
- **Arms.** 2.2 mm blades, top z −6.2 → −5.6, bottom z −14.75 → −15.0 (root), blended into the holder and into the
  rail cap. 3 teardrop wire holes (Ø1.9) in each blade, a 4th through the rail cap (z −10.8) on the way to the deck slot.
- **Tray lugs.** Ø6 columns from the face at z −9.0 up into the deck, hidden under the deck top (no bumps on the deck);
  the faces are planed flat at z −9.0 (the blend would otherwise bulge 0.2 mm into the tray tabs).
- **Holder foot** at **z −30.0** (−25.5 before): the frame is **32.5 mm** tall (28.0 mm in §13). The §13 foot left the
  flow board lens only 2.9 mm above the ground: this was missed in §13. Now the flow cover plate is 6.3 mm above the
  ground (T400 / T1200), 5.3 mm (T800).
- **Mesh for the slicer.** The guard band had point contacts in its 2D outline (window corner on the band edge) that
  gave zero-length edges, and some voids and rims shared faces with other parts: these gave the Bambu Studio errors.
  Fixed at the source (outline closed by 0.02 mm, no shared faces, holder bore cut 0.02 mm outside the 128-gon). The STL
  is checked after the float32 round trip: **1 body, watertight, 0 non-manifold edges**, consistent normals.

**Flow board cover (new part).** A 0.67 g PETG cover over the sensor side of Flow rev A: 0.8 mm plate 0.3 mm under the
PMW3901, 0.8 mm walls on three sides up to the board back; open only for the PMW3901 lens (Ø6), the VL53L1X window
(3.0 × 5.4) and the status LED (Ø1.2); connector edge (+X) open for J1 / J2 and cable C. It is held by the two flow
screws, now **M2 × 6 nylon** from below, heads recessed in the cover standoffs. One part for every tray. Details:
`02 - Mounts/Flow_Cover_A1/README.md`.

![Flow board cover](Renders/ACwing_Flow_cover_sketch.png)

![Underside, T400, flow board cover](Renders/ACwing_Mech_A1_T400_below_flow_cover.png)

**Motor-lead route (rev R, as in the renders and in `03 - Assembly/ACwing_Mech_A1/reference/ACwing_Ref_motor_leads_x4.stl`).**
Two wires per motor (Ø0.7 mm with insulation), 83–85 mm from the motor to the ESC pads:
1. out of the motor bottom, through the floor hole (Ø1.7) into the recess inside the foot ring;
2. through the tunnel (2 × 1 mm) into the closed channel of the rib, up to the teardrop exit (z −16.2) on the lead side;
3. woven through the 3 teardrop holes of the arm blade (in and out on alternate sides);
4. after the 3rd hole the wires are on the side away from the rail: they wrap once under the blade at the arm root;
5. through the hole in the rail cap (from outside, z −10.8), up through the deck slot, around the ESC board edge to the pads.
The route clears the core, the boards, plugs, cables and cover (0 mm³); it touches only the motor (where the wires leave it) and the ESC pads.

![Motor leads along the arm](Renders/ACwing_Mech_A1_motor_leads_arm.png)

**Results** (FE as in §5, statics as in §12, supports as in §12).

| | §13 (2026-11-13 morning) | **Rev R** |
|---|---|---|
| Core, solid | 16.67 g | **18.12 g** |
| Frame | 134.8 × 134.8 × 28.0 mm | 134.8 × 134.8 × 32.5 mm |
| First / second mode, T400 | 91.7 / 135.8 Hz | **90.5 / 139.7 Hz** |
| First mode, T800 / T1200 | 84.9 / 90.3 Hz* | 76.7 / 62.7 Hz* |
| Outer push 5 N (φ 180) | 4.53 mm | **4.24 mm** |
| Side push 5 N (φ 90) | 5.63 mm | 5.29 mm |
| Vertical 5 N at φ 90 / φ 60 | 10.33 / 4.25 mm | 9.18 / 3.84 mm |
| Bottom push 5 N | 0.87 mm | 0.78 mm |
| Push 5 N on the ramp | 2.30 mm | 1.86 mm |
| Motor thrust 2 N | 1.15 mm | **1.00 mm** |
| Support envelope, guards + spokes | 0.04 cm³ | 0.14 cm³ |
| Support envelope, whole core | 20.2 cm³ | 24.2 cm³ |

\* Not the same thing. In §13 the knee braces sat 0.6 mm from the tray rails and the voxel model (h 0.6 mm) joined
them, so the core held the rear of the tray: those values were optimistic. Rev R leaves 1.36 mm there and the tray is
modelled screwed on its four lugs (bonded on Ø5.2 pads at z −9.0). On T800 / T1200 the first mode is now the rear
overhang of the tray with the battery (the frame saddle follows at 119 / 91 Hz); the pack is mass only in the model,
so these are lower bounds. Measure them with a tap test on the printed core + tray + pack, and set the gyro notch from it.

The core is 1.45 g heavier than in §13 (ring beam, rail caps, 4.5 mm longer holders) and stiffer in every static case
(motor thrust −13 %, outer push −6 %, vertical φ 90 −11 %, ramp −19 %). Peak stress stays under 19 MPa for every 5 N case.

**Checks** (§4, rerun on rev R with the flow cover, T400 indoor / GPS, T800, T1200): **0 unexpected overlaps**.
- Unchanged: cable A – propeller disc 1.37 mm, frame – propeller disc 1.00 mm, FC / ESC USB-C plug – frame 1.20 / 0.77 mm,
  cable C – frame 0.51 mm, cable D – frame 1.10 mm.
- Battery – frame 0.47 mm (T400), 0.24 mm (T800, T1200) (0.18 / 0.03 / 0.02 mm in §13).
- Deck ribs – ESC parts 0.96 mm; tray tabs on flat lug faces (0 overlap).
- Flow cover: optical cones 0.80 mm from the openings, Flow J1 plug 1.77 mm, cable C 3.9 mm, tray 0.40 mm.

**Files.** Core: `01 - Frame/Frame_A1/ACwing_Frame_A1_core.stl` (source), `Prints/ACwing_Mech_A1_01_Frame_core_PETG.stl`
(upside down), `STEP/Parts/ACwing_Frame_A1_core.step` (80k facets, reference only: print from the STL). Flow cover:
`02 - Mounts/Flow_Cover_A1/`, `Prints/ACwing_Mech_A1_06_Flow_cover_PETG.stl`, `STEP/Parts/ACwing_Flow_Cover_A1.step`.
The assembly STEP files with hardware and cables (`STEP/*_hardware_cables.step`) are rewritten with the M2 × 6 flow
screws.
