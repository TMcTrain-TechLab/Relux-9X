# RELUX-9X // Autonomous Additive Manufacturing Cell

[![YouTube](https://shields.io)](https://youtube.com) ; 
[![Klipper](https://shields.io)](https://klipper3d.org) ; 
[![Home Assistant](https://shields.io)](https://home-assistant.io) ; 
[![License: GPL v3](https://shields.io)](https://gnu.org)

> **No belts. No lead screws on X/Y. Pure magnetic reluctance and automated tool-changing.**

Welcome to the official open-source repository of the **Relux-9X** by **TMcTrain TechLab**. This project documents the ground-up engineering of a fully enclosed, beltless, multi-toolhead 3D printing cell designed for high-speed, continuous serial production of engineering-grade composites (`ABS-CF`, `ASA-GF`, `PA-CF`).

---

## 🔗 Ecosystem Repositories

To keep the hardware and firmware modular for community builders, the sub-systems of the **Relux-9X** are maintained in dedicated repositories:

* **[DIY-LMD-Drive](https://github.com)** — Custom-wound copper coils, Halbach permanent magnet arrays (`Q-15-04-04-MN`), and `B-G431B-ESC1` Field-Oriented Control (FOC) configurations for X/Y linear motion.
* **[Relux-TC](https://github.com/TMcTrain-TechLab/Relux-TC)** — High-speed Klipper toolchanger inspired by the YUDX architecture, featuring `HGX-Lite` extruder gears, dual filament cutters, and Pogo-Pin toolhead PCBs.

---

## ⚙️ Core Architecture

* **Beltless X/Y Kinematics:** Driven by custom Linear Magnetic Drives over heavy-duty `MGN12H` Y-rails (2040 aluminum extrusions) and a featherweight dual-rail `MGN12C` carbon-fiber X-gantry.
* **Planar & Non-Planar Tilt Z-Axis:** Fixed toolhead plane (`Z = 0`). A heavy-duty 400×400 mm aluminum bed lifted by 4× 12 mm ball screws driven by water-cooled NEMA17 steppers with 50:1 self-locking worm gears. Supports dynamic bed tilting for non-planar slicing and automated gravity part ejection through a motorized front door.
* **10-Slot Toolchanger Array:** Engineered for **9 active filament toolheads** plus 1 reserved experimental slot (`[TOOL_X // RESTRICTED]`). Designed for self-replication—starting with 1 toolhead to print its own upgrades and docks.
* **Modular Smart AMS (Up to 32 Spools):** Scalable 4×4 drybox sub-units featuring active chamber heating, high-torque autoloading steppers, hardwired USB-serial RFID spool tracking (Spoolman integration), and dual-status NeoPixel indicators.
* **Thermal & Air Management:** 230V AC silicone bed heater with a 6-point thermistor telemetry matrix and a lower GFK heat shield protecting lightweight carbon/polymer stabilization rods. Includes dual liquid-cooling loops and a 5-fan HEPA/carbon filtration stack with a servo-actuated bypass damper.
* **SCADA Control & Edge AI:** Powered by an Intel N350 host running Klipper, Moonraker, Dockerized Home Assistant (3-tab custom 10" tablet UI), dual top/bottom enclosure safety interlocks, and a Google Coral Edge TPU for visual/acoustic defect detection.

---

## 🚀 Build Roadmap & Status

- [x] **Phase 0:** Structural CAD layout (`2020R90` frame) & FOC driver board acquisition (`B-G431B-ESC1`)
- [ ] **Phase 1:** Y-Axis 2040 workbench testbed & Halbach array assembly (*"And it moves!"*)
- [ ] **Phase 2:** Black aluminum enclosure, dual-sensor safety interlocks & chamber lighting (*"Es werde Licht"*)
- [ ] **Phase 3:** Carbon-fiber X-gantry, 50:1 worm-gear Z-bed & first toolhead self-replication
- [ ] **Phase 4:** Modular 4×4 RFID drybox expansion & 3-tab Home Assistant SCADA dashboard
- [ ] **Phase 5:** Automated motorized door ejection & `Tool X` reveal

---

## 📂 Repository Structure

*(Directories will be populated as each mechanical and electronic stage is validated on YouTube)*

```text
├── CAD/                 # SolidCraft STEP files, enclosure brackets & assembly jigs
├── Electronics/         # Main cabinet wiring diagrams, 230V SSR schematics & safety loops
├── Klipper/             # printer.cfg, differential Z-tilt kinematics & non-planar macros
├── HomeAssistant/       # 3-tab Lovelace SCADA dashboard YAML, Spoolman RFID scripts & interlocks
└── BOM/                 # Verified Bill of Materials & sourcing links
```

---

## ⚠️ Safety Notice

This project involves **high-current DC linear drives**, **230V AC mains voltage** (heated bed), and **strong neodymium magnets**. Always implement proper thermal fuses, physical safety interlocks (dual top/bottom door switches), and protective gear when assembling Halbach arrays or energizing unshielded coils.

---

## 📜 License & Contact

This project is open-source and licensed under the **GNU General Public License v3.0 (GPL-3.0)** — see the [LICENSE](LICENSE) file for details.

* **YouTube:** [TMcTrain || TechLab](https://www.youtube.com/@TMcTrainTechLab)
* **Discord:** `@TMcTrain`
* **Business & Sponsorship Inquiries:** `tmctrain.techlab@gmail.com`
