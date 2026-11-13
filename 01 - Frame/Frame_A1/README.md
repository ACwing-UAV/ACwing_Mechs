# Frame A1 – core

`ACwing_Frame_A1_core.stl`: the frame A1 core (PETG, **18.12 g** solid, **rev R** of 2026-11-13), source mesh in the **assembly position**
(z = 0 propeller plane, +Y forward). It is the printing master: the print-ready copy (upside down, on z = 0) is
written by the Mech A1 macro to `00 - Docs/00 - Mech_A1_Docs/Prints/`.

- Fits ESC 1S rev A, FC rev A, GPS rev A (option) and Flow rev A, all 1.0 mm (ACwing_HW handoff §0.19–§0.20,
  2026-11-08), with the A1 battery trays.
- Motors at **RM 52** (frame 134.8 × 134.8 × **32.5 mm**), 4 one-piece holders for 8.5 mm motors in TPU sleeves
  (2026-11-13): 0.85 mm wall with a 45° top chamfer, snap windows at ±90°, floor with the lead hole and an **L1 foot
  ring** at z −30 (the drone stands on the four holders; no landing loop).
- **Wave prop guards** (2026-11-12, print-first): a 0.86 mm wall bulged 1.2 mm outward, with a top lip, a lower rim and
  an S ribbon between them (the curve of the cover skirt), 15 windows per guard. Every window sill is a 45° slope or a
  6.2 mm bridge, so the guards print upside down with no support inside. Open toward the body (45° ramps with a 1.2 mm
  rim), so the board-edge plugs and cable A have free room above them. Straight spokes flush with the lower rim and in
  line with the bridges between the guards (rim section 1.28 × 1.6 mm).
- **Motor leads**: the motors have no connector, so thread the leads before soldering: floor hole → recess in the foot
  ring → closed channel in the rib under the arm → woven through 3 teardrop holes (Ø1.9 mm) in the arm → 4th hole through the
  rail cap → deck slot.
- 4 stack bosses (20 × 20 pattern, hot-melt inserts), 4 tray lugs (flat faces at z −9.0, inserts open downwards),
  **ring beam**: side rails (raised top, flared toward the arms, round caps past the arm roots) and deck ribs from the
  stack bosses to the rails; cable C slot behind the rear grommets.
- Design notes: [`ACwing_frame_A1_mechanical_handoff.md`](../../00%20-%20Docs/00%20-%20Mech_A1_Docs/ACwing_frame_A1_mechanical_handoff.md) §11–§14.
- Mesh (rev R): about 0.61 M triangles. **Generated from scratch** from a parametric plan (no mesh surgery on older
  cores): deck, bosses, ribs, rails, lugs, arms as one smooth signed-distance body with 0.8 mm blend fillets, fused with
  the exact holders, guards, spokes and bridges; holes cut last. One body, watertight, 0 non-manifold edges, checked
  after the float32 STL round trip (what the slicer reads).
- Print: upside down, guard top lips on the bed; tree supports only under the deck, holders and arms. PETG Basic / HF,
  not Matte (see the Mech A1 README).
