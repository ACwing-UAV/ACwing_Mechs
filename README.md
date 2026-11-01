<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ACwing-UAV/ACwing/main/brand/ACwing_logo_white.png">
    <img alt="ACwing" src="https://raw.githubusercontent.com/ACwing-UAV/ACwing/main/brand/ACwing_logo_black.png" width="260">
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
00 - Docs/            per release: print-ready files, BoM, print settings, renders, handoff notes, assembly instructions
01 - Frame/           frames, one subfolder per revision (Frame_C2, Frame_C3, …)
02 - Mounts/          board mounts, battery holders, sensor brackets
03 - Prints/          print-ready exports of single parts outside a release
04 - Assembly/        assembly macros, one subfolder per release, with the non-printed reference parts
```

The print-ready files of a release are **generated** by its assembly macro into `00 - Docs/<release>_Docs/Prints/`
(oriented for printing, on z = 0) from the source meshes in `01 - Frame/` and `02 - Mounts/`.

For every part keep: the **native CAD file**, a **STEP export** (the neutral
format the other repositories and the stack check read), and for printed parts
the **STL/3MF** with material, layer height and orientation.

## Releases

| Release | Contents | Fits | Docs |
|---|---|---|---|
| **Mech A** | frame C3 core, battery trays T400 / T800 / T1200, stack spacers, TPU motor sleeves | ESC 1S rev A, FC rev A (layout 2026-10-24), Flow rev A, GPS rev A (option) | [`00 - Docs/00 - Mech_A_Docs`](00%20-%20Docs/00%20-%20Mech_A_Docs/README.md) · macro [`04 - Assembly/ACwing_Mech_A`](04%20-%20Assembly/ACwing_Mech_A/README.md) |

```
00 - Docs/00 - Mech_A_Docs/        README (print + build guide), BoM (xlsx/csv), Prints/, STEP/, Renders/, Checks/, design notes
01 - Frame/Frame_C3/               ACwing_Frame_C3_core.stl
02 - Mounts/Battery_Trays_C3/      ACwing_Tray_C3_T400/T800/T1200.stl
02 - Mounts/Stack_Spacers/         ACwing_Stack_Spacers_S1x4_S2x4.stl
02 - Mounts/Motor_Sleeves/         ACwing_Motor_Sleeve_x4.stl
04 - Assembly/ACwing_Mech_A/       ACwing_Mech_A.FCMacro, ACwing_Mech_A_data.json, reference/ (motors, props, leads)
```

## Large files (Git LFS)

Native CAD files and print exports are binary: they are stored with
[Git LFS](https://git-lfs.com) (rules in [`.gitattributes`](.gitattributes)).
Install it once before cloning:

```
git lfs install
```

Without Git LFS, a clone gets small pointer files in place of the models.
STEP and DXF are text and stay in plain Git, so their changes show in diffs. Renders (PNG), GLB views and
spreadsheets (XLSX) go to Git LFS as well; Markdown, CSV, JSON and the FreeCAD macros are plain text.

## Author

**Andrea Cirillo** – ACwing mechanical design.
