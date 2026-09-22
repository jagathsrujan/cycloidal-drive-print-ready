# Cycloidal Drive — Print-Ready

A 15:1 cycloidal gearbox, cleaned up in FreeCAD and exported for 3D printing.
**106 printed parts across 15 part types**, plus the purchased hardware sorted out.

The design is the [HowToMechatronics DIY Cycloidal Drive](https://howtomechatronics.com/how-it-works/what-is-cycloidal-driver-designing-3d-printing-and-testing/)
(N = 16 ring pins, R = 45 mm, Rr = 6.5 mm, E = 1.5 mm). This repo is the print-prep pass
over that CAD: the original STEP is a single flat assembly of 216 objects with no indication
of what is printable, what you have to buy, or how many of each to make.

## How it works

An eccentric cam on the input shaft drives two cycloidal disks around the inside of a ring of
16 rollers. The disk has **one fewer lobe than there are rollers** — 15 lobes against 16 rollers —
so one full turn of the cam advances the disk by exactly one lobe. That single rule gives the
whole gear ratio:

```
ratio = N / (N - 1) = 16 / 15  ->  15:1 reduction
```

Two disks run 180° out of phase to cancel the imbalance the eccentric motion creates. The
reduced rotation leaves through 6 output pins passing through holes in both disks.

The design parameters, from the article:

| | |
|---|---|
| `N` rollers | 16 |
| `R` roller pitch radius | 45 mm |
| `Rr` roller radius | 6.5 mm |
| `E` eccentricity | 1.5 mm |
| Ratio | 15:1 |
| Envelope | Ø115 mm, 109 mm long including the NEMA 17 |

The disk profile is an epitrochoid, not a circle arc — `R/(E·N)` is what shapes the lobes, and
`E` must stay below half the roller diameter or the profile folds on itself. The roller "teeth"
are ball bearings rather than printed bushings; that substitution is the whole reason a printed
version of this gearbox survives at all.

Measured on the author's build: **260 N·cm out of the gearbox from a 26 N·cm NEMA 17** — about
10× torque multiplication, roughly 66 % efficiency. It is also back-drivable.

## What's here

| Path | What it is |
|------|-----------|
| `Cycloidal Drive - PRINT READY.FCStd` | cleaned FreeCAD model, parts grouped and named |
| `STL/01_PRINT_THESE/` | 15 folders, one per printed part, quantity in the folder name |
| `STL/PRINT_LIST.md` | print list, buy list, slicer settings |
| `ASSEMBLY.md` | build order, verified stack heights, and the gotchas |
| `Cycloidal Drive - 3D Printable DIY.STEP` | the original author's CAD, unmodified |

## Print quantities

| Qty | Part | | Qty | Part |
|----:|------|-|----:|------|
| 1 | Roller Pins Housing | | 16 | Ring Pin Ø6×35 |
| 1 | Housing Lid | | 6 | Output Pin Ø6×15 |
| 2 | Cycloidal Disk | | 32 | Spacer 7 mm |
| 4 | Input Shaft (sections p1–p4) | | 16 | Spacer 3 mm |
| 1 | Output Flange Front (13 mm) | | 6 | Distance Ring 3×6 |
| 1 | Output Flange Rear (16 mm) | | 12 | Shim 1 mm × Ø6 |
| 1 | Motor Coupler | | 6 | Shim 1 mm × Ø15 |
| 1 | Motor Mount (NEMA 17) | | | |

## Buy these

44 × bearing 686-2RS (6×13×5) · 4 × 6802-2RS (15×24×5) · 2 × 6807-2RS (35×47×7) ·
1 × NEMA 17 stepper · M3/M4 bolts and heat-set threaded inserts — full quantities in
[`STL/PRINT_LIST.md`](STL/PRINT_LIST.md).

## Before you print

Set **Hole Horizontal Expansion ≈ 0.07 mm** in your slicer. Printed bores come out undersize,
and that setting is what makes the 13 mm and 24 mm bearing seats press-fit instead of either
loose or impossible. Calibrate on a test plate first.

The 16 ring pins are the only printed part taking real load. They print hollow with a 3 mm bore
on purpose — the article's build slid **3 mm metal shafts** through them, and Ø6 mm ground steel
dowel is a straight drop-in upgrade if you'd rather not print them at all. See
[`ASSEMBLY.md`](ASSEMBLY.md) for the build order and the fits that will bite you.

## Model structure

The FreeCAD file groups everything the way you'd work through it at the printer:

```
Cycloidal Drive - PRINT READY
├── 01_PRINT_THESE_3D          (15 groups, 106 parts — x{N}_{name})
└── 02_BUY_THESE_HARDWARE      (11 groups, 92 parts)
```

Geometry is untouched — every part sits exactly where it did in the original assembly, so
clearances and fits are unchanged. Only the organisation, names and visibility are new.

## Credit

Original design and CAD by [HowToMechatronics](https://howtomechatronics.com/how-it-works/what-is-cycloidal-driver-designing-3d-printing-and-testing/).
The STEP file is redistributed here unmodified for reference; check the original source for
its terms before reusing the CAD commercially.
