# Dual-Output-DC-DC-Converter-LTspice-
Dual output DC-DC converter designed and simulated in LTSpice, generating regulated positive and negative voltages with transient analysis.

Overview

This project presents the design and simulation of a dual-output DC-DC converter using the LT1945 Dual Micropower DC/DC Converter IC in LTspice.
The circuit generates:

Positive boosted output (~12V)

Negative inverted output (~ -20V)
from a single low input voltage of 3.5V, demonstrating both boost and inverting converter operation in a single IC.

Key Features

•Dual output from single input supply

•Simultaneous boost + inverting topology

•Low input voltage operation (3.5V)

•Stable outputs with feedback regulation

•Transient startup behavior analyzed

Circuit Description

Input Stage
V1 = 3.5V DC source

Supplies the LT1945 IC
Both converter channels operate from the same input

Converter 1 (Left Side – Negative Output)

Topology: Inverting DC-DC Converter

Components:

•Inductor: L1 = 10µH

•Diodes: D2, D3 (1N5819 Schottky)

•Capacitors: C1, C2 = 1µF

•Feedback Network: R1 (365K), R2 (24.9K)

•Load: 2KΩ

Operation:

When the switch turns ON → energy stored in inductor.
 When OFF → energy transferred through diode to output. Output becomes negative with respect to ground.

Result:

•Output settles around -20V  
  •Converter 2 (Right Side – Positive Output)

Components:

•Inductor: L2 = 10µH

•Diode: D4 (MBRS360)

•Capacitor: C3 = 1µF

•Feedback Network: R4 (1MΩ), R5 (115KΩ)

•Load: 1KΩ

Operation:

Inductor stores energy during ON cycle.
Releases energy to output during OFF cycle.
Output voltage boosted above input.

Result:

•Output stabilizes around 12V

•Separate feedback pins:

FB1 → Negative output regulation

FB2 → Positive output regulation

Simulation Setup

•Analysis Type: Transient (.tran 1 startup)

•Startup condition enabled to observe initial behavior

•Simulation time ≈ 10 ms

Waveform Analysis

1. Input Voltage (V(in))
Constant at 3.5V
Confirms stable supply to both converters

2. Positive Output (V(out2))
Rises quickly and stabilizes around ~12V
Small ripple present due to switching action
Indicates proper boost converter operation

3. Negative Output (V(out1))
Drops rapidly from 0V to ~ -20V
Settles after ~1 ms
Slight ripple indicates switching regulation

Key Observations

•Both outputs reach steady state quickly (< 2 ms)

•Converter operates efficiently from low input voltage

•Ripple is minimal due to output capacitors

•Independent regulation for both outputs works correctly

Applications

•Dual power supply systems (+V and –V rails)

•Analog circuits (op-amps requiring dual supply)

•Embedded systems power management

•Sensor and instrumentation circuits
