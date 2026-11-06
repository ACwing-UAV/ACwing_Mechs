# Electronics cover A1

A translucent PLA cover over the electronics stack, with the ACwing logo raised on the roof. Fits ESC 1S rev A + FC rev A
(indoor) or ESC 1S rev A + FC rev A + GPS rev A (GPS option). All boards are 1.6 mm (2026-11-06).

| File | Variant | Size (board axes) | Height (frame z) | Mass (PLA, solid) | Stack screws |
|---|---|---|---|---|---|
| `ACwing_Cover_A1_indoor.stl` | ESC + FC | 52 × 52 mm | z 5.0 → 13.5 (8.5 mm) | 4.4 g | 4 × M2 × 16 ISO 7380 |
| `ACwing_Cover_A1_gps.stl` | ESC + FC + GPS | 52 × 52 mm | z 5.0 → 22.7 (17.7 mm) | 5.4 g | 4 × M2 × 25 ISO 7380 |

The meshes are in assembly position (frame coordinates: z = 0 propeller plane, +Y forward). The print files, on z = 0,
are written by the assembly macro to `00 - Docs/00 - Mech_A1_Docs/Prints/`.

## Shape

- **Hood.** Rounded square aligned with the boards (45° to the frame), outer half-size 26 mm, R4 edges, wall and roof
  1.2 mm (3 lines of 0.4 mm). Open at the bottom (z 5.0, 0.4 mm above the FC bottom face).
- **Side openings.** One arched opening per side, 34 mm wide, from the bottom edge to 0.6 mm under the roof. They give
  room to the plugs on every edge (ESC J1 and FC J5 rear, FC J2 and J6 front, FC J3 and J4 right, GPS J1/J2 right) and
  to the cable bundles, and let air through.
- **USB-C notch.** At the frame +X corner, for the FC J1 USB-C plug.
- **Posts.** Four Ø5 posts on the 20 × 20 stack columns.
  - Indoor: they sit on the upper silicone grommets (z 8.4).
  - GPS: they sit on the GPS board (z 13.8) with a Ø3.8 foot, 3.2 mm tall, that clears the GPS J1 / J2 bodies next
    to the columns; full Ø5 above it.
  - Each has a Ø2.3 bore and a Ø4.0 counterbore for the ISO 7380 button head (dk 3.5, k 1.1). The heads sit 0.1–0.2 mm
    below the roof top.
- **Logo.** ACwing logo from the ACwing_HW footprint `ACwing_Logo_Full_10mm`, 24 mm wide, raised 0.6 mm, aligned
  with the frame (front = +Y). It is kept 1 mm away from the screw counterbores.

## Dimensions: where they come from

The size was set from the assembly (cables, plugs, screws), not from a free choice:
- **Roof.** The roof underside is 0.85 mm above the top of cable A. Cable A runs flat over the FC at z 10.4, between
  the stack columns (posts and S2 spacers); its top is at 10.83.
  - With the GPS, the roof underside is 0.8 mm above the SAM-M10Q top (z 20.1).
- **Width.** The plugs mated on the board edges end 25.3 mm from the board centre, so the inner wall is at 24.8 mm.
  They pass through the side openings.
- **Screw length.** The head sits in the counterbore and the tip ends 2.4–2.7 mm into the 3 mm boss insert (tip z −4.4
  indoor, −4.1 GPS), clear of the battery.

Checks against the frame, propellers, stack parts, plugs, cables and screws: see
`00 - Docs/00 - Mech_A1_Docs/Checks/`.

## Print

- Translucent (natural) PLA, 0.4 mm nozzle, 0.12–0.16 mm layers, 3 perimeters (walls fully solid).
- Print it **upright**: open bottom on the bed, logo up, so the logo comes out sharp.
- The roof spans about 50 mm between the walls. Use tree supports from the bed under the roof, inside only, or
  bridge it with slow bridge settings. Supports leave marks on the inside face only.
- For a clearer finish: slow outer wall, no ironing on the logo, 215–220 °C.

## Use

The cover is part of the stack clamp: the four stack screws go through it, and the screw lengths are chosen for it.
Without the cover:
- GPS option: M2 × 18 from the GPS top (tip z −4.2);
- indoor: no standard length fits well with 1.6 mm boards. M2 × 14 with a washer on the upper grommet ends at z −5.3,
  0.1 mm above the bottom of the insert seat, so fit the cover.
