# Mech A1 – checks

## Assembly checks

Files: `ACwing_Mech_A1_assembly_checks_<tray>_<indoor|gps>.json` (2026-11-12).

Every pair of parts is intersected as a mesh boolean (manifold3d): `unexpected_overlaps_mm3` lists the pairs that
overlap and are not an assembly interface, `assembly_interfaces_mm3` the expected contacts (sleeve in holder, screw in
insert, board on spacer, plug on its header, …). `clearances_mm` gives the minimum distance between selected parts.
`cables_wire_mm` gives the wire lengths between the plug housings; `stack_screws` the spacer and screw sizes, head
seat and tip.

**Inputs:**
- ACwing_HW rev A boards, all 1.0 mm (STEP models of 2026-11-08, every part of every board; the silkscreen update of
  2026-11-12 does not change the geometry);
- frame A1 at RM 52 with the wave guards (2026-11-12); ESC 1S J1 and FC J2 at (−10.5, +16.85);
- flow board turned 90° (connectors toward +X), optical cones of the PMW3901 (46°) and VL53L1X (31°);
- flat-roof electronics cover of 2026-11-12 (indoor or GPS), M2 damping balls, S1 2.57 / S2 3.57 mm;
- plug envelopes of FC J5 (ELRS), FC J6 (ESC B) and both USB-C plugs (12.4 × 6.5 mm overmold, 26 mm long).

**Result:** **no unexpected overlap** in all four runs (T400 indoor, T400 GPS, T800 indoor, T1200 indoor). The battery
touches the core envelope limit (z −6.7) with T800 / T1200 without entering it. The JST-PH pair of the battery lead
sits in line with the insertion path: plug it after the pack is in.

**Smallest clearances (T400 indoor):**

| Part | Clearance |
|---|---|
| Cable A | propeller disc 1.37 mm, frame 4.55 mm, cover 0.51 mm |
| Cable C | frame 0.51 mm, tray 0.47–0.53 mm, FC USB-C plug 5.4 mm, propeller disc 4.0 mm |
| Cable D | frame 0.48 mm |
| Cover | FC 1.36 mm, plug housings 0.52 mm (GPS cover: cable B 1.41 mm) |
| USB-C plugs | FC plug – frame 1.20 mm, ESC plug – frame 0.77 mm (the guard bulge fades to a straight wall there) |
| Frame | propeller disc 1.00 mm, FC 5.28 mm |

## Print study

`ACwing_Mech_A1_print_study.json` (2026-11-12): core mass, free-free modes (T400 / T800 / T1200), deflection and stress
under 5 N on a guard, and the support estimate of the core printed upside down, for the A2 rings, proposal P1 (band
guard with pointed arches and a 45° flare) and the adopted wave guards. See the handoff §12 and the weight study §2b.

## Guard-ring study

`ACwing_Mech_A1_guard_ring_study.json` (2026-11-08): core mass, free-free modes and the deflection under 5 N side /
vertical loads on a guard for the closed rings, the open rings with thin ramps, the open rings with steep ramps and
the adopted A2 rings. See the handoff §11.

## Weight study

`ACwing_Mech_A1_fe_weight_study.json` (2026-11-07): core mass and first 10 free-free modes for each frame variant,
and the core mass by group. See `../ACwing_Mech_A1_weight_study.md`.

## Vibration

Files: `ACwing_Mech_A1_fe_modes_<tray>.json` (2026-11-12; the A2 and P1 values in the same model are kept in each file).

Voxel FE: hex8 elements, h 0.6 mm, PETG with E 2000 MPa. Motors (4 × 4.0 g), stack + cover (15.0 g), battery (on the
tray lips and rails) and flow board are lumped masses. Free-free frequencies after the 6 rigid modes.

| Case | First mode (saddle) |
|---|---|
| A1 2026-11-01 (RM 51, closed rings) + T400, same model | 102.5 Hz |
| A1 RM 52, A2 + T400 | 98.8 Hz |
| A1 RM 52, A2 + T800 | 91.8 Hz |
| A1 RM 52, A2 + T1200 | 97.6 Hz |
| A1 RM 52, wave guards + T400 | 93.9 Hz |
| A1 RM 52, wave guards + T800 | 87.2 Hz |
| A1 RM 52, wave guards + T1200 | 92.8 Hz |
| **A1 RM 52, 2026-11-13 (one-piece holders) + T400** | **91.7 Hz** |
| A1 RM 52, 2026-11-13 + T800 | 84.9 Hz |
| A1 RM 52, 2026-11-13 + T1200 | 90.3 Hz |

The 2026-11-07 values (127 Hz with T400) came from the older model (h 0.8, battery on the whole tray) and are not
comparable; `ACwing_Mech_A1_fe_modes_preliminary_draft.json` keeps the old reference.
