# Frame A1 – core

`ACwing_Frame_A1_core.stl`: the frame A1 core (PETG, 15.4 g solid), source mesh in the **assembly position**
(z = 0 propeller plane, +Y forward). It is the printing master: the print-ready copy (upside down, on z = 0) is
written by the Mech A1 macro to `00 - Docs/00 - Mech_A1_Docs/Prints/`.

- Fits ESC 1S rev A, FC rev A (layout 2026-10-24), GPS rev A (option), with the A1 battery trays.
- 4 stack bosses (20 × 20 pattern, hot-melt inserts), 4 tray lugs (flat faces at z −9.0, inserts open downwards),
  knee braces, side spars, 4 prop guards Ø57, 4 holders for 8.5 mm motors in TPU sleeves.
- Design notes: [`ACwing_frame_A1_mechanical_handoff.md`](../../00%20-%20Docs/00%20-%20Mech_A1_Docs/ACwing_frame_A1_mechanical_handoff.md).
- Mesh: 500 k triangles, watertight, within 0.01 mm of the 0.2 mm design mesh (generated from the signed-distance model).
