# High-Fidelity Audio Preamplifier

Design, construction, PCB development, assembly, and experimental evaluation of a **high-fidelity analog audio preamplifier** with a dedicated phono input, RIAA equalization, multiple line-level inputs, adjustable gain, volume and balance controls, and multiple line-level outputs.

The project was developed as part of my studies at the **School of Electrical and Computer Engineering, Technical University of Crete**.

The complete project is documented in the PDF report contained in this repository.

---

## Overview

The objective of this project was to design and construct a complete analog audio preamplifier suitable for use in a high-fidelity audio system.

The system accepts signals from several analog audio sources and provides the necessary signal conditioning before the signal is sent to a power amplifier, active loudspeakers, recording equipment, or another line-level audio device.

Special attention was given to:

- Low-noise analog design
- Signal integrity
- RIAA equalization
- Power-supply stability
- PCB layout
- Grounding
- Electromagnetic interference reduction
- Crosstalk reduction
- Input level matching
- Practical troubleshooting
- Mechanical integration
- Reliable long-term operation

The final result is a fully functional stereo analog preamplifier assembled on a custom-designed PCB and installed in a metal enclosure.

---

# Main Features

The preamplifier includes:

- Stereo analog audio operation
- Dedicated moving-magnet phono input
- RIAA equalization
- Multiple line-level inputs
- Input selection
- Adjustable gain
- Volume control
- Balance control
- Multiple line-level outputs
- Low-noise operational amplifiers
- Regulated dual-rail power supply
- ±15 V analog supply rails
- Additional AC supply connections for VU meters
- Decoupling and bypass capacitors
- Star-ground architecture
- Custom PCB
- Metal chassis
- Shielded signal wiring
- Practical noise and crosstalk mitigation

---

# Rod Elliott / Elliott Sound Products Designs

A significant part of the circuit architecture was developed using well-known designs by **Rod Elliott of Elliott Sound Products (ESP)** as reference designs.

The final preamplifier combines concepts and circuitry from several ESP projects rather than being based on a single design.

## Project P05 — Power Supply

The main regulated power supply is based on **Rod Elliott Project P05**.

It provides the symmetrical power rails required by the operational amplifiers:

```text
+15 V
  0 V
-15 V
```

The supply section includes:

- Full-wave rectification
- Large reservoir capacitors
- Positive voltage regulation
- Negative voltage regulation
- Protection diodes
- Local filtering
- Power indication
- Chassis-ground connection

The power supply was designed to provide stable and low-noise DC rails for the sensitive analog audio circuitry.

Additional **15 VAC connections** were also provided for the possible installation of VU meters.

---

## Project 06 — Hi-Fi Phono Preamp

The phono section is based on concepts from **Rod Elliott Project 06 — Hi-Fi Phono Preamp (RIAA Equalisation)**.

This section is intended for the very low-level signal produced by a **moving-magnet (MM) turntable cartridge**.

Because a phono cartridge produces a significantly smaller signal than a conventional line-level audio source, the phono stage must provide both:

1. Significant low-noise amplification
2. RIAA frequency-response correction

The circuit uses low-noise operational amplifiers and an RIAA feedback network to restore the original frequency response of the recorded audio signal.

The output of the phono stage is brought to approximately line level so that it can be processed by the remaining preamplifier stages.

---

## Project 88 — Audio Preamp / Control Stages

Parts of the main preamplifier signal path were based on **Rod Elliott Project 88**.

The project was used as a reference particularly for the:

- Balance control
- Volume control
- Second gain stage
- Output-stage arrangement

The balance and volume controls are positioned between the initial buffering/gain stage and the second active amplification stage.

The second stage also provides selectable gain through switchable feedback resistor combinations.

This makes it possible to modify the overall signal gain according to the connected source and required output level.

---

# System Architecture

The complete audio path can be represented approximately as:

```text
                       ┌─────────────────────┐
Turntable ────────────►│  RIAA Phono Stage   │
                       │   ESP Project 06    │
                       └──────────┬──────────┘
                                  │
                                  ▼
Line Input 1 ─────┐
Line Input 2 ─────┤
Line Input 3 ─────┼──► Input Selection
Phono Output ─────┘
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
                    ESP Project 88
                          │
                          ▼
                 Multiple Line Outputs
                          │
           ┌──────────────┼──────────────┐
           ▼              ▼              ▼
      Power Amp      Active Speakers   Recorder
```

