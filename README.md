# 4-Bit ALU Design with Integrated MAC Unit (90nm CMOS)

![Cadence](https://img.shields.io/badge/Tool-Cadence%20Virtuoso-black?style=flat-square&logo=cadence)
![Technology](https://img.shields.io/badge/Tech-90nm%20CMOS-blue?style=flat-square)
![Type](https://img.shields.io/badge/Type-Senior%20Design%20Project-orange?style=flat-square)

## 📖 Project Overview
[cite_start]This project presents the design and performance evaluation of a **4-bit Arithmetic Logic Unit (ALU)** integrated with a **Multiply-Accumulate (MAC)** unit[cite: 559]. The design targets digital signal processing (DSP) applications where repeated multiplication and accumulation are critical (e.g., filtering, convolution).

The system performs basic arithmetic operations (ADD, SUB, MUL, DIV) and specialized MAC operations. [cite_start]The circuit is implemented at the **transistor level** using **90nm CMOS technology** in **Cadence Virtuoso**[cite: 539, 549].

## ⚙️ Architecture & Features
The design is divided into two main processing architectures compared in this study:

### 1. Basic ALU Core
* **Operations:** Addition, Subtraction, Multiplication (Array Multiplier), Division (Restoring Divider).
* [cite_start]**Architecture:** Modular design with a 4:1 Multiplexer output selection[cite: 854, 859].
* [cite_start]**Overflow Detection:** Logic-based detection for Carry, Borrow, and Multiplication/Division overflow[cite: 866].

### 2. MAC Unit (Multiply-Accumulate)
* [cite_start]**Core Component:** CSA-based Array Multiplier (Carry Save Adder) for high-speed partial product summation[cite: 882].
* [cite_start]**Accumulator:** Synchronous 8-bit Register (PIPO) with Reset to store cumulative results[cite: 894].
* [cite_start]**Optimization:** Uses CSA to reduce critical path delay during the accumulation stage compared to ripple carry adders[cite: 903].

## 🛠 Tools & Environment
* **Schematic Entry:** Cadence Virtuoso Schematic Editor L.
* **Simulation:** Virtuoso Visualization & Analysis (Transient Response).
* **Calculation:** Microsoft Excel (Power & Delay analysis).
* [cite_start]**Operating Frequency:** 50 MHz[cite: 978].
* **Supply Voltage (VDC):** 1.0V.

## 📂 Repository Contents
* `Report/`: Full technical report (PDF) containing theoretical frameworks and block diagrams.
* `Schematics/`: Screenshots of the transistor-level and gate-level schematics from Cadence.
* `Waveforms/`: Simulation results validating operation logic (ADD, SUB, MAC operations).

## 📊 Performance Analysis
[cite_start]We conducted a comparative analysis between the **Basic ALU** and the **ALU with Integrated MAC** to evaluate the trade-offs in Power and Delay (Simulation at 50MHz, 90nm node)[cite: 983, 998].

### 1. Power Consumption Comparison
| Design Variant | Dynamic Power | Static Power | **Total Power** | Increase |
| :--- | :--- | :--- | :--- | :--- |
| **Basic ALU** | 219.2 µW | 160.7 µW | **379.9 µW** | - |
| **ALU with MAC** | 239.7 µW | 232.8 µW | **472.5 µW** | +24.37% |

> [cite_start]**Analysis:** The MAC integration increases total power by **~24%**[cite: 1002]. This is an acceptable trade-off given the capability to perform complex DSP operations in a single consolidated block.

### 2. Critical Path Delay (Multiplication/MAC)
| Operation | Basic ALU Delay | ALU with MAC Delay | Note |
| :--- | :--- | :--- | :--- |
| **Multiplication** | ~415 ps | ~567 ps | [cite_start]Increased due to accumulation logic overhead[cite: 987]. |
| **Division** | ~347 ps | ~529 ps | |

> [cite_start]**Conclusion:** While the MAC unit introduces additional latency and power consumption due to hardware complexity, it significantly enhances functional density, enabling efficient **Consecutive Multiply-Accumulate** tasks essential for filters (FIR/IIR) and Neural Networks[cite: 994].

## 📉 Simulation Waveforms
*(Upload your simulation images here)*

* **Fig 1:** Basic ALU Operations (ADD/SUB/MUL) - Verified correct logic.
* [cite_start]**Fig 2:** MAC Unit Operation - Demonstrating successful accumulation of products over multiple clock cycles[cite: 933].

## 📜 References
1.  [cite_start]*Design of a 4-bit ALU with Integrated MAC and Performance Evaluation*, Senior Design Project Report, HCMUTE, July 2025[cite: 558].
2.  [cite_start]M. Sai Kumar et al., "Design and performance analysis of Multiply-Accumulate (MAC) unit," ICCPCT-2014[cite: 1025].

---
<p align="center">
  <i>Implemented by Nguyen Dinh Tuan & Nguyen Dac Gia Huy - HCMUTE</i>
</p>
