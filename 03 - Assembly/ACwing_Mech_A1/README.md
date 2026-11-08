# ACwing Mech A1 – FreeCAD assembly macro

`ACwing_Mech_A1.FCMacro` builds the Mech A1 assembly and writes the print files.

## Run it

1. Open FreeCAD (0.21 or 1.0).
2. Choose **Macro → Macros…**, select `ACwing_Mech_A1.FCMacro` in this folder and click **Execute**.
   Keep the macro in this folder: it finds the repository root from here.

The macro:
- writes the **print-ready STL files** (oriented, on z = 0) to `00 - Docs/00 - Mech_A1_Docs/Prints/` (all three trays);
- builds the assembly with the selected tray in a new document (groups Frame, Propulsion, Electronics, Hardware, Cables,
  Cover);
- writes the hardware, cables and battery as STEP to `00 - Docs/00 - Mech_A1_Docs/STEP/`.

## Options (top of the macro)

| Option | Default | Meaning |
|---|---|---|
| `TRAY` | `'T400'` | `'T400'` / `'T800'` / `'T1200'` |
| `WITH_GPS` | `True` | GPS rev A, cable B, S2 spacers, GPS cover, M2 × 25 screws (outdoor variant). `False`: indoor cover, M2 × 14 |
| `WITH_FLOW` | `True` | Flow rev A board and cable C |
| `WITH_ELECTRONICS` | `True` | board STEP models from ACwing_HW |
| `HW_DIR` | `''` | path to an ACwing_HW clone; empty = look for `../ACwing_HW` or `../hw` next to this repository |
| `EXPORT_PRINTS` | `True` | rewrite `Prints/` |
| `EXPORT_STEP` | `True` | write `STEP/` |
| `SAVE_FCSTD` | `False` | save the document to `00 - Docs/00 - Mech_A1_Docs/CAD/` (large: it holds the meshes) |

## Electronics

The board models are **not copied** into this repository (see the repository README). The macro reads them from
ACwing_HW (`00 - Docs/<board>_Docs/<board>.step`):
- in the system repository, the `hw/` submodule sits next to this one;
- otherwise, clone ACwing_HW next to ACwing_Mechs or set `HW_DIR`.

If the models are not found, the boards are skipped and the flow board is drawn as a simple placeholder.

Placement: KiCad STEP centre (X 150, Y −100) → frame origin, rotated +45° about z. The bottom faces sit at:
- ESC −2.0;
- FC 4.0;
- GPS 11.0.

All boards are 1.0 mm (ACwing_HW handoff §0.19–§0.20, 2026-11-08). The FC sits in M2 damping balls (2.43 mm above and
below the board), on S1 spacers of 2.57 mm; the GPS sits on S2 spacers of 3.57 mm.

The Flow board is flipped (sensor side down) with its back face on the tray bosses, and turned so that its
connector edge faces the frame right (+X, since 2026-11-07).

## Files

| File | What |
|---|---|
| `ACwing_Mech_A1.FCMacro` | the macro |
| `ACwing_Mech_A1_data.json` | assembly data: stack heights, hardware positions, wires of every cable (with lengths), plug housings, cover screw lengths and seats, per-tray battery and flow heights |
| `reference/` | non-printed parts for the assembly view, motors at RM 52: 8520 coreless motors, 55 mm propeller discs (front pair green), motor leads |

The printed parts come from `01 - Frame/` and `02 - Mounts/` (cover: `02 - Mounts/Electronics_Cover_A1/`).

Frame coordinates:
- z = 0 is the propeller plane;
- +Y is forward;
- +X is right.

Units are mm.
