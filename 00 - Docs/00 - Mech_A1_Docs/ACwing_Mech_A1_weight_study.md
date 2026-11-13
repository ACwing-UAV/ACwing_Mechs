# Mech A1 – weight study (2026-11-07, updated 2026-11-08, 2026-11-12 and 2026-11-13)

Mass budget of the drone and a list of what could make the structure lighter. Since 2026-11-12: boards 1.0 mm, frame
at RM 52 with the print-first wave guards and one-piece motor holders (foot ring, no landing loop), flat-roof cover (§2b). Each frame option was checked with a voxel FE model of core + T400 tray.
Scripts and raw results: `Checks/ACwing_Mech_A1_fe_weight_study.json` (2026-11-07) and
`Checks/ACwing_Mech_A1_guard_ring_study.json` (2026-11-08), `Checks/ACwing_Mech_A1_print_study.json` (2026-11-12).

## 1. Mass budget, indoor, T400 (2026-11-13)

| Group | Part | Mass (g) | Basis |
|---|---|---|---|
| Structure | Frame A1 core (RM 52, wave guards, one-piece holders) | 16.67 | mesh × 1.27 g/cm³ |
| | Tray T400 | 3.30 | mesh |
| | Electronics cover, indoor (flat roof) | 2.79 | mesh × 1.24 g/cm³ |
| | Motor sleeves TPU ×4 | 2.18 | mesh × 1.21 g/cm³ |
| | Spacers S1 ×4 | 0.15 | volume |
| | Inserts ×10, damping balls ×4, screws (stack Ti M2 × 14, tray A4 M2 × 5, flow nylon) | 3.2 | estimates |
| | **Structure total** | **28.3** | **41 %** |
| Propulsion | Motors 8520 ×4 | 14.4 | |
| | Propellers 55 mm ×4 | ≈ 2.0 | estimate, weigh |
| Electronics | FC rev A, 1.0 mm, with parts | ≈ 5.0 | HW handoff (−1.8 g from 1.6 mm) |
| | ESC 1S rev A, 1.0 mm, with parts | ≈ 4.8 | HW handoff |
| | Flow rev A, 1.0 mm | ≈ 1.5 | HW handoff |
| | Cables A, C, pigtail | ≈ 0.8 | estimate (cable A now 10 mm) |
| Battery | 1S 400 mAh | 11.5 | |
| | **Drone** | **≈ 68.3** | T/W 2.05 with 140 g of thrust |

Against 2026-11-12 (69.3 g): core −0.96 g (landing loops −0.46 g, one-piece holders, arm-root cleanup) → **−1.0 g**.
Against 2026-11-08 (67.4 g): core +1.12 g (print-first guards), cover −0.23 g (flat roof) → **+0.9 g**.
Against 2026-11-07 (71.1 g): boards −4.2 g, core +2.7 g, cover 0 g, tray −0.1 g, cables −0.2 g → **−1.8 g**.

The 2026-11-08 core was 0.6 g heavier than the RM 51 core of 2026-11-07:
- 1 mm longer arms and bridges, and the deck edges swept to the new ring position: about +0.35 g;
- the old bottom bridges stay merged with the new ones: about +0.1 g;
- the A2 rings: −0.17 g (ramps 1.2 × 1.7 instead of the closed top ring, inner ribs and top bridges removed);
- the motor holders could only be thinned where nothing is attached: −0.23 g (−0.51 g in the 2026-11-07 design).

### Core breakdown, 2026-11-07 (RM 53 voxels; still indicative)

Where the core mass sits (voxel breakdown at RM 53, groups overlap slightly in the blends; at RM 51 the arms are 2 mm
shorter, −0.2 g):

| Group | Mass (g) | Share |
|---|---|---|
| Deck + stack bosses | 3.46 | 22 % |
| Motor holders | 2.25* | 15 % |
| Guard rings (top + bottom) | 2.62 | 17 % |
| Arms | 2.50 | 16 % |
| Spokes | 1.70 | 11 % |
| Tray lugs + knee braces + side spars | 1.46 | 9 % |
| Motor legs | 0.42 | 3 % |
| Guard ribs | 0.28 | 2 % |
| Ring bridges | 0.20 | 1 % |
| Clips | 0.13 | 1 % |

\* After the 0.8 mm wall change (2.76 g before).

## 2. Guard rings A2 (2026-11-08)

