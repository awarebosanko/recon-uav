# Reaper Recon UAV

**Autonomous Detection, Mapping & Modular Flight Testbed**  
*Developed by Aiden Ware Bosanko — Mechanical Engineering, Texas A&M University*

Reaper Recon UAV is a low-cost, 3D-printed fixed-wing reconnaissance platform designed for rapid deployment in constrained environments. Built around a stretched, modified MQ-9 airframe (`@Jhonny_3159308` base), the aircraft features a standardized modular avionics sled for rapid payload swaps, autonomous ArduPilot waypoint navigation, and a live 5.8GHz FPV downlink for ground-station YOLO object detection and terrain mapping.

📄 **[Read the Full Proposal & Technical Specification (PDF)](docs/Reaper%20Recon%20UAV%20Proposal%20%26%20Technical%20Specification.pdf)**

---

## Repository Layout
* **cad/** — SolidWorks parts/assemblies (`.SLDPRT`, `.SLDASM`) and print-ready `.STL` files
* **analysis/** — eCalc propulsion trade studies, Ansys FEA, and Simcenter STAR-CCM+ CFD results
* **software/** — ArduPilot/Mission Planner parameter backups, waypoint grids, and ground-station vision/mapping scripts
* **docs/** — Technical specification PDF, living `BOM.md`, wiring diagrams, flight logs, and build media

---

## Core Hardware & Avionics Architecture

| Subsystem | Component | Key Specs / Role |
| :--- | :--- | :--- |
| **Airframe** | Custom Stretched MQ-9 | eSUN LW-PLA (body/wings), ABS (spars/mounts/gear), TPU (wheels/skid) |
| **Flight Controller** | CoreWing F405 Wing V2 | ArduPilot firmware, integrated PDB & BECs |
| **Propulsion** | X2806.5 1700KV + EMAX 50A ESC | 4S 5000mAh 40C LiPo, prop TBD via eCalc & dyno validation |
| **Navigation** | HGLRC M100-5883 | M10 GPS + QMC5883 compass |
| **Control Link** | RadioMaster RP3 V2 + Pocket | 2.4GHz ExpressLRS diversity receiver |
| **Video Downlink** | RunCam Phoenix 2 SP V3 + SpeedyBee TX800 | 5.8GHz analog FPV feed (25–800mW) to ground-station |
| **Actuators** | MG90S Metal Gear Servos | 9g, 180° control surface actuation |

---

## Project Progress & Milestones

### Phase 1: Airframe Redesign & Simulation
- [x] Baseline STL-to-SolidWorks assembly import & initial measurements
- [x] Technical specification & project scope finalized
- [ ] Stretch fuselage, extend wingspan, and design modular internal avionics sled
- [ ] Complete eCalc powertrain trade study (propeller sizing & endurance)
- [ ] Run Ansys FEA (3G maneuver & max static thrust, FoS ≥ 2) and STAR-CCM+ CFD ($C_L$, $C_D$, $L/D$)

### Phase 2: Fabrication & Propulsion Validation
- [ ] FDM 3D print airframe (LW-PLA), structural spars/mounts (ABS), and wheels/skid (TPU)
- [ ] Bench-test X2806.5 motor & candidate props on the [Motor-Dynameter](https://github.com/awarebosanko/Motor-Dynameter)

### Phase 3: Avionics & Software Integration
- [ ] Solder, harness, and balance avionics sled (CG & EMI verification)
- [ ] Configure ArduPilot parameters, failsafes, and waypoint grids in Mission Planner
- [ ] Build and bench-test ground-station video capture, YOLO detection, and map stitching

### Phase 4: Flight Testing & Autonomous Verification
- [ ] Maiden flight (Manual/FBWA), trim, and `AUTOTUNE` PID calibration
- [ ] Verify autonomous hand-launch, waypoint grid, RTL, and live ground-station detection

### Phase 5: Mission Flight & Future Platforms
- [ ] Execute end-to-end autonomous recon & terrain mapping mission
- [ ] Future upgrade: drop-in onboard companion compute (Raspberry Pi / Jetson) via modular sled
