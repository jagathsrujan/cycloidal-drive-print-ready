# Assembly

Build order from the [HowToMechatronics article](https://howtomechatronics.com/how-it-works/what-is-cycloidal-driver-designing-3d-printing-and-testing/),
cross-checked against the CAD in this repo. Part names match the FreeCAD groups and the
folders in `STL/01_PRINT_THESE/`.

Axial measurements below are read straight out of the model — the X axis is the gearbox axis,
motor at the back (X=20), output face at the front (X=129).

## 0. Before anything else

- **Install all heat-set inserts first.** 8 × M4 (housing back face) and 9 × M3 — 6 on the
  front output face, 2 in the back of the input shaft, 1 in the motor coupler area.
  Once the gearbox is stacked you cannot reach them.
- Chase the 6 mm pin bores in the housing and lid. This is a tight build and every bore matters.
- Test-fit a 686 bearing in a housing pin bore. Press fit, not hammer fit. If it's wrong, stop
  and fix your Hole Horizontal Expansion before printing the lid.

## 1. Ring gear — housing, pins, rollers

16 × `x16_Ring_Pin_6x35_hollow` go into the `x1_Roller_Pins_Housing`, then the rollers stack
onto each pin:

```
Spacer 7mm │ bearing │ Spacer 3mm │ bearing │ Spacer 7mm
```

That order is straight from the article, and the CAD agrees — measured spans on one pin column:

| Part | X span |
|------|--------|
| Ring Pin Ø6×35 | 88.0 → 122.8 |
| Spacer 7 mm | 92.0 → 99.0 |
| Bearing 686 | 99.0 → 104.0 |
| Spacer 3 mm | 104.0 → 107.0 |
| Bearing 686 | 107.0 → 112.0 |
| Spacer 7 mm | 112.0 → 119.0 |

27 mm of roller stack centred in the 35 mm pin, so the pin sticks out both ends. The front end
seats into the lid — that's the tight fit when you close it up.

**About the pins:** they are printed hollow with a 3 mm bore for a reason. The author wasn't
confident a plain printed pin would survive the load, so he slid **3 mm metal shafts** down the
middle of each one. Either do that, or buy **Ø6 × 35 mm ground steel dowels** and skip the
printed pins entirely. Do *not* substitute M6 bolts — they measure under 6 mm, so the bearings
wobble on them.

## 2. Input shaft

`x1_Input_Shaft_SET_4_pieces` — four sections because the cam offset makes the shaft
impossible to assemble in one piece. Each section takes a 6802 bearing and distance rings.

- Slide the sections together on **2 × M3×30** bolts. Those holes are printed deliberately
  undersize so the bolts **cut their own thread** in the plastic — that's the design, not a
  mistake. Don't drill them out. They thread into the 2 M3 inserts at the back of the input shaft
  (both at the ±4 mm offset, X=103.5).
- The **cycloidal disks have to go on during this step**, not after. The author assembled the
  shaft first, then had to tear it back down because he couldn't get the disks in afterwards.

## 3. Output shaft

6 × `x6_Output_Pin_6x15_hollow`, each drilled through with an M3×20 bolt. Same idea as the ring
rollers, tighter stack — this one fills the full 15 mm pin with zero slack:

```
Shim 1mm │ bearing │ Ring 3mm │ bearing │ Shim 1mm
```

| Part | X span |
|------|--------|
| Output Pin Ø6×15 | 98.0 → 113.0 |
| Shim 1 mm | 98.0 → 99.0 |
| Bearing 686 | 99.0 → 104.0 |
| Ring 3 mm | 104.0 → 107.0 |
| Bearing 686 | 107.0 → 112.0 |
| Shim 1 mm | 112.0 → 113.0 |
| M3×20 bolt | 93.0 → 116.0 |

## 4. Stack it into the housing

1. Press one **6807** bearing into the housing (X=88.5).
2. Lower the input + output assembly in.
3. Press the second **6807** in at the front (X=122.5).

**Disk phasing:** the two cycloidal disks sit 8 mm apart and must be **180° out of phase**. The
author put small index holes in both disks, 180° apart, so you just line them up and push the
output rollers through. Find those holes before you start — you cannot see the phase once the
disks are inside the ring.

## 5. Lid, motor mount, motor

- **Lid:** goes over all 16 pins, tight fit — expect to need some force.
- **8 × M4×40** through the lid into the M4 inserts in the back of the housing. The bolt spans
  X 84 → 128, i.e. the full housing (84→119) plus lid (119→128).
- **Motor mount:** 4 × M3×10 at X=81.5, on a 63 × 26 mm rectangle — mount to housing.
- **Motor:** 4 × M3×8 at X=63.5, on a 31 × 31 mm square — that's the standard NEMA 17 pattern.
- **Coupler:** slides over the motor shaft and bolts to the M3 inserts at the back of the input shaft.

## Gotchas worth knowing before you start

- **Don't skip the calibration plate.** 0.07 mm of Hole Horizontal Expansion is the difference
  between "press fit" and "won't go on". This gearbox is essentially a stack of fits.
- **Disks must be phased 180°** using the index holes, or the gearbox will fight itself.
- **The disks have to go on with the input shaft**, mid-assembly (see step 2).
- **Ring pins are the weak point.** Printed solid in PLA they can shear under shock; the 3 mm
  rod or steel dowel fix exists for exactly this reason.
- This thing is **back-drivable** — turning the output turns the motor.
