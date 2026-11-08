# Electronics cover A1

A translucent PLA canopy over the electronics stack, with the ACwing logo raised on the roof. Fits ESC 1S rev A + FC rev A
(indoor) or ESC 1S rev A + FC rev A + GPS rev A (GPS option), all boards **1.0 mm**. Redrawn on 2026-11-08 to follow the
frame with the A2 guard rings.

| File | Variant | Size (board axes) | Height (frame z) | Mass (PLA, solid) | Stack screws |
|---|---|---|---|---|---|
| `ACwing_Cover_A1_indoor.stl` | ESC + FC | 52 × 52 mm, concave sides | z 6.2 → 12.0 (logo 12.6) | 3.0 g | 4 × M2 × 14 ISO 7380 |
| `ACwing_Cover_A1_gps.stl` | ESC + FC + GPS | 52 × 52 mm, concave sides | z 6.2 → 21.95 (logo 22.55) | 4.5 g | 4 × M2 × 25 ISO 7380 |

The meshes are in assembly position (frame coordinates: z = 0 propeller plane, +Y forward). The print files, on z = 0,
are written by the assembly macro to `00 - Docs/00 - Mech_A1_Docs/Prints/`.

## Shape

- **Plan.** The 52 mm square aligned with the boards (45° to the frame), R7 corners. Each side is **concave**: an arc
  28 mm from the motor axis it faces, 0.5 mm outside the propeller disc, like the deck between the guard rings.
- **Roof.** Crowned (+0.7 mm at the centre), 3 mm fillet into the walls; the walls taper 0.7 mm toward the roof.
  Wall and roof 0.8 mm (2 lines of 0.4 mm).
- **Skirt.** Its lower edge is a wave: low at the four corners (z 6.2), high at the side centres (z 9.0 indoor, 17.0 GPS),
  with the smoothstep curve of the guard-ring ramps. The plugs and cables on the board edges stay under the high part.
- **LEDs.** The FC RGB LEDs at the front and rear corner tips show under the skirt.
- **USB-C.** Notch at the frame +X corner for the FC USB-C plug. The ESC USB-C plug (6 mm lower) passes under the
  cover. One plug at a time (the two overmolds overlap, HW handoff §0.19).
- **Posts.** Four Ø5 posts on the 20 × 20 stack columns.
  - Indoor: they sit on the upper damping balls (z 7.43).
  - GPS: they sit on the GPS board (z 12.0) with a Ø3.8 foot, 3.2 mm tall, that clears GPS J1 / J2; full Ø5 above it.
  - Each has a Ø2.3 bore and a Ø4.0 counterbore for the ISO 7380 head (dk 3.5, k 1.1). Head seat z 9.4 indoor
    (head 0.8 mm below the roof), z 20.0 GPS.
- **Logo.** ACwing logo from the ACwing_HW footprint `ACwing_Logo_Full_10mm`, 24 mm wide, raised 0.6 mm on the crowned
  roof, aligned with the frame (front = +Y), 1 mm away from the counterbores.

## Dimensions: where they come from

- **Roof.** Indoor roof underside z 10.5: 1.5 mm above the tallest FC part (L3, z 9.0) and above the top of the FC
  USB-C notch (plug top z 9.83). GPS: 2.25 mm above the SAM-M10Q (z 18.2), as needed by the M2 × 25 screw.
- **Screws.** Head in the counterbore, tip 2.6 mm (indoor, z −4.6) or 3.0 mm (GPS, z −5.0) into the 3 mm boss insert,
  never past the insert seat (z −5.4), clear of the battery.
- **Clearances** (checks 2026-11-08): FC 1.4 mm, plug housings 0.5 mm, cable A 0.5 mm.

## Print

- Translucent (natural) PLA, 0.4 mm nozzle, 0.12–0.16 mm layers, 2 perimeters (walls fully solid), 5–6 top layers.
- Print it **upright**: skirt corners on the bed, logo up, so the logo comes out sharp.
- Tree supports from the bed under the roof (inside) and under the skirt arches. Supports leave marks on the inside
  face only.
- For a clearer finish: slow outer wall, no ironing on the logo, 215–220 °C.

## Use

The cover is part of the stack clamp: the four stack screws go through it, and the screw lengths are chosen for it.
Without the cover: M2 × 12 with a 0.3 mm washer on the upper ball (indoor, tip z −4.3), or M2 × 16 from the GPS top
(tip z −4.0).
