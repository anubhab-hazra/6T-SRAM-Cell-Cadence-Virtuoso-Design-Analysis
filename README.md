# 6T SRAM Cell — Cadence Virtuoso Design & Analysis

Design and implementation of a **6-transistor (6T) SRAM cell** using **Cadence Virtuoso (90nm GPDK)**.  
Includes schematic design, DC and power analysis, read operations (0 and 1), and physical layout with DRC verification.

---

## 📌 Short description
This project implements a **6T SRAM cell** at the transistor level in Cadence Virtuoso.  
It covers functional simulations (hold, read, write states), DC transfer analysis, static power analysis, read 0 and read 1 operations, and layout verification.

---

## 📝 Key results
- **Schematic:** 6T SRAM cell built with cross-coupled inverters + access transistors.  
- **DC Analysis:**  
  - Obtained transfer curve for latch stability.  
  - **Butterfly curve midpoint:** ~`699.29 mV, 702.20 mV`.  
- **Power Analysis:**  
  - Static power measured.  
  - **Peak power dissipation:** ~`148.3 µW`.  
- **Read Operations:**  
  - **Read 0:** BL < BLB → output confirmed.  
  - **Read 1:** BL > BLB → output confirmed.  
- **Layout (Layout XL):** Completed SRAM layout.  
- **DRC:** Clean, no design violations.  

---

## 🛠 Tools & environment
- **Cadence Virtuoso** (schematic, symbol, simulation)  
- **Layout XL** (physical design, DRC)  
- **Spectre ADE** (DC + transient simulations, power analysis)  
- **GPDK 90nm PDK**  

---

## 📐 SRAM design overview
- **Transistor configuration:**  
  - T1–T4 → cross-coupled latch (1-bit storage).  
  - T5–T6 → access transistors controlled by **Word Line (WL)**.  
- **Bit Lines:**  
  - **BL / BLB** used for read & write operations.  
- **Operating states:**  
  1. **Hold** → Cell retains stored value.  
  2. **Read** → WL = 1, sensed via BL/BLB differential.  
  3. **Write** → WL = 1, BL/BLB forced externally.  

---

## 📊 Simulation results
- **DC Transfer Characteristics:**  
  - Stability verified with butterfly curve.  
  - Midpoint at ~`699 mV`.  
  - Confirms bistable behavior of latch.  

- **Static Power Analysis:**  
  - Power peaks at ~`148 µW`.  
  - Shows typical static consumption of 6T SRAM at 90nm.  

- **Read Operations:**  
  - **Read 0:** Q = 0, Qb = 1 → BL discharges, BLB charges → BL < BLB.  
  - **Read 1:** Q = 1, Qb = 0 → BL charges, BLB discharges → BL > BLB.  
  - Comparator (sense amp) confirms correct readout.  

