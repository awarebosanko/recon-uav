# Propulsion Trade Study (eCalc propCalc)

## Baseline Simulation Parameters
* **Airframe:** Baseline MQ-9 CAD (`1082 mm` wingspan, `19.18 dm²` wing area, `1400 g` est. AUW)
* **Motor:** X2806.5 1700KV (45 mΩ internal resistance, 1.9 A @ 10 V no-load, 14P, 48 g)
* **ESC / Battery:** EMAX 50A ESC | 4S 5000 mAh LiPo (85% usable capacity)
* **Environment:** 250 m ASL, 25 °C (standard Texas field conditions)

---

## Propeller Sweep Results (APC Electric E)

| Prop | Max Current | Electric Power (WOT) | Static Thrust | T/W Ratio | Pitch Speed | Mixed Flight Time | Est. Motor Temp (WOT) | Specific Thrust | Status |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **6x4** | 21.15 A | 306 W | 1,166 g | 0.83 : 1 | 84 mph | 17.3 min | 88 °C | 3.32 g/W | **Finalist** — Highest endurance & lowest thermal load |
| **7x4** | 33.00 A | 472 W | 1,638 g | 1.17 : 1 | 79 mph | 13.7 min | 118 °C | 3.47 g/W | **Finalist** — Peak efficiency & strong hand-launch |
| **7x5** | 38.43 A | 546 W | 1,930 g *(1,570 g stalled)* | 1.38 : 1 | 96 mph | 13.1 min | 137 °C | 2.88 g/W | **Rejected** — Static blade stall & efficiency drop |
| **8x4** | 47.00 A | 662 W | 2,093 g | 1.49 : 1 | 73 mph | 11.4 min | 174 °C | 3.16 g/W | **Rejected** — Near 50A ESC limit & critical overheat |
| **9x4.5** | 66.02 A | 910 W | 2,657 g | 1.90 : 1 | 73 mph | 9.6 min | 286 °C | 2.92 g/W | **Rejected** — Exceeds ESC (50A) & motor (900W) limits |

---

## Engineering Conclusions & Next Steps
1. **Hardware Protection:** Simulation immediately flagged the initially procured `9x4.5` prop as unsafe on 4S (66 A draw, 286 °C predicted case temp), preventing an ESC/motor failure on the test stand.
2. **Thermal & Endurance Context:** eCalc's temperature figures assume continuous 100% static throttle (0 mph airspeed). Fixed-wing cruise (~35–40 mph at 30–40% throttle) draws ~10–12 A, keeping motor temperatures well within safe limits and yielding **21–25 min** real-world endurance on the 4S 5000 mAh pack.
3. **Empirical Validation:** Both **APC 6x4E** and **APC 7x4E** propellers have been procured for Phase 2 static thrust, current, and IR thermal verification on the [Motor-Dynameter](https://github.com/awarebosanko/Motor-Dynameter).
