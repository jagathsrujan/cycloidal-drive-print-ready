# BOM — Hardware Buy List

Everything to buy for one complete gearbox (the 106 printed parts are not included — see
[`STL/PRINT_LIST.md`](STL/PRINT_LIST.md)). Prices in ₹, checked Sep 2026. **Every dimension
below was measured against `Cycloidal Drive - PRINT READY.FCStd`** — the hardware group and
every mating bore in the printed parts — so the sizes are known-good, not assumed.

## Order 1 — OnlyScrews (onlyscrews.in)

| Qty | Item | Unit ₹ | Line ₹ | Notes |
|----:|------|-------:|-------:|-------|
| 44 | 686 ZZ bearing 6×13×5 | 26.00 | 1,144.00 | 32 ring rollers + 12 output-pin bearings. CAD: Ø6 bore / Ø13 OD / 5.00 wide, stack heights 27 and 15 mm — exact |
| 4 | M3×8 socket head SS304 DIN 912 | 3.20 | 12.80 | motor → mount. Mount has the 31×31 pattern, holes measured at exactly ±15.5 |
| 4 | M3×10 socket head SS304 DIN 912 | 3.20 | 12.80 | mount → housing. Housing holes measured at exactly the 63×26 rectangle (±31.5, ±13) |
| 6 | M3×20 button head SS304 * | 2.60 | 15.60 | output roller pins (span X 93–116 in CAD). *socket head is out of stock — button head fits; socket head ₹3.80 when restocked |
| 2 | M3×30 socket head SS304 DIN 912 | 6.00 | 12.00 | clamps the 4 input-shaft sections; threads into the 2 shaft inserts (X 87–120 measured) |
| 8 | M4×40 socket head SS304 DIN 912 | 7.60 | 60.80 | housing ↔ lid. Lid has Ø4 clearance + Ø7×4 head counterbore; 40 mm shank lands exactly on the insert |
| 9 | M3×5 brass heat-set insert (3D-printing slant knurled) | 4.60 | 41.40 | output face ×6 (Ø4×5 pockets), shaft back ×2, coupler ×1. OD 4.4 vs Ø4.0 holes = correct heat-set bite. **Use 5 mm, not 6 mm — the output-face pockets are exactly 5 deep** |
| 8 | M4×6 brass heat-set insert | 3.40 | 27.20 | housing back face. CAD pocket Ø5.6 × 5–6 deep; insert OD 5.8 × 6 → fits. **Do not buy the 8 mm version — it bottoms out and sticks out** |
| 16 | M3×35 hard dowel pin (3 mm metal shaft) | 6.40 | 102.40 | slides inside the printed hollow ring pins (bore Ø3.0 × 34.8 measured) |

**Subtotal ₹1,429.00** + 18 % GST at checkout. Free shipping over ₹799.
Coupon codes seen on site: `DEEZNUTS` 5 % over ₹849 · `SCREWME10` 10 % over ₹1,599 · `LOYALSCREWER` 15 % over ₹2,999.

## Order 2 — bearings + motor (OnlyScrews doesn't stock these)

| Qty | Item | Unit ₹ | Line ₹ | Source |
|----:|------|-------:|-------:|--------|
| 4 | 6802 bearing 15×24×5 | 80.00 | 320.00 | IndiaMART — Manzil Trading, Mumbai. CAD: Ø15 journals on all 4 shaft sections, Ø24 bores in front flange + both disks + rear flange — exact |
| 2 | 6807 bearing 35×47×7 | 98.00 | 196.00 | IndiaMART — Manzil Trading, Mumbai. CAD: Ø47 × 7 seats in housing (X 85–92) and lid (119–126), Ø35 journals on both output flanges — exact |
| 1 | NEMA 17 stepper, 42-40 body, 4.2 kg-cm, Ø5 D-shaft | 549.00 | 549.00 | Amazon.in (alt: QuartzComponents ₹605). CAD mount = 31×31 + Ø22 pilot + Ø5 × 15 coupler bore — matches any standard 42-40 NEMA 17 |

