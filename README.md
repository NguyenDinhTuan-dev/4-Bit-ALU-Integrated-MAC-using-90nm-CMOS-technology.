# 4-Bit ALU Design with Integrated MAC Unit (90nm CMOS)

![Cadence](https://img.shields.io/badge/Tool-Cadence%20Virtuoso-black?style=flat-square&logo=cadence)
![Technology](https://img.shields.io/badge/Tech-90nm%20CMOS-blue?style=flat-square)
![Type](https://img.shields.io/badge/Type-Senior%20Design%20Project-orange?style=flat-square)

## 📖 Project Overview
This project presents the design and performance evaluation of a **4-bit Arithmetic Logic Unit (ALU)** integrated with a **Multiply-Accumulate (MAC)** unit. The design utilizes **90nm CMOS technology** and is implemented at the transistor level using Cadence Virtuoso.

The project is structured hierarchically, starting from basic logic gates, building up to the ALU core, and finally integrating the MAC unit for high-speed DSP applications.

## 📂 Repository Structure
The design files are organized into three main modules corresponding to the design hierarchy:

### 1. 📁 `Logic_Gates` (Basic Building Blocks)
Contains the schematic and symbol views of the fundamental CMOS logic gates and sub-circuits used to build the larger system:
* **Basic Gates:** Inverter (NOT), NAND, NOR, AND, OR, XOR.
* **Arithmetic Cells:** Half Adder (HA), Full Adder (FA), Half Subtractor, Full Subtractor.
* **Multiplexers:** 2:1 MUX, 4:1 MUX (used for operation selection).

### 2. 📁 `Basic_ALU` (Arithmetic Logic Unit)
Contains the design of the standalone 4-bit ALU without the MAC unit:
* **Operations:** Addition (Ripple Carry Adder), Subtraction, Array Multiplication, Restoring Division.
* **Features:** Includes 4-bit parallel inputs (A, B) and a 4:1 MUX to select the output (Y).
* **Overflow Logic:** Logic circuits to detect Carry, Borrow, and Overflow conditions.

### 3. 📁 `ALU_Integrated_MAC` (Top-Level Design)
Contains the final integrated system optimized for DSP tasks:
* **MAC Unit:** Integrates a **CSA-based Array Multiplier** and an **8-bit PIPO Register** (Accumulator) with synchronous reset.
* **Function:** Performs consecutive Multiply-Accumulate operations in a single consolidated block.
* **Performance:** Optimized for delay and throughput compared to standard ripple-carry architectures.

---

## 🛠 Tools & Environment
* **Schematic Entry:** Cadence Virtuoso Schematic Editor L.
* **Simulation:** Virtuoso Visualization & Analysis (Transient Response).
* **Technology Node:** 90nm CMOS.
* **Supply Voltage:** 1.0 VDC.

## 📊 Performance Analysis
Comparative analysis between the Basic ALU and the ALU with Integrated MAC (Simulation at 50MHz):

| Metric | Basic ALU | ALU with MAC | Analysis |
| :--- | :--- | :--- | :--- |
| **Total Power** | 379.9 µW | 472.5 µW | **~24% increase** due to the addition of accumulator registers and feedback loops. |
| **Delay (MUL)** | ~415 ps | ~567 ps | Increased latency is expected due to the complexity of the MAC data path. |
| **Delay (DIV)** | ~347 ps | ~529 ps | Division remains the most timing-critical operation in both designs. |

> **Conclusion:** Although the MAC unit introduces additional power and delay, it provides essential functionality for DSP algorithms (like FIR Filters/CNNs) that require continuous accumulation, making the trade-off justified.

## 📜 References
1.  *Design of a 4-bit ALU with Integrated MAC and Performance Evaluation*, Senior Design Project Report, HCMUTE, July 2025.
2.  Neil Weste and David Harris, “CMOS VLSI Design: A Circuits and Systems Perspective”, 4th Edition.


