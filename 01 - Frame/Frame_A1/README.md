# Frame A1 – core

`ACwing_Frame_A1_core.stl`: the frame A1 core (PETG, 16.67 g solid), source mesh in the **assembly position**
(z = 0 propeller plane, +Y forward). It is the printing master: the print-ready copy (upside down, on z = 0) is
written by the Mech A1 macro to `00 - Docs/00 - Mech_A1_Docs/Prints/`.

- Fits ESC 1S rev A, FC rev A, GPS rev A (option) and Flow rev A, all 1.0 mm (ACwing_HW handoff §0.19–§0.20,
  2026-11-08), with the A1 battery trays.
- Motors at **RM 52** (frame 134.8 × 134.8 × 28.0 mm), 4 one-piece holders for 8.5 mm motors in TPU sleeves
  (2026-11-13): 0.85 mm wall with a 45° top chamfer, snap windows at ±90°, floor with the lead hole and an **L1 foot
  ring** (the drone stands on the four holders; no landing loop).
- **Wave prop guards** (2026-11-12, print-first): a 0.86 mm wall bulged 1.2 mm outward, with a top lip, a lower rim and
  an S ribbon between them (the curve of the cover skirt), 15 windows per guard. Every window sill is a 45° slope or a
  6.2 mm bridge, so the guards print upside down with no support inside. Open toward the body (45° ramps with a 1.2 mm
  rim), so the board-edge plugs and cable A have free room above them. Straight spokes flush with the lower rim and in
  line with the bridges between the guards (rim section 1.28 × 1.6 mm).
- **Motor leads**: the motors have no connector, so thread the leads before soldering: floor hole → recess in the foot
  ring → closed channel in the rib under the arm → woven through 3 teardrop holes (Ø1.9 mm) in the arm → deck slot.
- 4 stack bosses (20 × 20 pattern, hot-melt inserts), 4 tray lugs (flat faces at z −9.0, inserts open downwards),
  knee braces, side spars, cable C slot behind the rear grommets.
- Design notes: [`ACwing_frame_A1_mechanical_handoff.md`](../../00%20-%20Docs/00%20-%20Mech_A1_Docs/ACwing_frame_A1_mechanical_handoff.md) §11–§13.
- Mesh: about 0.88 M triangles (44 MB). Made by mesh booleans from the 2026-11-07 core (2026-11-08: pods moved to RM 52;
  2026-11-12: guards, spokes and eyelets replaced; 2026-11-13: holders, spokes, bridges and wire path rebuilt, arm roots
  remeshed on a 0.06 mm grid). One body, watertight, no non-manifold edges.
- Print: upside down, guard top lips on the bed; tree supports only under the deck, holders and arms. PETG Basic / HF,
  not Matte (see the Mech A1 README).
