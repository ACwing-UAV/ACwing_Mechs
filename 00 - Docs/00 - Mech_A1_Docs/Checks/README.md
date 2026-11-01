# Mech A1 – checks

## Assembly checks

Files: `ACwing_Mech_A1_assembly_checks_<tray>.json`.

Each key is a pair of parts. The value is the overlap volume in mm³, sampled on the signed-distance models with
h = 0.06–0.15 mm. `cables` gives the wire lengths between the plug housings, in mm.

**T400** was checked with the ACwing_HW stack data of 2026-10-24 (FC rev A and GPS rev A layout update). Every pair is 0,
except:
- tray × battery 0.003 mm³: the pack resting on the lips;
- cable B, now 13 mm.

**T800 and T1200** were checked with the stack data before that update. The frame and the trays are the same for all
three trays. The update moved only FC parts inside the board outline, FC J6 and GPS J1, so the stack and cable results
of T400 apply to them too.

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
