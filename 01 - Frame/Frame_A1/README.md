# Frame A1 – core

`ACwing_Frame_A1_core.stl`: the frame A1 core (PETG, 15.55 g solid), source mesh in the **assembly position**
(z = 0 propeller plane, +Y forward). It is the printing master: the print-ready copy (upside down, on z = 0) is
written by the Mech A1 macro to `00 - Docs/00 - Mech_A1_Docs/Prints/`.

- Fits ESC 1S rev A, FC rev A, GPS rev A (option) and Flow rev A, all 1.0 mm (ACwing_HW handoff §0.19–§0.20,
  2026-11-08), with the A1 battery trays.
- Motors at **RM 52** (frame 132.9 × 132.9 × 38.0 mm), 4 holders for 8.5 mm motors in TPU sleeves.
- **A2 prop guards** (2026-11-08): the top ring covers only the outer half of each guard and ramps down to the bottom
  ring toward the body, so the board-edge plugs and cable A have free room above them. Ribs at ±90° and ±150°, bottom
  bridges between the guards.
- 4 stack bosses (20 × 20 pattern, hot-melt inserts), 4 tray lugs (flat faces at z −9.0, inserts open downwards),
  knee braces, side spars, cable C slot behind the rear grommets.
- Design notes: [`ACwing_frame_A1_mechanical_handoff.md`](../../00%20-%20Docs/00%20-%20Mech_A1_Docs/ACwing_frame_A1_mechanical_handoff.md) §11.
- Mesh: about 800 k triangles. Made on 2026-11-08 by mesh booleans from the 2026-11-01 core (pods moved to RM 52, new
  rings), so it is a single manifold solid with a few touching (pinched) edges where swept fills meet; slicers accept it.