| Variant (RM 51, core + T400, FE h 0.6) | Core | 1st mode | 2nd mode |
|---|---|---|---|
| Closed rings (A1) | 15.44 g | 118.5 Hz | 152.3 Hz |
| Open top ring, ramps 1.0 × 1.4 | −0.34 g | 116.7 Hz | 145.0 Hz |
| **A2: open, ramps 1.2 × 1.7 (adopted)** | **−0.17 g** | **117.1 Hz** | 146.0 Hz |

The inner arc of the top ring carries little of the first mode: opening it costs 1.4 Hz. The thin ramps saved 0.34 g but
made the end of the top ring 44 % softer to a side push; the 1.2 × 1.7 ramps give back that stiffness for 0.17 g.

## 2b. Print-first guards (2026-11-12)

The first print of the A2 core (PETG Matte, upside down) failed: the top rings of the guards needed supports and broke
when they were removed. Three print-first guards were compared at RM 52 (FE as in the handoff §5, core + T400; static
5 N on a 1.6 mm patch of the front-left guard, stack bosses clamped; support envelope from a 45° overhang analysis of
the core printed upside down). Raw data: `Checks/ACwing_Mech_A1_print_study.json`.

| Guard | Core (solid) | 1st / 2nd mode | Outer push | Side push 90° | Vertical 90° | Push on the ramp | Support in the guards | Support, whole core |
|---|---|---|---|---|---|---|---|---|
| A2 rings (2026-11-08, printed) | 15.55 g | 98.8 / 153.5 Hz | 7.96 mm | 7.89 mm | 13.65 mm | 0.16 mm | 2.9 cm³ (guards + spokes) | 28.2 cm³ |
| P1: band, pointed arches, 45° flare | 18.17 g | 93.9 / 146.3 Hz | 3.22 mm | 3.57 mm | 7.54 mm | 0.99 mm | 0 | 20.9 cm³ |
| P2: wave (2026-11-12) | 17.63 g | 93.9 / 141.1 Hz | 3.57 mm | 4.99 mm | 9.06 mm | 1.97 mm | 0.06 cm³ | 20.8 cm³ |
| **P2 + frame fixes (2026-11-13, adopted)** | **16.67 g** | **91.7 / 135.8 Hz** | **4.53 mm** | **5.63 mm** | **10.33 mm** | **2.30 mm** | **0.04 cm³** | **20.2 cm³** |

P2 is the wave proposed by Andrea Cirillo: an S ribbon between the top lip and the lower rim, the same smoothstep curve
as the cover skirt, and a 1.2 mm outward bulge. Every window sill is a 45° slope or a 6.2 mm bridge. A first P2 with
a 1.8 mm ribbon and no ramp rim weighed 17.29 g but was 3.0 mm soft at the ramp; the 2.2 mm ribbon and the 1.2 mm
ramp rim cost 0.35 g and gave back a third of that. The guards are stiffer than the A2 rings everywhere (×2.2 at the outer side, ×1.1 at
φ 60) except at the ramp, where a 5 N push still bends them less than 2 mm. Peak stress (99.9th percentile von Mises) for
5 N on the outer side: 13 MPa (A2 25.8 MPa), well under the 45–50 MPa of PETG.

## 3. Frame options of 2026-11-07 (FE, core + T400)

The options were compared on 2026-11-07 with the motors at RM 53, the RM of that moment. The chosen design (RM 51,
0.8 mm holders) was then run again: core 14.83 g (voxels), **first mode 127.0 Hz**.

The first free-free mode is the "saddle" mode: diagonal motors in phase, the guard rings bending. It sets the frame
stiffness that matters for the FC soft mount and for the gyro notch.

| Option | Core mass (g) | Δ mass | 1st mode (Hz) | Δ | Verdict |
|---|---|---|---|---|---|
| Base (RM 53, rev A stack, cover) | 15.56 | – | 121.3 | – | reference |
| **Motor holders: wall 1.0 → 0.8 mm, floor 1.2 → 1.0 mm** | 15.05 | **−0.51** | 121.2 | −0.1 | **adopted** |
| Deck 1.2 → 1.0 mm | 15.43 | −0.13 | 122.6 | +1.3 | not adopted: it lowers the whole stack by 0.1 mm for a small gain |
| Guard ribs 6 → 4 per ring | 15.45 | −0.10 | 119.2 | −2.1 | no |
| Arms 10 / 3.5 → 8 / 3.0 mm deep | 15.20 | −0.36 | 118.0 | −3.3 | possible; keep for a later revision |
| Lighter guard rings (top 0.9 × 1.1, bottom 1.1 × 1.4, ribs Ø1.0) | 14.77 | −0.79 | 96.8 | −24.5 | no: the rings carry the first mode |
| Rings + ribs + holders together | 14.06 | −1.50 | 95.8 | −25.5 | no |

