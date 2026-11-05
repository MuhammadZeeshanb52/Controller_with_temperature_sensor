# Automatic Fan Controller with Temperature Sensor

An analog temperature-controlled fan switch designed to manage component heating in electrical equipment, heatsinks, and home automation systems[cite: 9, 10]. The system continuously senses environmental or component temperature and automatically toggles the cooling fan based on a customizable temperature threshold[cite: 6, 10].

---

## 📌 Features
- **Supply Voltage:** 5V to 12V DC[cite: 9]
- **Current Capacity:** Up to 1A continuous (Maximum load peak: 4A)[cite: 9]
- **Temperature Threshold:** Adjustable from 10°C to 100°C using an on-board multiturn trimmer potentiometer[cite: 9]
- **Visual Indicator:** On-board LED for output status indication[cite: 5, 6]
- **Compact Hardware:** Custom PCB designed in Altium Designer with a custom 3D enclosure designed in SolidWorks[cite: 7, 8]

---

## ⚙️ Circuit & Working Principle
1. **Sensing & Comparison:** The circuit utilizes an LM358 op-amp (U1) configured as a voltage comparator[cite: 6]. One input takes readings from the temperature sensor, while the other connects to a 2K potentiometer (R2) to set the reference temperature[cite: 5, 6].
2. **Switching Mechanism:** When the sensed temperature exceeds the threshold set by R2, the LM358 output goes `HIGH`, turning on the gate of an **Si2302DS MOSFET (Q1)** to activate the fan[cite: 6].
3. **Protection & Filtering:** A 4.7V Zener diode (D2) and resistor (R3) protect the gate from overvoltage[cite: 6]. Capacitors C1 and C2 act as bypass capacitors for noise reduction, while C3 suppresses switching noise[cite: 6].

---

## 🛠️ Bill of Materials (BOM)

| Component | Value / Description | Footprint / Package | Quantity |
| :--- | :--- | :--- | :--- |
| **U1** | LM358 Op-Amp IC | SOIC8[cite: 10] | 1[cite: 10] |
| **Q1** | Si2302DS MOSFET | SOT-23[cite: 10] | 1[cite: 10] |
| **P1, P3** | Fan & Power Terminals | XH-2P 2.54mm[cite: 10] | 2[cite: 10] |
| **P2** | Sensor Terminal | XH-3P 2.54mm[cite: 10] | 1[cite: 10] |
| **R2** | 2K Multiturn Potentiometer | 3296W Trimmer[cite: 10] | 1[cite: 10] |
| **R1, R5** | 10K Resistor | 0805[cite: 10] | 2[cite: 10] |
| **R3, R4** | 470R Resistor | 0805[cite: 10] | 2[cite: 10] |
| **C1** | 100nF - 50V Ceramic Capacitor | 0805[cite: 8, 10] | 1[cite: 8, 10] |
| **C2, C3** | 10uF - 16V Capacitor | 0805/SMD[cite: 8, 10] | 2[cite: 8, 10] |
| **D1** | 1N4007 Diode | SMA (DO-214AC)[cite: 8, 10] | 1[cite: 8, 10] |
| **D2** | 4.7V Zener Diode | SOD-80D2[cite: 8, 10] | 1[cite: 8, 10] |
| **D3** | Red Status LED | 0805[cite: 10] | 1[cite: 10] |

---

## 📐 Enclosure Specifications
- **CAD Software:** SolidWorks[cite: 8]
- **Base Dimensions:** 30mm x 19mm[cite: 8]
- Designed with custom cutouts and precise clearance to house the assembled PCB[cite: 8].

---

## 📂 Repository Structure
```text
├── Schematic/        # Altium schematic files & PDFs
├── PCB/              # Gerber files & PCB design files
├── Enclosure/        # SolidWorks 3D CAD models (.SLDPRT / .STEP)
└── README.md         # Project documentation
