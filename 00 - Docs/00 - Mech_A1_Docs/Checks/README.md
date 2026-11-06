# Mech A1 – checks

## Assembly checks

Files: `ACwing_Mech_A1_assembly_checks_<tray>_<indoor|gps>.json` (2026-11-07).

Each key in `checks` is a pair of parts. The value is the overlap volume in mm³, sampled on the signed-distance models
with h = 0.06–0.15 mm (only in the cells where both parts can be inside). `cables` gives the wire lengths between the
plug housings, in mm; `cover` gives the cover heights and the stack screw (length, head seat, tip).

Inputs: ACwing_HW rev A boards, connector layout of 2026-11-02/03, **all boards 1.6 mm**; silicone grommets H 6.0 with
a 1.6 mm groove; electronics cover A1 (indoor or GPS).

Every pair is **0** in all four runs (T400 indoor, T400 GPS, T800 indoor, T1200 indoor), except tray × battery:
0.003 mm³ (T400) and 0.036 mm³ (T800), the pack resting on the lips. The checks include:
- frame × stack, USB-C plugs, plug housings, wires, hardware, flow board, battery, insertion path;
- propellers × stack, wires, housings, tray, cover;
- wires × stack parts, hardware (spacers, grommets, screws);
- tray × frame, battery, wires, motor leads, flow board, housings;
- optical cones of the flow board × frame, wires, housings, screws, tray, battery;
- cover × frame, propellers, stack boards and parts, FC grown 0.8 mm (soft-mount float), wires, plug housings, plug
  envelopes (USB-C narrowed to the 13.2 mm overmold), screws, grommets;
- frame × FC J5 (ELRS) and J6 (ESC link B) plug envelopes.

Fixes made by these checks:
- cable A top run moved between the stack columns (it crossed the cover posts and, with the GPS, the S2 spacers);
- cable A rear corridor moved 0.6 mm inboard (pin 1 touched the FC J1 USB-C body);
- GPS cover posts with a Ø3.8 foot (the Ø5 post touched the GPS J1 / J2 bodies).

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
