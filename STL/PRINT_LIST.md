# PRINT LIST — Cycloidal Drive 15:1

From `Cycloidal Drive - 3D Printable DIY.STEP` (HowToMechatronics 15:1, N=16, R=45, Rr=6.5, E=1.5).
Cleaned model: **`Cycloidal Drive - PRINT READY.FCStd`** → group `01_PRINT_THESE_3D`.

Each folder under `01_PRINT_THESE/` is one part type; the folder name carries the quantity to print.
STLs are in **assembly orientation** — lay them flat in the slicer (see notes at the bottom).

## Print these — 106 parts across 15 folders

| Qty | Folder | Files | Notes |
|----:|--------|-------|-------|
| 1 | `x1_Roller_Pins_Housing` | `Roller_Pins_Housing.stl` | ring gear; print flat, pin bores vertical |
| 1 | `x1_Roller_Pins_Housing_LID` | `Housing_Lid.stl` | print flat; 16 pin slots must line up |
| 2 | `x2_Cycloidal_Disk` | `Cycloidal_Disk_A.stl`, `_B.stl` | the two files are the same disk within 0.1% — print 2 of either, mount 180° apart |
| 4 | `x1_Input_Shaft_SET_4_pieces` | `Input_Shaft_p1..p4.stl` | 4 different sections = one set; axis vertical if possible |
| 1 | `x1_Output_Flange_Front` | `Output_Flange_Front.stl` | 13 mm thick; print flat, pin holes vertical |
| 1 | `x1_Output_Flange_Rear` | `Output_Flange_Rear.stl` | 16 mm thick |
| 1 | `x1_Motor_Coupler` | `Motor_Coupler.stl` | match your motor's shaft flat |
| 1 | `x1_Motor_Mount` | `Motor_Mount.stl` | NEMA 17 bracket |
| 16 | `x16_Ring_Pin_6x35_hollow` | `Ring_Pin_6x35.stl` | Ø6×35, 3 mm bore; **or buy 6×35 mm steel dowels** |
| 6 | `x6_Output_Pin_6x15_hollow` | `Output_Pin_6x15.stl` | Ø6×15, 3 mm bore takes the M3×20 bolt |
| 32 | `x32_Spacer_7mm` | `Spacer_7mm.stl` | ring rollers: 7 / bearing / 3 / bearing / 7 |
| 16 | `x16_Spacer_3mm` | `Spacer_3mm.stl` | |
| 6 | `x6_Distance_Ring_3x6` | `Distance_Ring_3x6.stl` | output pin stack |
| 12 | `x12_Shim_1x6` | `Shim_1x6.stl` | output pins, 2 per pin |
| 6 | `x6_Shim_1x15` | `Shim_1x15.stl` | input shaft bearings |

106 printed parts total. The 16 ring pins are the only printed part carrying real load — if you
have Ø6 mm ground steel rod, use it instead of printing them.

## Buy these — do not print

| Qty | Part |
|----:|------|
| 1 | NEMA 17 stepper motor |
| 44 | Ball bearing 686-2RS — 6×13×5 mm (16 ring positions ×2, + 6 output pins ×2) |
| 4 | Ball bearing 6802-2RS — 15×24×5 mm |
| 2 | Ball bearing 6807-2RS — 35×47×7 mm |
| 8 | Bolt M4×40 (housing ↔ lid) |
| 6 | Bolt M3×20 (output roller pins) |
| 2 | Bolt M3×30 (clamps the 4 input-shaft sections) |
| 4 | Bolt M3×10 |
| 4 | Bolt M3×8 |
| 8 | Threaded insert M4 (heat-set) |
| 9 | Threaded insert M3 (heat-set) |

Buy spares of the 686 bearings — 44 identical small parts, some will be gritty.

## Slicer settings that matter

- **Hole Horizontal Expansion ≈ 0.07 mm** and **Horizontal Expansion ≈ 0.02 mm**. Printed holes
  come out undersize; this is what turns the bearing bores into press fits. Calibrate on a test
  plate with Ø6.0 / Ø13.0 / Ø16.0 holes before committing to the housing.
- 0.15–0.2 mm layers, 4–5 walls, 40–60 % gyroid or cubic infill for housing, lid, disks, flanges.
  100 % for the pins and spacers — they are small.
- PLA is fine for a demo; PETG/ASA lasts longer under load. Heat is what kills printed cycloidal
  drives, so keep the disks cool and use light grease.
- Orientation: disks flat on the bed (no supports), housing and lid flat with pin bores vertical,
  input shaft sections axis-vertical, flanges flat with pin holes vertical.
