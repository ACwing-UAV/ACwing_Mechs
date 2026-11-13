# Frame A1 – core

`ACwing_Frame_A1_core.stl`: the frame A1 core (PETG, 17.63 g solid), source mesh in the **assembly position**
(z = 0 propeller plane, +Y forward). It is the printing master: the print-ready copy (upside down, on z = 0) is
written by the Mech A1 macro to `00 - Docs/00 - Mech_A1_Docs/Prints/`.

- Fits ESC 1S rev A, FC rev A, GPS rev A (option) and Flow rev A, all 1.0 mm (ACwing_HW handoff §0.19–§0.20,
  2026-11-08), with the A1 battery trays.
- Motors at **RM 52** (frame 134.8 × 134.8 × 36.4 mm), 4 holders for 8.5 mm motors in TPU sleeves.
- **Wave prop guards** (2026-11-12, print-first): a 0.86 mm wall bulged 1.2 mm outward, with a top lip, a lower rim and
  an S ribbon between them (the curve of the cover skirt), 15 windows per guard. Every window sill is a 45° slope or a
  6.2 mm bridge, so the guards print upside down with no support inside. Open toward the body (45° ramps with a 1.2 mm
  rim), so the board-edge plugs and cable A have free room above them. Straight spokes at the lower-rim level, bottom
  bridges between the guards.
- **12 closed wire eyelets** on the arms (3 per arm): the motors have no connector, so thread the leads before
  soldering them.
- 4 stack bosses (20 × 20 pattern, hot-melt inserts), 4 tray lugs (flat faces at z −9.0, inserts open downwards),
  knee braces, side spars, cable C slot behind the rear grommets.
- Design notes: [`ACwing_frame_A1_mechanical_handoff.md`](../../00%20-%20Docs/00%20-%20Mech_A1_Docs/ACwing_frame_A1_mechanical_handoff.md) §11–§12.
- Mesh: about 1.04 M triangles (36 MB). Made by mesh booleans from the 2026-11-07 core (2026-11-08: pods moved to RM 52;
  2026-11-12: guards, spokes and eyelets replaced), so it is a single manifold solid with a few touching (pinched) edges
  where swept fills meet; slicers accept it.
- Print: upside down, guard top lips on the bed; tree supports only under the deck, holders and arms. PETG Basic / HF,
  not Matte (see the Mech A1 README).
