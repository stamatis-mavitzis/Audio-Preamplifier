# Audio Preamplifier

Design, construction, and experimental evaluation of a high-fidelity analog audio preamplifier.

This project was developed as part of my studies at the **School of Electrical and Computer Engineering, Technical University of Crete**.

The complete technical documentation, circuit diagrams, PCB layouts, construction photographs, and experimental observations are available in the project report:

📄 **[View the Full Project Report](<Pre_Amplifier(2).pdf>)**

---

## Overview

The objective of this project was to design and construct a fully functional analog audio preamplifier suitable for high-fidelity audio systems.

The system includes:

- Phono input for turntables
- RIAA equalization
- Multiple line-level inputs
- Multiple line-level outputs
- Adjustable gain
- Volume control
- Balance control
- Input selection
- Low-noise operational amplifier stages
- Regulated symmetrical power supply
- Star-ground topology
- Custom PCB design

The project combines theoretical circuit design with practical PCB development, assembly, testing, and troubleshooting.

---

## System Architecture

The preamplifier consists of several main stages:

### Power Supply

The power supply is based on **Rod Elliott's Project P05** and provides a regulated:

```text
+15 V
  0 V
-15 V