The power supply operates independently from the signal path and supplies the active analog stages with regulated **±15 V**.

---

# Inputs

The system was designed to support several analog audio sources.

The available input architecture includes a dedicated **phono input** together with conventional **line-level inputs**.

Possible sources include:

- Turntables
- CD players
- DACs
- Media streamers
- Tape equipment
- External audio players
- Other line-level analog sources

A rotary input-selection system allows the user to select which source is connected to the main signal path.

---

# Phono Stage

One of the most important sections of the preamplifier is the dedicated phono stage.

A moving-magnet turntable cartridge produces a very small electrical signal and therefore cannot normally be connected directly to a conventional line-level input.

The phono stage performs two main functions.

## Signal Amplification

The very small cartridge voltage is amplified to a level suitable for the rest of the preamplifier.

Low-noise operational amplifiers were selected because any noise introduced at this stage will also be amplified by the following stages.

## RIAA Equalization

Vinyl records are produced using the standardized RIAA recording characteristic.

During playback, the inverse RIAA characteristic must therefore be applied.

The phono stage contains the required frequency-dependent feedback network to perform this equalization.

The resulting signal can then be treated similarly to the other line-level sources.

---

# First Gain Stage

After input selection, the audio signal passes through the first active stage.

This stage provides signal buffering and initial amplification while presenting suitable impedances to the surrounding circuitry.

The stereo channels are handled independently while maintaining an identical topology for the left and right channels.

The stage uses operational amplifiers configured for high-quality analog audio operation.

---

# Balance Control

A stereo balance control allows the user to modify the relative level between the left and right audio channels.

The implementation was inspired by the control section of **ESP Project 88**.

At the center position, both channels operate at approximately the same level.

Moving the balance control allows one channel to be attenuated relative to the other.

---

# Volume Control

The main volume potentiometer controls the amplitude of both stereo channels simultaneously.

The volume-control section is positioned before the second active gain stage.

This arrangement allows the signal level to be adjusted before the final preamplifier amplification and output distribution stages.

The volume and balance section was based on the corresponding ideas from **Rod Elliott Project 88**.

---

# Second Gain Stage

The second active stage provides additional amplification after the volume and balance controls.

A selectable feedback network allows different gain values to be selected.

The design uses switches together with different feedback resistor values, allowing the closed-loop gain of the operational amplifier to be modified.

This makes it possible to compensate for differences between connected audio sources.

The stage is implemented independently for the left and right channels.

---

# Multiple Outputs

The preamplifier provides multiple output connections.

This allows the processed audio signal to be distributed to more than one external device.

Possible applications include simultaneous connection to:

- Power amplifiers
- Active loudspeakers
- Recording equipment
- Headphone amplifiers
- Measurement equipment
- Additional audio systems

The output circuitry was designed with low output impedance so that the signal can be delivered reliably to connected equipment.

---

# Power Supply

The power supply is one of the most important parts of a low-noise analog audio system.

The circuit is based on **ESP Project P05** and generates regulated positive and negative voltage rails.

The basic power-supply architecture is:

```text
Transformer
     │
     ▼
AC Input
     │
     ▼
Rectifier
     │
     ▼
Reservoir Capacitors
     │
     ├───────────────┐
     ▼               ▼
Positive         Negative
Regulator        Regulator
     │               │
     ▼               ▼
   +15 V           -15 V
     │               │
     └───────┬───────┘
             │
            GND
```

The symmetrical supply is particularly useful for operational-amplifier circuits because the audio signal can operate around the 0 V reference without requiring a single-supply virtual ground.

---

# Power-Supply Decoupling

Power-supply filtering alone is not sufficient for a high-performance analog circuit.

Local **decoupling/bypass capacitors** were therefore installed close to the operational amplifiers.

These capacitors help:

- Reduce high-frequency power-supply noise
- Reduce parasitic oscillations
- Improve operational-amplifier stability
- Reduce interference between stages
- Provide a local transient-current source
- Improve overall signal integrity

Component placement was considered carefully so that the decoupling capacitors were physically close to the power pins of the active devices.

---

# PCB Design

After completing the circuit design, the project was transferred to a custom printed circuit board.

