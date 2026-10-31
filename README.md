<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ACwing-UAV/ACwing_HW/main/00%20-%20Docs/05%20-%20Brand/ACwing_logo_white.png">
    <img alt="ACwing" src="https://raw.githubusercontent.com/ACwing-UAV/ACwing_HW/main/00%20-%20Docs/05%20-%20Brand/ACwing_logo_black.png" width="260">
  </picture>
</p>

<h1 align="center">ACwing – mechanics</h1>

<p align="center">
  Frames, mounts and printed parts for the ACwing multirotors<br>
  by Andrea Cirillo
</p>

---

**ACwing** is an open project for small multirotors. This repository holds the
mechanical design. The other parts of the project:

| Repository | What |
|---|---|
| [ACwing](https://github.com/ACwing-UAV/ACwing) | system repository: the three repositories below as submodules, compatible versions, releases |
| [ACwing_HW](https://github.com/ACwing-UAV/ACwing_HW) | PCBs: flight controller, ESC 1S, GPS, Flow |
| [ACwing_FW](https://github.com/ACwing-UAV/ACwing_FW) | firmware, PC tools, ACwing Pilot app |
| **ACwing_Mechs** | this repository |

## Interfaces with the electronics

The board outlines, holes and keep-outs are **produced by the hardware
repository** (its generator scripts write them); this repository consumes
them and never keeps a copy. Point to the file in `ACwing_HW` – or to the `hw/`
submodule of the system repository – from the CAD model or the README of the
part that uses it.

| Interface | Source in ACwing_HW |
|---|---|
| FC outline, holes (DXF) | [`00 - Docs/00 - FC_Docs/ACwing_FC_A_outline.dxf`](https://github.com/ACwing-UAV/ACwing_HW/blob/main/00%20-%20Docs/00%20-%20FC_Docs/ACwing_FC_A_outline.dxf) |
| Flow board outline (DXF) | [`00 - Docs/03 - FLOW_Docs/ACwing_Flow_A_mech_outline.dxf`](https://github.com/ACwing-UAV/ACwing_HW/blob/main/00%20-%20Docs/03%20-%20FLOW_Docs/ACwing_Flow_A_mech_outline.dxf) |
| Board 3D models (STEP) | `00 - Docs/<board>_Docs/<board>.step` |
| Stack, handoff and frame answers | [`00 - Docs/04 - System_Docs`](https://github.com/ACwing-UAV/ACwing_HW/tree/main/00%20-%20Docs/04%20-%20System_Docs) |

When a part depends on a board revision, write it in the part README
(for example "fits FC rev A, layout 2026-10-24").

## Repository structure

Same convention as the other ACwing repositories: numbered top-level folders,
one folder per part family, `ACwing_<part>_<rev>` file names.

```
00 - Docs/            drawings (PDF), renders, handoff notes, assembly instructions
01 - Frame/           frames, one subfolder per revision (Frame_C2, Frame_C3, …)
02 - Mounts/          board mounts, battery holders, sensor brackets
03 - Prints/          print-ready exports (STL / 3MF) with the print settings in the README
```

For every part keep: the **native CAD file**, a **STEP export** (the neutral
format the other repositories and the stack check read), and for printed parts
the **STL/3MF** with material, layer height and orientation.

## Large files (Git LFS)

Native CAD files and print exports are binary: they are stored with
[Git LFS](https://git-lfs.com) (rules in [`.gitattributes`](.gitattributes)).
Install it once before cloning:

```
git lfs install
```

Without Git LFS, a clone gets small pointer files in place of the models.
STEP and DXF are text and stay in plain Git, so their changes show in diffs.

## Author

**Andrea Cirillo** – ACwing mechanical design.
