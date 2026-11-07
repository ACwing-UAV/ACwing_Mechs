# Mech A1 – checks

## Assembly checks

Files: `ACwing_Mech_A1_assembly_checks_<tray>_<indoor|gps>.json` (2026-11-07).

Each key in `checks` is a pair of parts. The value is the overlap volume in mm³, sampled on the signed-distance models
with h = 0.06–0.15 mm, only in the cells where both parts can be inside. `cables` gives the wire lengths between the
plug housings, in mm. `cover` gives the cover heights and the stack screw (length, head seat, tip).

**Inputs:**
- ACwing_HW rev A boards, all 1.6 mm (ESC layout of branch `esc-j1-corner`, 2026-11-07);
- frame A1 (motors at RM 51) with the new cable C slot; ESC 1S J1 at (+13.3, +16.08), toward the front corner;
- flow board turned 90° (connectors toward +X);
- electronics cover A1 with 0.8 mm walls (indoor or GPS);
- silicone grommets H 6.0 with a 1.6 mm groove.

**Result:** every pair is **0** in all four runs (T400 indoor, T400 GPS, T800 indoor, T1200 indoor), except tray ×
battery: 0.003 mm³ (T400) and 0.036 mm³ (T800), which is the pack resting on the lips.

The checks include:
- frame × stack, USB-C plugs, plug housings, wires, hardware, flow board, battery, insertion path;
- propellers × stack, wires, housings, tray, cover;
- wires × stack parts and hardware (spacers, grommets, screws);
- tray × frame, battery, wires, motor leads, flow board, housings;
- optical cones of the flow board × frame, wires, housings, screws, tray, battery;
- cover × frame, propellers, stack boards and parts, FC grown 0.8 mm (soft-mount float), wires, plug housings, plug
  envelopes (USB-C narrowed to the 13.2 mm overmold), screws, grommets;
- frame × FC J5 (ELRS) and J6 (ESC link B) plug envelopes.

**Smallest clearances, measured on the models:**

| Cable | Clearance |
|---|---|
| A | propeller disc 2.8 mm, frame (guard ring) 0.42 mm, cover 1.25 mm |
| C | frame 0.49 mm, tray 0.69 mm, FC J1 USB-C plug 2.4 mm, motor leads 6.4 mm |

## Weight study

`ACwing_Mech_A1_fe_weight_study.json`: core mass and first 10 free-free modes for each frame variant, and the core mass
by group. See `../ACwing_Mech_A1_weight_study.md`.

## Vibration

Files: `ACwing_Mech_A1_fe_modes_<case>.json`.

The model is a voxel FE: hex8 elements, h 0.8 mm, PETG with E 2000 MPa. Motors, stack, battery and flow board are
lumped masses. `modes` gives the free-free frequencies after the 6 rigid modes, with the share of the motors and of
the hub in each mode.

| Case | Saddle mode |
|---|---|
| Preliminary draft (reference, bay fused to the frame) | 100.8 Hz |
| A1 + T400 | 125.8 Hz |
| A1 + T800 | 123.9 Hz |
| A1 + T1200 | 102.6 Hz |
| A1 + T400, 0.8 mm motor holders, 1.6 mm stack + cover lumped at 19 g (2026-11-07) | 127.0 Hz |
| same at RM 53 (weight study, `ACwing_Mech_A1_fe_weight_study.json`) | 121.2 Hz |

The A1 rows above were computed at RM 51 with the 1.0 mm stack (12 g).