The voxel masses (h 0.35) run about 0.4 g above the meshed mass. The differences between options are what count.

The guard rings are the efficient part of the structure: they weigh 17 % of the core but give most of its torsional
stiffness. Lightening them drops the first mode into the middle of the 60–130 Hz band of the FC soft mount.
Lightening the holders costs nothing in stiffness.

## 4. Other options

| Option | Δ mass (g) | Status / note |
|---|---|---|
| Cover walls and roof 1.2 → 0.8 mm (2 lines of 0.4) | −1.6 | **adopted** (4.4 → 2.8 g; the roof is also 0.6 mm lower now that no cable runs over the FC) |
| No cover at all | −2.8 more | possible, but the stack screws then need washers, and no standard length fits well indoor (see the cover README) |
| Titanium instead of A4 for the 4 stack screws | −0.6 | recommended (also non-magnetic) |
| Titanium tray screws M2 × 5 | −0.3 | optional |
| Flow inserts → thread-forming screws into the PETG bosses | −0.2 | optional; the flow board is rarely removed |
| TPU sleeves 0.6 → 0.45 mm | ≈ −0.5 | needs a print test for motor retention |
| Print settings | ≈ −0.5 to −1.0 | the masses above are solid-mesh masses. With 3 perimeters and 30–40 % gyroid, the thick parts (bosses, lugs, holder floors) print lighter. Weigh the first print |
| Motors 0720 instead of 8520 | ≈ −5 | changes thrust and endurance; out of scope for the frame |
| 1.0 mm FC and ESC boards | −3.6 | **adopted by the electronics on 2026-11-07 evening** (HW handoff §0.19) |
| Old bottom bridges removed (keep only the new ones) | ≈ −0.1 | possible in a regenerated core |

## 5. Result (2026-11-07)

Changes adopted on 2026-11-07, against the A1 design for the rev A stack of 2026-11-06:

| Change | Δ mass (g) |
|---|---|
| Thinner motor holders | −0.5 |
| Cover 0.8 mm walls, lower roof | −1.6 |
| Stack screws M2 × 16 → M2 × 14 | −0.1 |
| Motors at RM 51 (RM 53 not needed once ESC J1 moved toward the corner) | 0 |
| **Total** | **−2.2** |

The first frame mode goes from 125.8 Hz (1.0 mm stack, 12 g) to 127.0 Hz with the heavier 1.6 mm stack and the cover
(19 g), thanks to the lighter holders.

The battery dominates everything else: T800 adds 10.6 g over T400, and T1200 adds 18.5 g. For a light indoor drone,
the next steps are titanium screws (−0.6 g) and weighing the printed parts.

## 6. Result (2026-11-08)

Drone T400 indoor ≈ 67.4 g, T/W 2.08 (T800 ≈ 78.2 g, T1200 ≈ 86.6 g). First frame mode 98.8 Hz with T400 in the
2026-11-08 FE model (102.5 Hz for the RM 51 design in the same model).

## 7. Result (2026-11-12)

Drone T400 indoor ≈ 69.3 g, T/W 2.02 (T800 ≈ 80.1 g, T1200 ≈ 88.5 g). First frame mode 93.9 Hz with T400 (T800
87.2 Hz, T1200 92.8 Hz) in the same FE model. The print-first guards cost 2.1 g of solid mass for a core that prints
without supports in the guards. Printed, expect about 15 g (the A2 core printed at 13 g for 15.55 g solid). The next
steps for a lighter indoor drone are still titanium screws (−0.6 g) and weighing the printed parts.

## 8. Result (2026-11-13)

Drone T400 indoor ≈ 68.3 g, T/W 2.05 (T800 ≈ 79.1 g, T1200 ≈ 87.5 g). First frame mode 91.7 Hz with T400 (T800
84.9 Hz, T1200 90.3 Hz). The one-piece motor holders with the L1 foot ring replace the landing loops: −0.96 g on the
core, frame 28.0 mm tall instead of 36.4 mm (handoff §13).
