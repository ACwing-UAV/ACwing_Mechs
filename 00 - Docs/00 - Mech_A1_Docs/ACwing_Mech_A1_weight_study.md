# Mech A1 – weight study (2026-11-07, updated 2026-11-08)

Mass budget of the drone and a list of what could make the structure lighter. Since 2026-11-08: boards 1.0 mm, frame
with the A2 guard rings at RM 52, new cover. Each frame option was checked with a voxel FE model of core + T400 tray.
Scripts and raw results: `Checks/ACwing_Mech_A1_fe_weight_study.json` (2026-11-07) and
`Checks/ACwing_Mech_A1_guard_ring_study.json` (2026-11-08).

## 1. Mass budget, indoor, T400 (2026-11-08)

| Group | Part | Mass (g) | Basis |
|---|---|---|---|
| Structure | Frame A1 core (RM 52, A2 guard rings) | 15.55 | mesh × 1.27 g/cm³ |
| | Tray T400 | 3.30 | mesh |
| | Electronics cover, indoor | 3.02 | mesh × 1.24 g/cm³ |
| | Motor sleeves TPU ×4 | 2.18 | mesh × 1.21 g/cm³ |
| | Spacers S1 ×4 | 0.15 | volume |
| | Inserts ×10, damping balls ×4, screws (stack Ti M2 × 14, tray A4 M2 × 5, flow nylon) | 3.2 | estimates |
| | **Structure total** | **27.4** | **41 %** |
| Propulsion | Motors 8520 ×4 | 14.4 | |
| | Propellers 55 mm ×4 | ≈ 2.0 | estimate, weigh |
| Electronics | FC rev A, 1.0 mm, with parts | ≈ 5.0 | HW handoff (−1.8 g from 1.6 mm) |
| | ESC 1S rev A, 1.0 mm, with parts | ≈ 4.8 | HW handoff |
| | Flow rev A, 1.0 mm | ≈ 1.5 | HW handoff |
| | Cables A, C, pigtail | ≈ 0.8 | estimate (cable A now 10 mm) |
| Battery | 1S 400 mAh | 11.5 | |
| | **Drone** | **≈ 67.4** | T/W 2.08 with 140 g of thrust |

Against 2026-11-07 (71.1 g): boards −4.2 g, core +0.6 g, cover +0.2 g, tray −0.1 g, cables −0.2 g → **−3.7 g**.

The core is 0.6 g heavier than the RM 51 core of 2026-11-07:
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
2026-11-08 FE model (102.5 Hz for the RM 51 design in the same model). The next steps for a lighter indoor drone are
still titanium screws (−0.6 g) and weighing the printed parts.
