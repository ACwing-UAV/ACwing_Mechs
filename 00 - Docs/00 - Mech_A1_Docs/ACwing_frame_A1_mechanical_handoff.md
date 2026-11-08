# ACwing frame A1 – core + interchangeable battery trays (Mech A1)

> **Revisions.** A1 is the first released mechanics of the 1S mini drone. Earlier frames were **preliminary drafts**:
> internal design iterations, never released. The boards named here are the rev A release (FC rev A, ESC 1S rev A,
> GPS rev A, Flow rev A).

**Author:** Andrea Cirillo (ACwing). **From:** mechanical / frame design. **To:** electronics design and build.
**Date:** 2026-11-01, **updated 2026-11-06** (§9: rev A stack with 1.6 mm boards, ACwing_Mechs issue #2; electronics cover)
**2026-11-07** (§10: ESC J1 on the front edge then toward the front corner, cable C and flow board per the HW handoff §0.14–§0.17,
motors back at RM 51; weight study) and **2026-11-08** (§11: boards back to 1.0 mm, ESC J1 at (−10.5, +16.85) per the HW
handoff §0.19–§0.20; new **A2 guard rings**, motors at **RM 52**, new electronics cover).
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
| T400 | 400 mAh, 11.5 g | 20 × 40 × 8 | 3.30 g | ≈ 67.4 g | 2.08 | × 0.80 | 98.8 Hz** |
| T800 | 800 mAh, ≈ 22 g | 25 × 45 × 9 | 3.55 g | ≈ 78.2 g | 1.79 | × 1.28 | 91.8 Hz** |
| T1200 | 1200 mAh, ≈ 30 g | 30 × 64 × 8 | 4.04 g | ≈ 86.6 g | 1.62 | × 1.64 | 97.6 Hz** |

\* Indoor configuration (ESC 1S rev A + FC rev A + Flow rev A, no GPS), boards 1.0 mm, electronics cover (3.0 g),
2026-11-08. Mass budget and lightening options: `ACwing_Mech_A1_weight_study.md`.
\** FE model of 2026-11-08 (§5, battery lumped on the tray lips): the A1 design of 2026-11-01 gives 102.5 Hz in the
same model, so these values are not comparable with the 127 Hz of the older model.
- Thrust ≈ 140 g.
- Hover power ∝ m^1.5, with the same usable fraction of the capacity.
- The reference is the preliminary draft (battery bay fused to the frame) with the 400 mAh pack, ≈ 58 g.

Cost of interchangeability, compared with the preliminary draft (frame 15.55 g):
- core 15.55 g (RM 52, A2 guard rings, 2026-11-08; 14.95 g at RM 51 with the closed rings);
- tray as in the table above;
- 4 brass inserts + 4 M2 × 5 A4 screws ≈ 1.2 g (estimate, see the BoM; ≈ 0.85 g with titanium screws).

Net mass overhead: **+4.5 g (T400), +4.7 g (T800), +5.2 g (T1200)**.

## 1. Core A1 (changes from the preliminary draft)

| Item | A1 |
|---|---|
| Battery bay, latch, flow plate | not on the frame: they are on the trays |
| Battery envelope | box 31.2 × 66 × 9.9 mm under the deck (top at z −6.7, centred, open to the rear for insertion). Nothing of the core enters it. Blend fillets of ring and arm roots are trimmed there. |
| Tray lugs | 4 bosses Ø6 from the deck down to a flat face at **z −9.0**, at frame **(±20.0, −6.0)** and **(±20.0, +3.5)**. Each has a Hangtife HLTI-M2-001 insert in a Ø2.8 seat, open downwards. |
| Knee braces | blade braces Ø2.4 × 3 mm from each arm (radius 25, z −15) to the nearest lug. They give back the stiffness the bay rails provided in the preliminary draft. |
| Side spars | 3 mm wide spar on each side, joining the two lugs of that side to the deck |
| Motors | at **RM 52** from the frame centre (frame (±36.77, ±36.77)) since 2026-11-08 (§11); RM 51 before |
| Guard rings | **A2** (2026-11-08, §11): bottom ring 360°; top ring only on the outer half (φ 90…270°, φ = 0 toward the frame centre); from φ ±90° it ramps down to the bottom ring at φ ±32° (ramps 1.2 × 1.7 mm); ribs at ±90° and ±150°; bottom bridges between neighbouring rings, no top bridges |
| Arms | start at radius 23.5, 10 / 3.5 mm deep |
| Rear spokes | the inner spokes of the rear rings are at 75° / −75°, clear of the T1200 corners |
| Motor leads M2 / M3 | they leave the holder on the other side of the arm (`LEAD_SIDE`) and enter the deck slot from below. Lead z under the deck is −8.65. The ESC pads are unchanged. |
| Deck | no rear notch; cable C slot behind the rear grommets, board (u 20.5 … 23.7, v −13.5 … −10.1) |
| Motor holders | outer wall 0.2 mm thinner where nothing is attached (2026-11-08); floor 1.2 mm |
| Mass | 15.55 g PETG; 132.9 × 132.9 × 38.0 mm |

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
  - Lens tip above the ground with the drone landed, 1.0 mm board: **11.3 mm (T400, T1200), 10.3 mm (T800)**. The 9 mm pack sits 1 mm lower.
  - The flow board screws stay M2 × 4 nylon (1.0 mm board + 3.0 mm in the insert).
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

Rerun on 2026-11-08 (§11: 1.0 mm boards, RM 52, A2 guard rings, new cover), configurations T400 indoor, T400 GPS,
T800 indoor, T1200 indoor. Parts: core, tray, battery and its insertion path, sleeves, motors, propeller discs, ESC /
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
| **A1 RM 52, A2 guard rings + T400** | **98.8 Hz** | 153.5 Hz |
| A1 RM 52, A2 + T800 | 91.8 Hz | 142.7 Hz |
| A1 RM 52, A2 + T1200 | 97.6 Hz | 152.7 Hz |

−3.7 Hz from the 2026-11-01 design: about −1.4 Hz from the open top rings and the rest from the 1 mm longer arms
(guard-ring study, `Checks/ACwing_Mech_A1_guard_ring_study.json`). Up to 2026-11-07 the battery was lumped on the
whole tray and h was 0.8 mm; that model gave 127 Hz for the RM 51 frame, so only the differences matter.

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
| Flow board screws M2 × 4, nylon | 2 | from the sensor side |

Full list: `ACwing_Mech_A1_BoM.xlsx`.

## 7. Printing

PETG with a **0.4 mm nozzle** for core and trays:
- 0.42–0.45 mm lines, Arachne walls;
- 0.12–0.16 mm layers, 3 perimeters;
- 30–40 % gyroid infill.

Sleeves in TPU 95A with the same nozzle. Print a test coupon for the Ø2.8 insert seats.

Electronics cover in translucent PLA, upright (skirt corners on the bed, logo up), tree supports under the roof and the skirt arches:
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
| `02 - Mounts/Stack_Spacers/`, `02 - Mounts/Motor_Sleeves/` | spacers S1/S2 (1.0 mm boards), TPU sleeves (RM 52) |
| `02 - Mounts/Electronics_Cover_A1/ACwing_Cover_A1_indoor/gps.stl` | electronics cover, translucent PLA, source meshes |
| `03 - Assembly/ACwing_Mech_A1/ACwing_Mech_A1.FCMacro` | FreeCAD assembly; writes the print files to `00 - Docs/00 - Mech_A1_Docs/Prints/` |
| `00 - Docs/00 - Mech_A1_Docs/` | print files, BoM, STEP, renders, checks (incl. the guard-ring study), weight study, this note |

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

![Front-left A2 guard with cable A](Renders/ACwing_Mech_A1_guard_A2_cable_A.png)

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
- Spacers, balls and screws for 1.0 mm boards: table above; flow screws M2 × 4 nylon.
- Both USB-C ports at +X: FC plug through the cover notch, ESC plug under the cover; frame clearance 4.0 / 1.1 mm.
- Corner LEDs: visible under the cover skirt at the front and rear corners.
- Battery lead: from the ESC corner pads over the rear deck tip, down behind the tray (cable D).

**Mass:** drone T400 indoor ≈ 67.4 g (−3.7 g from 2026-11-07: boards −4.2 g, core +0.6 g, cover +0.2 g, tray
−0.1 g, cables −0.2 g). See `ACwing_Mech_A1_weight_study.md`.

**For HW rev B:** keep the low connectors near the board corners; the A2 rings leave room above the board edges, but the
propeller disc is 27.5 mm from each motor axis.