The initial electronic design was developed using **Autodesk Eagle**, while the final PCB development and preparation were completed using **EasyEDA**.

The PCB was designed specifically for this project.

Particular attention was given to:

- Component placement
- Signal routing
- Power routing
- Ground routing
- Stereo-channel organization
- Separation of sensitive signals
- Short signal paths
- Power-supply isolation
- Reduction of electromagnetic interference
- Reduction of ground loops
- Mechanical accessibility of connectors and controls

The final board was manufactured by **JLCPCB**.

---

# PCB Organization

The board is divided into several functional areas.

The main sections include:

```text
┌─────────────────────────────────────────────────────┐
│                                                     │
│   Inputs            Gain / Controls        Outputs │
│                                                     │
│        Phono Stage        Gain Stage                │
│                                                     │
│                                                     │
│              Power Supply Section                   │
│                                                     │
└─────────────────────────────────────────────────────┘
```

The power-supply circuitry was intentionally grouped separately from the most sensitive signal-processing sections.

The phono circuitry was also treated carefully because of the extremely small signal levels involved.

---

# Grounding Strategy

Grounding is especially important in analog audio systems.

Poor grounding can create:

- Ground loops
- 50 Hz hum
- Buzzing
- Signal interference
- Channel crosstalk
- Oscillation
- Increased noise floor

For this reason, the project uses a **STAR grounding architecture**.

---

## Star Ground

In a star-ground configuration, the ground connections from different parts of the circuit are routed toward a common central reference point instead of forming uncontrolled loops.

Conceptually:

```text
Input Ground ──────────┐
Phono Ground ──────────┤
Gain Stage Ground ─────┤
Output Ground ─────────┼──► STAR GROUND POINT
Power Supply Ground ───┤
Chassis Ground ────────┘
```

This technique was used throughout the PCB and final assembly.

The metal chassis was also connected to the central grounding system.

---

# Mechanical Construction

After PCB fabrication, the electronic components were assembled and soldered onto the board.

The completed electronics were then integrated into a metal enclosure.

The front-panel controls include the required user controls for operating the preamplifier, including functions such as:

- Input selection
- Volume
- Balance
- Gain-related control

The metal chassis also provides mechanical protection and electromagnetic shielding for the analog electronics.

---

# Troubleshooting and Experimental Optimization

Building a practical analog audio circuit revealed several issues that were not necessarily apparent during schematic design.

A significant part of the project therefore involved identifying and correcting real-world problems.

---

## Input Crosstalk

During initial testing, signals from inputs that were not selected could still be detected in the active signal path.

### Cause

The problem was associated with insufficient shielding and electromagnetic coupling between nearby signal wires.

High-impedance and low-amplitude audio lines are particularly vulnerable to this type of coupling.

### Solution

The original signal wiring was replaced with **shielded coaxial cable**.

This significantly reduced unwanted coupling between neighboring inputs.

---

# 50 Hz Hum

A noticeable **50 Hz buzzing/hum** was detected during testing.

The frequency indicated that the interference was associated with the mains power system.

### Cause

A mains-related power wire between the chassis and the power switch was routed too close to sensitive analog sections of the PCB.

The alternating electromagnetic field generated by the cable could therefore couple into the audio signal path.

### Solution

The cable was physically moved farther away from the PCB and sensitive signal lines.

This reduced the induced 50 Hz interference.

---

# Chassis Grounding

Another source of noise was related to the metal enclosure.

Initially, the chassis was not correctly integrated into the grounding architecture.

### Problem

A floating metal enclosure can act as an antenna and allow electromagnetic interference to couple into sensitive audio circuitry.

### Solution

The chassis was connected to the central **star-ground point**.

This improved shielding and reduced unwanted noise.

---

# Operational-Amplifier Stability

During prolonged operation, small changes in the operating conditions of some operational amplifiers were observed.

These were associated with thermal and supply-related effects.

### Improvements

The design was improved by:

- Adding bypass capacitors near the operational amplifiers
- Improving power-supply decoupling
- Considering component placement
- Improving thermal behavior

These modifications helped increase the stability of the circuit.

---

# Different Source Levels

Not every audio source produces the same output voltage.

For example, different CD players, DACs, streamers, and other devices may have different nominal line levels.

Without compensation, switching between inputs can therefore produce significant changes in perceived volume.

