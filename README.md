<div align="center">

# 🎚️ High-Fidelity Audio Preamplifier

### Stereo Analog Preamplifier • MM Phono Stage • RIAA Equalization • Custom PCB

A standalone audio-electronics project covering the complete design, construction, PCB development, assembly, troubleshooting, and experimental evaluation of a high-fidelity analog preamplifier.

![Status](https://img.shields.io/badge/status-completed-success)
![Project](https://img.shields.io/badge/project-independent-blue)
![Audio](https://img.shields.io/badge/audio-stereo-orange)
![Supply](https://img.shields.io/badge/supply-%C2%B115%20V-lightgrey)
![PCB](https://img.shields.io/badge/PCB-custom-green)

**Designed and built by Stamatios Mavitzis**  
**June 2022**

</div>

---

## Overview

This project is a complete **stereo analog audio preamplifier** designed for use in a high-fidelity audio system.

It supports conventional line-level sources as well as a **moving-magnet turntable cartridge** through a dedicated phono stage with **RIAA equalization**. The design also includes adjustable gain, volume and balance controls, multiple outputs, a regulated dual-rail power supply, and a custom PCB.

The project was developed independently as a **standalone personal electronics project**. It is not associated with, submitted to, or developed on behalf of any university or academic institution.

The complete technical documentation is available in the PDF report included in this repository.

---

## Main Features

| Category | Implementation |
|---|---|
| Audio channels | Stereo |
| Phono input | Moving-magnet (MM) |
| Equalization | RIAA playback equalization |
| Line inputs | Multiple analog line-level inputs |
| Input selection | Rotary selector |
| Gain | Adjustable / selectable |
| User controls | Volume and balance |
| Outputs | Multiple line-level outputs |
| Analog supply | Regulated ±15 V |
| Grounding | Star-ground architecture |
| PCB | Custom-designed |
| Enclosure | Metal chassis |
| Signal wiring | Shielded where required |
| PCB fabrication | JLCPCB |

---

## Project Goals

The main goal was not only to reproduce a working audio circuit, but to design and integrate a complete practical preamplifier system.

Particular attention was given to:

- Low-noise analog design
- Signal integrity
- RIAA equalization
- PCB layout and component placement
- Power-supply stability
- Grounding strategy
- Crosstalk reduction
- Electromagnetic interference reduction
- Input-level matching
- Shielded signal routing
- Mechanical integration
- Troubleshooting and experimental optimization
- Reliable long-term operation

---

## System Architecture

The preamplifier is organized into several functional blocks:

```text
Turntable
   │
   ▼
RIAA Phono Stage
   │
   ├─────────────────────────────┐
   │                             │
Line Input 1 ────────────────────┤
Line Input 2 ────────────────────┤
Line Input 3 ────────────────────┤
                                 ▼
                         Input Selection
                                 │
                                 ▼
                         First Gain Stage
                                 │
                                 ▼
                          Balance Control
                                 │
                                 ▼
                           Volume Control
                                 │
                                 ▼
                         Second Gain Stage
                                 │
                                 ▼
                       Multiple Line Outputs
                                 │
             ┌───────────────────┼───────────────────┐
             ▼                   ▼                   ▼
        Power Amplifier     Active Speakers      Recorder / Test
```

The analog signal path is supplied from an independent regulated **±15 V power supply**.

---

## Circuit Design References

Several well-known circuits published by **Rod Elliott / Elliott Sound Products (ESP)** were used as references during development.

| ESP Project | Function used in this project |
|---|---|
| **Project P05** | Regulated dual-rail power supply |
| **Project 06** | MM phono preamplifier and RIAA equalization |
| **Project 88** | Balance, volume, gain and second amplification stage |

These circuits served as the basis for individual functional sections. The complete system integration, PCB organization, signal routing, grounding, mechanical construction, troubleshooting, and final implementation were developed specifically for this project.

---

## Phono Stage

The dedicated phono input is intended for a **moving-magnet cartridge**.

Because the output voltage of a turntable cartridge is much lower than that of a conventional line-level source, the phono stage performs two essential functions:

1. **Low-noise amplification** of the cartridge signal.
2. **RIAA equalization** to restore the correct playback frequency response.

The output of the phono stage is raised to approximately line level before entering the main preamplifier signal path.

---

## Main Gain and Control Stages

After input selection, the signal passes through the main active circuitry.

### First Gain Stage

The first stage provides buffering and initial amplification while maintaining suitable input and output impedances.

### Balance Control

The balance network allows the relative levels of the left and right channels to be adjusted.

### Volume Control

A stereo potentiometer controls both channels simultaneously before the second gain stage.

### Second Gain Stage

The second active stage provides additional amplification. A selectable feedback network allows different gain settings to be used to compensate for differences between connected audio sources.

---

## Power Supply

The analog electronics operate from a regulated symmetrical supply based on **ESP Project P05**.

```text
Transformer
    │
    ▼
Rectifier
    │
    ▼
Reservoir Capacitors
    │
    ├───────────────┐
    ▼               ▼
Positive          Negative
Regulator         Regulator
    │               │
    ▼               ▼
  +15 V           -15 V
    │               │
    └───────┬───────┘
            ▼
           GND
```

The dual-rail supply allows the operational amplifiers to process audio signals around the 0 V reference without requiring a virtual ground.

Local bypass and decoupling capacitors are positioned close to the active devices to improve supply stability and reduce high-frequency noise.

---

## Grounding and Noise Control

Grounding was treated as an important part of the electrical design rather than only as a PCB connection requirement.

A **star-ground architecture** was used to reduce circulating ground currents and minimize hum.

```text
Input Ground ──────────┐
Phono Ground ──────────┤
Gain Stage Ground ─────┤
Output Ground ─────────┼──► STAR GROUND POINT
Power Supply Ground ───┤
Chassis Ground ────────┘
```

The metal chassis is connected to the central grounding system so that it also acts as an electromagnetic shield.

---

## PCB Design and Manufacturing

The initial schematic and circuit-development work was carried out in **Autodesk Eagle**. The final PCB layout and manufacturing preparation were completed in **EasyEDA**.

The PCB was designed specifically for this project, with emphasis on:

- Short and controlled audio paths
- Separation of sensitive analog circuitry from the power supply
- Organized stereo-channel routing
- Local power-supply decoupling
- Ground-current control
- Mechanical accessibility of connectors and controls
- Reduced coupling between input wiring
- Practical assembly and servicing

The finished PCB was manufactured by **JLCPCB**, manually assembled, soldered, inspected, tested, and installed in the final enclosure.

---

## Practical Troubleshooting

One of the most valuable parts of the project was the transition from schematic design to a real physical audio system. Several problems only became apparent after construction and testing.

### Input Crosstalk

Signals from unselected inputs were initially detectable in the active signal path.

**Cause:** electromagnetic coupling between nearby high-impedance signal wires.

**Improvement:** the original wiring was replaced with **shielded coaxial cable**, significantly reducing coupling between inputs.

### 50 Hz Hum

A noticeable mains-frequency hum appeared during testing.

**Cause:** a mains-related wire between the chassis and power switch was routed too close to sensitive analog circuitry.

**Improvement:** the cable was physically moved away from the PCB and low-level signal paths.

### Chassis Grounding

The metal enclosure initially behaved as a floating conductive structure.

**Improvement:** the chassis was connected to the central star-ground point, improving electromagnetic shielding and reducing noise.

### Operational-Amplifier Stability

Small operating changes were observed during extended testing.

**Improvements included:**

- Additional local bypass capacitors
- Improved power-supply decoupling
- Better component placement
- Consideration of thermal behaviour

### Different Source Levels

Different line-level sources can produce noticeably different output amplitudes.

**Improvement:** selectable gain settings were implemented using different feedback-resistor combinations.

---

## Development Workflow

```text
Circuit Research
      │
      ▼
Circuit Selection
      │
      ▼
Schematic Design
      │
      ▼
Simulation / Analysis
      │
      ▼
PCB Design
      │
      ▼
PCB Manufacturing
      │
      ▼
Component Assembly
      │
      ▼
Initial Testing
      │
      ▼
Troubleshooting
      │
      ▼
Noise Optimization
      │
      ▼
Mechanical Assembly
      │
      ▼
Final Testing
```

---

## Final Result

The completed system is a functional stereo analog preamplifier capable of interfacing with:

- Moving-magnet turntables
- CD players
- DACs
- Media streamers
- Tape equipment
- Other line-level analog sources
- Power amplifiers
- Active loudspeakers
- Recording or measurement equipment

The project demonstrated that high-quality analog audio performance depends on much more than the circuit schematic alone. PCB geometry, grounding topology, cable routing, shielding, power-supply filtering, decoupling, mechanical construction, thermal behaviour, and practical troubleshooting all had a significant effect on the final result.

---

## Skills and Experience

This project provided practical experience in:

- Analog circuit design
- Audio electronics
- Operational-amplifier circuits
- RIAA equalization
- Phono preamplifiers
- Feedback networks
- Linear power supplies
- Voltage regulation
- Schematic capture
- PCB layout
- Component selection
- PCB manufacturing
- Through-hole assembly
- Soldering
- Star grounding
- Shielded audio wiring
- EMI reduction
- Crosstalk reduction
- Troubleshooting
- Audio-system integration
- Experimental testing

---

## Repository Contents

The repository contains the complete project documentation, including the main technical report:

```text
Pre_Amplifier.pdf
```

The report includes:

- System architecture
- Power-supply design
- Phono-stage design
- RIAA equalization
- Gain and control stages
- Complete schematics
- PCB design
- PCB construction
- Hardware photographs
- Final assembly photographs
- Troubleshooting procedures
- Noise-reduction modifications
- Experimental observations
- Final conclusions

---

## Tools Used

| Tool | Use |
|---|---|
| **Autodesk Eagle** | Initial schematic and circuit development |
| **EasyEDA** | Final PCB design and fabrication preparation |
| **JLCPCB** | PCB manufacturing |

---

## Acknowledgements

Special acknowledgement is given to **Rod Elliott and Elliott Sound Products** for publishing the audio circuit designs and technical material that were used as references during development.

I would also like to thank **Lukas Chevas** for his help during the project, particularly with troubleshooting, practical implementation, and optimization of the final design.

---

## Author

**Stamatios Mavitzis**  
Independent electronics project  
June 2022

---

<div align="center">

### High-Fidelity Audio Preamplifier

*Analog design • PCB development • construction • testing • troubleshooting*

</div>
