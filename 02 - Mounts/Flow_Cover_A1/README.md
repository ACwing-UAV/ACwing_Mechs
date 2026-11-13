# Flow board cover A1

A thin PETG cover over the sensor side of the **ACwing Flow rev A** board (new on 2026-11-13). The PCB and its parts are
covered; only the two sensors and the status LED look out. One part fits every battery tray (T400, T800, T1200).

| File | Position | Size | Mass (PETG, solid) | Screws |
|---|---|---|---|---|
| `ACwing_Flow_Cover_A1.stl` | assembly position on the T400 / T1200 tray (board sensor face at z −20.3) | 24.6 × 23.2 × 4.4 mm | 0.67 g | 2 × M2 × 6 nylon pan head |

On the T800 tray the same part sits 1.0 mm lower (sensor face at z −21.3): the assembly macro moves it. The print copy,
plate on z = 0, is `00 - Docs/00 - Mech_A1_Docs/Prints/ACwing_Mech_A1_06_Flow_cover_PETG.stl`.

## Shape

- **Plate.** 0.8 mm thick, 2.6 mm under the board sensor face: 0.3 mm under the tallest part (PMW3901, 2.28 mm).
  Outline = board outline + 0.25 mm gap + 0.8 mm wall, R1.6 corners.
- **Walls.** 0.8 mm, on the −X, +Y and −Y sides, up to the board back (they cover the board edge).
- **Openings** (only these):
  - PMW3901 lens, Ø6.0 mm on the optical axis (frame 0, 0), with a 0.9 mm 45° outward flare;
  - VL53L1X window 3.0 × 5.4 mm (frame 7.0, 0), R0.6 corners, same flare;
  - status LED D1, Ø1.2 mm (frame 10.65, 1.6).
  The flares stay outside the 46° (PMW3901) and 31° (VL53L1X) fields of view: the checks run the optical cones against
  the cover (`00 - Docs/00 - Mech_A1_Docs/Checks/`, 0.80 mm margin).
- **Connector edge (+X).** Open from x 11.4: J1 / J2 (2.9 mm tall) and the Qwiic plugs (cable C) go in as before.
  A 4 mm tongue between the two connectors covers the bridge MCU up to x 17.2.
- **Standoffs.** Two Ø4.9 standoffs on the flow screw axes (frame 6.6, ±8.0) press the board against the tray bosses.
  Ø2.3 holes, Ø4.0 × 1.4 mm counterbores for the screw heads.

## Fitting

1. Put the board on the tray bosses, the cover over it, and drive the
   two **M2 × 6 nylon** screws from below (head seat 2.0 mm under the sensor face; about 3 mm of thread in the insert).
2. Plug cable C into Flow J1 after the cover is on.

The screws replace the M2 × 4 of the bare board. Ground clearance of the plate with the drone landed (foot rings at
z −30): 6.3 mm (T400, T1200), 5.3 mm (T800).

## Print

PETG, black or grey (no stray light on the sensors), 0.4 mm nozzle, 0.12 mm layers, 2 walls, 100 % infill, plate on the
bed, no supports.
