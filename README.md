# Wireless Power Transfer using Pulse Width Modulation (FPGA-Based)

**Contributors:**  
Ram Sampath Padala (2201EE43)  
S Akash (2201EE88)  
A Girish (2201EE06)  
Harshith Patnaik (2201EE89)  
Rushikesh Reddy (2201EE80)

## Overview

This project demonstrates the design, simulation, and partial hardware implementation of a wireless power transfer (WPT) system regulated by pulse width modulation (PWM). The project focuses on efficient and flexible control via FPGA-based digital logic and uses a series-series two-coil topology for the power transfer. All key stages – rectification, high-frequency inversion, resonant energy transfer, and regulated output – are analyzed, simulated, and described.

## Table of Contents

- [Project Highlights](#project-highlights)
- [System Architecture](#system-architecture)
- [Key Parameters](#key-parameters)
- [Simulation](#simulation)
- [FPGA PWM Generation](#fpga-pwm-generation)
- [Results](#results)
- [How to Use](#how-to-use)
- [Future Scope](#future-scope)
- [References](#references)

## Project Highlights

- **Series-series two-coil resonant WPT** for optimal cost and compact size.
- **FPGA-based digital PWM control** enabling real-time dynamic power regulation.
- **Simulink modeling** for comprehensive simulation of the circuit and system performance.
- Achieved **maximum output power of 59.87 W** at the resonant frequency of 680 kHz.
- Experimental and simulation results validated the approach.

## System Architecture

**Block Diagram Overview:**

1. **Power Input & Rectification:** AC mains are rectified to DC.
2. **Voltage Regulation:** PWM-controlled DC-DC converter adjusts voltage and power.
3. **High-Frequency Inversion:** DC is inverted to high-frequency AC using an IGBT-based inverter.
4. **Resonant Wireless Power Link:** Power is transmitted over the air via a pair of resonance-matched coils (series-series).
5. **Rectification & Output Regulation:** Received AC is rectified and stabilized for the load.
6. **FPGA PWM Control:** Duty cycle regulation is achieved via digital logic implemented on an FPGA.

## Key Parameters

| Parameter          | Value         |
|--------------------|--------------|
| Primary Inductance (L1) | 298 μH     |
| Secondary Inductance (L2) | 298 μH  |
| Primary Capacitance (C1) | 200 pF   |
| Secondary Capacitance (C2) | 200 pF |
| Coupling Coefficient (k) | 0.1      |
| Mutual Inductance (M) | 29.8 μH     |
| Parasitic Resistance (Tx) | 5 Ω     |
| Parasitic Resistance (Rx) | 2 Ω     |
| Resonant Frequency | 680 kHz       |
| Maximum Output Power | 59.87 W     |
| Input Voltage | 100 V             |

## Simulation

- The whole WPT system is modeled and tested in **Simulink**.
- Key subsystems implemented: Full-wave rectifier, PWM inverter, resonant coupled coils, and output rectifier.
- *Power vs Frequency* and *Power vs Duty Cycle* characteristic curves validated optimal operation and control strategies.
- Resonance frequency and performance aligned with theoretical predictions.

## FPGA PWM Generation

- **Duty cycle control** is implemented using an N-bit counter, comparator, and RS latch in digital logic.
- The PWM module takes ADC feedback to adjust the duty cycle according to load or power requirements (see block diagram in the report).
- Capable of real-time, high-resolution adjustments for robust operation.

## Results

- **Peak transfer efficiency** at resonance (680 kHz), with output power reaching nearly 60W.
- Dynamically tunable output by varying PWM duty cycle.
- FPGA implementation (simulated in Vivado) demonstrated reliable PWM waveforms and closed-loop control capability.

## How to Use

**Simulation:**

1. Load the Simulink model (`.slx`) or the provided schematic files.
2. Set initial parameters (as per Table I above).
3. Run the simulation; observe power transfer plots and verify resonance operation.
4. Adjust duty cycle and coupling coefficient to test dynamic behavior.

**FPGA PWM:**

1. Use provided HDL (VHDL/Verilog) code for the PWM generator.
2. Synthesize and implement on a compatible FPGA (e.g., Xilinx Spartan series).
3. Connect ADC feedback for live duty cycle adjustment (optional).

> **Note:** Hardware files and testbenches can be added as the project grows. For schematic images and more, see the PDF `EMT_project.pdf`.

## Future Scope

- **Adaptive resonance tracking** and **automatic impedance matching** for even higher efficiency under variable conditions.
- **Multi-coil and multi-receiver support** for complex wireless charging setups.
- **Integration of advanced control algorithms**, including machine learning strategies, to maximize efficiency and safety.
- **Miniaturization and ultra-high-frequency operation** for biomedical, IoT, and other compact applications.

## References

A select list; see the full report for citations:

- Smith & Doe, "Wireless power transfer: A survey of methodologies and applications", IEEE Transactions on Power Systems, 2020.
- Soljačić & Kurs, "Efficient wireless power transfer via magnetically coupled resonance", Science, 2007.
- S. Kirnapure & V. Wadhankar, “Design of pulse width modulation controller on FPGA using HDL”, IJIRCCE, 2015.


## Contact

For code contributions, suggestions, or queries, please open an issue or contact the project authors.

**Happy hacking and wireless powering!**
