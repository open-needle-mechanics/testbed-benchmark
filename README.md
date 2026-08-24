# testbed-benchmark
A high-precision, open-source surgical robotic testbed for needle penetration mechanics. Features passive mechanical overload protection for delicate force sensors and an ESP32-controlled environmental chamber maintaining 37°C and 98% RH to preserve tissue compliance during ex vivo trials. Fully synchronized tactile and optical data streams.
# Open-Access Benchmark Platform for Surgical Needle Mechanics

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

This repository provides the complete open-source hardware specifications, firmware, and data acquisition pipelines for a specialized testbed designed to measure needle-tissue interaction forces in surgical robotics[cite: 2].

Accurate modeling of needle penetration dynamics is critical for autonomous surgical tasks, yet high-fidelity force sensing in ex vivo tissues is constrained by sensor fragility under dynamic overload and artifacts caused by tissue desiccation[cite: 2]. This platform addresses these failure modes through an integrated design combining passive mechanical protection and active environmental control[cite: 2].

## Key Features

1. **Passive Overload Protection:** A custom-engineered shroud utilizes precise $0.50\text{ mm}$ radial and axial clearances to passively bypass destructive impact loads ($>18\text{ N}$) around sensitive multi-axis force flexures, directing excess forces directly into the primary robot flange[cite: 2].
2. **Environmental Chamber:** An active enclosure replicates *in vivo* conditions using a PID-regulated heated baseplate ($37.0^\circ\text{C} \pm 0.5^\circ\text{C}$) and an ESP32-controlled $108\text{ kHz}$ ultrasonic nebulizer, maintaining physiological tissue hydration at $98\%\text{ RH}$ without accumulating turbulent fluid[cite: 2].
3. **Hardware-Level Synchronization:** A centralized $1.0\text{ kHz}$ master TTL clock provides sub-millisecond synchronization across all sensory streams, ensuring exact temporal alignment between multi-axis force vectors, high-speed optical tracking (250 FPS), and robotic joint states[cite: 2].
4. **Validated Benchmark Performance:** The platform is validated using standardized multi-layered gelatin tissue phantoms, reliably isolating transient dynamics including peak puncture ($F_{\text{peak}} = 1.24 \pm 0.08\text{ N}$) and cutting forces ($F_{\text{cut}} = 0.42 \pm 0.04\text{ N}$)[cite: 2].

## Repository Structure

* `hardware/`: CAD models (STEP, STL), bills of materials, and assembly instructions for the protection shroud and environmental chamber[cite: 2].
* `firmware/`: ESP32 source code (PlatformIO) for the environmental chamber PID control loop and hardware synchronization timing[cite: 2].
* `data_acquisition/`: Python scripts for synchronized logging of National Instruments PCIe-6363 DAQ force streams, robotic kinematics (e.g., dVRK, UR3e), and high-speed optical tracking[cite: 2].
* `analysis/`: Feature extraction pipelines (loading slopes, $F_{\text{peak}}$ detection) used to generate the validated benchmark results[cite: 2].

## Getting Started

Refer to the [Hardware Assembly Guide](hardware/README.md) and the [System Configuration Manual](data_acquisition/README.md) for detailed setup and calibration instructions.

## Open Source Availability

All CAD designs, firmware, and software in this repository are licensed under the MIT License, supporting open replication and community contributions to standardized biomechanical datasets[cite: 2].
