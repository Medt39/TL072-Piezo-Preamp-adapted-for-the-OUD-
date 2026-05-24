# TL072 Piezo Preamp for Oud

## Introduction

As a musician regularly performing live with an oriental music band, I constantly faced limitations in the amplified sound of my Oud when using piezoelectric pickups.

Even with active DI boxes rated at 1MΩ input impedance, the instrument often sounded thin and unnatural on stage. The low frequencies were weakened, the attack became harsh, and the overall tone lost much of the warmth and dynamic response normally present acoustically.

These issues became even more noticeable in real live environments involving long cables, mixers, audio interfaces and varying input stages.

This project started from a simple question:

> How can a piezo pickup be conditioned electronically while preserving the natural character of the instrument?

The objective was therefore not only to amplify the signal, but to design a dedicated analog front-end capable of:
- adapting the impedance correctly,
- preserving low-frequency content,
- improving signal dynamics,
- reducing unwanted artifacts,
- maintaining a more natural acoustic response.

The system was designed and analyzed using LTSpice through frequency-domain simulations, transient analysis and real audio waveform injection.

---

# Engineering Problem

Piezoelectric pickups behave as high-impedance signal sources.

When connected directly to lower impedance audio inputs, the pickup experiences a loading effect that significantly modifies its behavior. This often results in:
- bass attenuation,
- loss of body resonance,
- reduced dynamic response,
- sharper transients,
- unnatural tonal coloration.

The goal of this project was therefore to create an analog conditioning stage capable of preserving signal integrity before the audio reaches mixers, interfaces or amplification systems.

---

# Design Objectives

- Preserve low-frequency response from the piezo pickup
- Minimize loading effect through very high input impedance
- Improve overall signal clarity and dynamics
- Reduce unwanted high-frequency artifacts
- Maintain stable analog behavior in live conditions

---

# System Architecture

The circuit is based around a TL072 JFET operational amplifier configured as a multi-stage analog audio conditioning system.

The architecture includes:
- high-impedance input buffering,
- active signal conditioning,
- frequency shaping,
- virtual ground generation,
- output coupling,
- dynamic limiting experimentation.

---

# Design Choices and Technical Justification

## TL072 Operational Amplifier

The TL072 was selected because its characteristics are well suited for piezoelectric audio applications.

### High Input Impedance

Piezo pickups require extremely large input impedance values to avoid signal loading and low-frequency loss.

The TL072 uses JFET inputs, providing very high input impedance and making it suitable for preserving the natural response of acoustic instruments.

### Slew Rate Performance

Acoustic instruments generate fast transient attacks and dynamic variations.

The TL072 offers a relatively high slew rate (~13 V/µs), allowing cleaner reproduction of rapid signal changes without excessive slew-induced distortion.

### Bandwidth and Audio Behavior

Its gain-bandwidth characteristics are sufficient for audio-frequency applications while maintaining stable analog operation.

### Noise Performance

Piezo signals can be relatively weak and sensitive to external noise.

The TL072 provides low-noise operation suitable for analog audio preamplification while remaining accessible and easy to prototype.

## High-Impedance Input Network

A 10MΩ input/bias network was implemented to reduce the loading effect on the piezo source.

This helps preserve:
- low-frequency response,
- signal amplitude,
- acoustic body resonance.

## Virtual Ground Architecture

Since the system operates from a single DC supply, a virtual ground stage was implemented to bias the audio signal around mid-supply.

This approach allows proper analog processing of bipolar audio waveforms without requiring dual power rails.

## Filtering and Frequency Shaping

Filtering stages were introduced to:
- smooth harsh upper-frequency content,
- reduce unwanted noise,
- improve stability,
- produce a more natural tonal response.

## Dynamic Limiting Stage

A soft clipping stage using diode limiting was explored to study transient containment during aggressive playing conditions.

---

# Simulation and Analysis

The system was extensively analyzed under LTSpice using both frequency-domain and time-domain simulations.

## Frequency Response Analysis

AC sweep simulations were used to:
- analyze cutoff frequencies,
- evaluate filtering behavior,
- study impedance influence,
- optimize frequency response.

## Real Audio Waveform Injection

Real Oud audio waveforms were injected directly into the simulation environment.

This allowed:
- transient observation,
- dynamic response analysis,
- clipping behavior evaluation,
- realistic signal conditioning verification.

## Parametric Studies

Several parameters were varied during simulation:
- input impedance,
- feedback resistance,
- coupling capacitors,
- load resistance,
- filter capacitor values.

---

# Tools and Technologies

- LTSpice
- Analog Electronics
- Audio Signal Processing
- TL072 JFET Operational Amplifier
- Frequency Response Analysis
- Circuit Prototyping

---

# Future Improvements

- PCB layout optimization
- Balanced audio output stage
- Parametric equalization
- Embedded DSP integration
- Battery management optimization
- Multi-piezo pickup architecture
