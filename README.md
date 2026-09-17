# UART
RTL design and verification of a complete UART communication system (TX/RX) with parameterized baud rate and loopback testing in Verilog.
# UART Communication System RTL in Verilog

## Overview
This repository contains the complete RTL design and verification environment for a Universal Asynchronous Receiver-Transmitter (UART) system. The project is implemented in Verilog from scratch and includes a custom baud rate generator, transmitter (TX), receiver (RX), and a top-level integration module.

## Key Features
- **Modular Architecture:** Cleanly separated design blocks for TX, RX, and Baud Generation.
- **Robust Receiver Design:** Implements 16x oversampling and double-flop synchronization to prevent metastability and ensure accurate mid-bit sampling.
- **FSM Control Logic:** Finite State Machine (FSM) based implementation for precise serial data transmission and reception.
- **Parameterized Design:** Easily configurable system frequency and baud rate for flexible integration.
- **Comprehensive Verification:** Includes individual unit-level testbenches and a system-level loopback testbench to verify end-to-end data integrity.

## Simulation & Verification
The design has been extensively simulated and verified using **Icarus Verilog** and waveforms were analyzed in **GTKWave**. The loopback test confirms that the TX serial output is correctly sampled and reconstructed by the RX module.

### How to Run Simulation
```bash
# Compile the design and testbench
iverilog -o uart.out uart.v tx.v rx.v baud_generater.v uart_tb.v

# Run the simulation
vvp uart.out