**Subtotal ₹1,065.00** (IndiaMART prices typically +GST).

## Total

| | ₹ |
|---|---:|
| OnlyScrews (incl. 18 % GST) | 1,686 |
| Bearings (incl. 18 % GST) | 609 |
| Motor | 549 |
| **Total** | **≈ 2,845** |

Variants:
- Listed prices without GST: ₹2,497.
- All-online convenience route (Flipkart ZMS 6802 10-pack ₹1,499 + Amazon XERFU 6807 4-pack ₹400 instead of IndiaMART): ≈ ₹4,140.
- Optional spares (PRINT_LIST recommends): +4 × 686 bearing ≈ +₹123.

## CAD fit checks that mattered

- **686 / 6802 / 6807** measured bore-for-bore against the model: ring roller bores Ø13, output
  stack 1+5+3+5+1 = 15 mm, 6802 journals Ø15 / bores Ø24, 6807 seats Ø47 × 7 / journals Ø35.
  All exact. 686 ZZ vs the CAD's 686-2RS: same dimensions (shield vs seal), fine here.
- **M4/M3 insert lengths** were the one real trap: the CAD models the inserts as Ø5.6 × 5 (M4)
  and Ø4.0 × 5 (M3) in 5–6 mm deep pockets. Buy the 6 mm M4 and the 5 mm M3 — the longer
  versions from the first draft of this BOM would not seat.
- **Coupler insert pocket is Ø5.6** (larger than the insert) — a standard M3 heat-set insert
  sits loose there; add a drop of CA glue.
- **M3 bolts are DIN 912 socket heads** in the model (Ø5.5 head); SS304 socket heads from
  OnlyScrews are the same standard. The M3×20 button-head substitute only changes head height
  inside a counterbore that has clearance to spare.
- **3 mm shafts:** the ring pins print with a Ø3 bore and the CAD expects a 35 mm shaft — the
  M3×35 dowel pins are the OnlyScrews-friendly version of the article's "3 mm metal shaft".

## Links

- onlyscrews.in — [686 ZZ](https://onlyscrews.in/products/686-zz-deep-groove-ball-bearing-6x13x5) ·
  [M3 socket heads](https://onlyscrews.in/collections/socket-head-m3) ·
  [M4×40](https://onlyscrews.in/products/m4-x-40mm-hex-allen-socket-head-ss-304-screw-dia-4mm-length-40mm) ·
  [M3×5 inserts](https://onlyscrews.in/products/m3-x-5mm-3d-printing-brass-threaded-inserts-dia-3mm-length-5mm) ·
  [M4×6 inserts](https://onlyscrews.in/products/m4-x-6mm-brass-threaded-inserts) ·
  [M3×35 dowel pins](https://onlyscrews.in/products/m3-x-35mm-hard-dowel-pins-dia-3mm-length-35mm)
- [IndiaMART 6802 (Manzil Trading)](https://www.indiamart.com/proddetail/6802-zz-2rs-radial-deep-groove-ball-bearing-24685559033.html) ·
  [IndiaMART 6807](https://www.indiamart.com/proddetail/6807-zz-2rs-radial-deep-groove-ball-bearing-24685567673.html)
- [Amazon 6807 4-pack (alt)](https://www.amazon.in/XERFU-6807-ZZ-Pieces-Bearing/dp/B0HDR91JZ7) ·
  [Flipkart 6802 10-pack (alt)](https://www.flipkart.com/zms-6802-zz-10-piece-id-15mm-od-24mm-width-5mm-japanese-high-speed-ball-bearing-wheel/p/itm5518b389155b9) ·
  [QuartzComponents NEMA 17 (alt)](https://quartzcomponents.com/products/nema17-pr42hs40-1204af-02-4-2kgcm-stepper-motor-d-type-shaft)
