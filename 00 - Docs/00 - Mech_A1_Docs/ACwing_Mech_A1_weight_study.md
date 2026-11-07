# Mech A1 – weight study (2026-11-07)

Mass budget of the drone with the rev A stack (1.6 mm boards, ESC J1 on the front edge, frame RM 53) and a list of what
could make the structure lighter. Each frame option was checked with a voxel FE model of core + T400 tray (hex8, h 0.8 mm,
PETG E 2000 MPa; motors + propellers, stack, battery and flow board as lumped masses). Scripts and raw results:
`Checks/ACwing_Mech_A1_fe_weight_study.json`.

## 1. Mass budget, indoor, T400

| Group | Part | Mass (g) | Basis |
|---|---|---|---|
| Structure | Frame A1 core (RM 53, 0.8 mm motor-holder walls) | 15.13 | mesh × 1.27 g/cm³ |
| | Tray T400 | 3.44 | mesh |
| | Electronics cover, indoor (0.8 mm walls) | 2.81 | mesh × 1.24 g/cm³ |
| | Motor sleeves TPU ×4 | 2.18 | mesh × 1.21 g/cm³ |
| | Spacers S1 ×4 | 0.17 | volume |
| | Inserts ×10, grommets ×4, screws (stack Ti M2 × 14, tray A4 M2 × 5, flow nylon) | 3.2 | estimates |
| | **Structure total** | **26.9** | **38 %** |
| Propulsion | Motors 8520 ×4 | 14.4 | |
| | Propellers 55 mm ×4 | ≈ 2.0 | estimate, weigh |
| Electronics | FC rev A, 1.6 mm, with parts | ≈ 6.8 | HW handoff |
| | ESC 1S rev A, 1.6 mm, with parts | ≈ 6.6 | HW handoff |
| | Flow rev A, 1.6 mm | ≈ 2.1 | HW handoff |
| | Cables A, C, pigtail | ≈ 1.0 | estimate |
| Battery | 1S 400 mAh | 11.5 | |
| | **Drone** | **≈ 71.3** | T/W 1.96 with 140 g of thrust |

Where the core mass sits (voxel breakdown, groups overlap slightly in the blends):

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

## 2. Frame options (FE, core + T400)

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

## 3. Other options

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
| 1.0 mm FC and ESC boards | −3.6 | decided against (1.6 mm, 2026-11-06) |

## 4. Result

Changes adopted on 2026-11-07, against the A1 design for the rev A stack of 2026-11-06:

| Change | Δ mass (g) |
|---|---|
| Motors moved out to RM 53 (needed for ESC J1, see the handoff §10) | +0.24 |
| Thinner motor holders | −0.51 |
| Cover 0.8 mm walls, lower roof | −1.6 |
| Stack screws M2 × 16 → M2 × 14 | −0.1 |
| **Total** | **−2.0** |

The battery dominates everything else: T800 adds 10.6 g over T400, and T1200 adds 18.5 g. For a light indoor drone,
the next steps are titanium screws (−0.6 g) and weighing the printed parts.