### Solution

Selectable gain settings were incorporated into the gain stage.

Different feedback resistance values can be selected, allowing the amplifier gain to be adjusted according to the required signal level.

---

# Design Considerations

Several analog design principles influenced the final implementation.

## Low-Noise Design

Noise performance is particularly important in the phono stage because the input signal is very small.

Low-noise operational amplifiers, careful grounding, shielding, and appropriate PCB routing were therefore used.

## Signal Integrity

Audio signal paths were kept as controlled as possible.

Unnecessary cable lengths and loops were minimized.

## Power Integrity

A regulated dual-rail supply and extensive local bypassing were used to reduce power-related interference.

## Channel Separation

The left and right channels were routed separately to reduce channel interaction and preserve the stereo image.

## Electromagnetic Compatibility

Sensitive signal wiring was kept away from mains and higher-current power-supply wiring whenever possible.

---

# Software Used

Two main electronic-design applications were used during development.

### Autodesk Eagle

Eagle was used during the initial schematic and circuit-development process.

### EasyEDA

EasyEDA was used for the final PCB design and preparation of the files required for fabrication.

---

# PCB Manufacturing

After the layout was completed and checked, the board was submitted for professional fabrication.

The PCB was manufactured by:

**JLCPCB**

The manufactured PCB was then manually populated, soldered, inspected, tested, and integrated into the final enclosure.

---

# Development Process

The development process can be summarized as:

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

# Project Results

The final result was a functional analog stereo audio preamplifier capable of interfacing with both conventional line-level equipment and moving-magnet turntables.

The project demonstrated the practical importance of areas that extend beyond schematic design alone.

These included:

- PCB geometry
- Grounding topology
- Wire placement
- Cable shielding
- Power-supply filtering
- Decoupling
- Mechanical construction
- Thermal behavior
- Input matching
- EMI reduction
- Troubleshooting techniques

The completed system successfully combined several analog subsystems into a single integrated audio device.

---

# Skills Developed

This project provided practical experience in:

- Analog circuit design
- Audio electronics
- Operational amplifiers
- RIAA equalization
- Phono preamplifiers
- Active gain stages
- Feedback networks
- Linear power supplies
- Voltage regulation
- PCB schematic capture
- PCB layout
- PCB manufacturing
- Component selection
- Through-hole assembly
- Soldering
- Signal grounding
- Star-ground techniques
- EMI reduction
- Crosstalk reduction
- Shielded wiring
- Electronic troubleshooting
- Audio-system integration
- Experimental testing

---

# Repository Contents

The repository contains the complete technical report:

```text
Pre_Amplifier.pdf
```

The PDF includes:

- Project introduction
- System architecture
- Power-supply design
- ESP Project P05-based power supply
- Power-supply decoupling
- Phono-stage design
- ESP Project 06-based RIAA stage
- Gain-stage design
- ESP Project 88-based control and amplification sections
- Complete circuit schematics
- PCB top-layer design
- PCB bottom-layer design
- PCB construction
- Hardware photographs
- Final assembly photographs
- Troubleshooting procedures
- Noise-reduction modifications
- Experimental observations
- Final conclusions

---

# References and Design Inspiration

The preamplifier incorporates and adapts concepts from several projects published by **Rod Elliott / Elliott Sound Products (ESP)**.

| ESP Project | Use in This Project |
|---|---|
| **Project P05** | Regulated dual-rail power supply |
| **Project 06** | Hi-Fi phono preamplifier and RIAA equalization |
| **Project 88** | Balance control, volume control, gain and second amplification stage |

These designs were used as reference circuits and were integrated into a custom overall implementation.

The PCB layout, subsystem integration, signal routing, grounding architecture, component arrangement, construction, and final implementation were developed specifically for this project.

---

# Author

**Stamatios Mavitzis**

School of Electrical and Computer Engineering  
Technical University of Crete

**June 2022**

---

# Acknowledgements

Special acknowledgement is given to **Rod Elliott and Elliott Sound Products** for publishing the audio circuit designs and technical material used as references during the development of this project.

The final system combines ideas from **ESP Project P05, Project 06, and Project 88** into a custom preamplifier implementation.

The project was also developed with the guidance of postgraduate student **Loukas Chevas**, whose assistance contributed to the troubleshooting and optimization of the final design.
