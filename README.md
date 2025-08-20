# 6T SRAM Cell — Cadence Virtuoso Design & Analysis

Design and implementation of a **6-transistor (6T) SRAM cell** using **Cadence Virtuoso (90nm GPDK)**.  
Includes schematic design, transient/DC simulations, read operations (0 and 1), power analysis, and physical layout with DRC verification.

---

## 📌 Short description
This project implements a **6T SRAM cell** at the transistor level in Cadence Virtuoso.  
It covers functional simulations (hold, read, write states), DC analysis, read 0 and read 1 operations, and layout verification.  

---

## 📝 Key results
- **Schematic:** 6T SRAM cell built with NMOS + PMOS transistors.  
- **DC Analysis:** Obtained **DC transfer characteristics** (stability check).  
- **Power Analysis:** Estimated static power dissipation.  
- **Read Operations:**  
  - **Read 0:** Simulated schematic + transient graph (BL < BLB).  
  - **Read 1:** Simulated schematic + transient graph (BL > BLB).  
- **Layout (Layout XL):** Completed SRAM layout.  
- **DRC:** Clean, no design violations.  

---

## 🛠 Tools & environment
- **Cadence Virtuoso** (schematic, symbol, simulation)  
- **Layout XL** (physical design, DRC)  
- **Spectre ADE** (DC + transient simulations)  
- **GPDK 90nm PDK**  

---

## 📐 SRAM design overview
- **Transistor composition:**  
  - T1–T4 → Cross-coupled latch (1-bit storage)  
  - T5–T6 → Access transistors controlled by **Word Line (WL)**  
- **Bit Lines:**  
  - **BL / BLB** used for read & write operations  
- **Operating states:**  
  1. **Hold** → Cell retains stored value (no read/write)  
  2. **Read** → WL high, cell value sensed via BL/BLB  
  3. **Write** → BL/BLB forced, WL high  

---

## 📊 Simulation results
- **DC Graph:** Shows inverter transfer characteristics and cell stability.  
- **Read 0:**  
  - Condition: Q = 0, Qb = 1  
  - Result: BL < BLB → Read 0 confirmed  
- **Read 1:**  
  - Condition: Q = 1, Qb = 0  
  - Result: BL > BLB → Read 1 confirmed  
- **Power:** Static power measured during hold state.  

---

## 📂 Repository structure (recommended)
