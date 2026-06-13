# 77-GHz Automotive Radar Analysis

This repository contains a technical presentation and report about a **77-GHz hybrid TDM-MIMO phased-array automotive radar**.

The project was developed for the course **Telecommunication Electronics** and is based on the analysis of a modern mm-wave radar architecture for automotive applications.

## Project Overview

The project focuses on the study of a 77-GHz automotive radar system that combines:

* Phased-array radar operation
* TDM-MIMO radar operation
* FMCW chirp generation
* Zig-zag PLL-based frequency synthesis
* LO chirp distribution to TX and RX channels
* Radar performance evaluation

The analyzed radar architecture is designed to support different automotive radar modes, including:

* Long-Range Radar, LRR
* Medium-Range Radar, MRR
* Short-Range Radar, SRR

## Main Reference Paper

The main paper analyzed in this project is:

```text
A 77-GHz Hybrid TDM-MIMO Phased-Array Radar With 186-m Detection Range and 3-cm Range Resolution
IEEE Journal of Solid-State Circuits, Vol. 60, No. 12, December 2025
```

## Key Concepts

### Automotive Radar

Automotive radars are widely used in Advanced Driver Assistance Systems, ADAS.
They are important for applications such as:

* Adaptive cruise control
* Blind spot detection
* Lane change assistance
* Collision avoidance
* Cross-traffic alert

The 77-GHz frequency band is suitable for automotive radar because it enables compact antenna arrays, high resolution and reliable operation in difficult weather and lighting conditions.

### Hybrid TDM-MIMO Phased-Array Architecture

The radar architecture combines phased-array and TDM-MIMO techniques.

In LRR mode, multiple TX channels operate together as a phased-array transmitter, increasing the effective antenna gain and improving detection range.

In SRR mode, the TX channels are activated in a time-division manner, creating a virtual antenna array and improving angular resolution.

This hybrid approach allows the same radar chip to support both long-range and short-range sensing scenarios.

## FMCW Radar Operation

The system uses FMCW radar operation, where the transmitted signal is a frequency-modulated chirp.

The range resolution depends on the chirp bandwidth:

$$
\Delta d = \frac{c}{2 BW_{chirp}}
$$

where:

* `c` is the speed of light
* `BW_chirp` is the chirp bandwidth

A larger chirp bandwidth results in better range resolution.

## Zig-Zag PLL-Based FMCW Generator

One of the most important parts of the analyzed radar is the **zig-zag PLL-based FMCW generator**.

The purpose of this circuit is to generate a wideband and highly linear FMCW chirp while keeping the effective VCO gain low.

The zig-zag tuning technique divides the total chirp bandwidth into multiple subbands.
Successive subbands use opposite tuning polarity, allowing the control voltage to remain nearly continuous during subband switching.

This reduces frequency ripple and improves chirp linearity.

## Optimal High Switching Voltage, OHSV

During subband switching, voltage jumps can appear at the VCO tuning voltage and create frequency ripple.

To reduce this effect, the paper introduces the **Optimal High Switching Voltage**, OHSV.

The main idea is to choose the switching point so that the frequency before and after the subband transition remains almost the same.

This helps maintain a continuous chirp and improves radar performance.

## LO Chirp Distribution

After the FMCW chirp is generated, it must be distributed to the TX and RX channels.

The architecture uses:

* 2:6 active I/Q splitter
* Differential grounded coplanar waveguide, GCPW
* Frequency triplers
* 1:8 Wilkinson splitter
* TX phase shifters
* OOK power amplifiers

This distribution network allows the generated chirp to drive multiple transmitter and receiver channels while supporting phased-array and TDM-MIMO operation.

## Performance Results

The analyzed radar achieves:

```text
Technology: 55-nm CMOS
Operating frequency: 77 GHz
Measured chirp bandwidth: 12.6 GHz
Maximum detection range: 186 m
Range resolution: 3 cm
Peak TX EIRP: 32 dBm
Minimum RX noise figure: 16.3 dB
```

These results show that the proposed architecture can support both long-range detection and high-resolution short-range sensing.

## Repository Structure

```text
.
├── Automotive Radar Presentation.pdf   # Presentation slides
├── Automotive Radars 77GHz.pdf         # Technical report
└── README.md
```

## Files

### Presentation

The presentation summarizes the main blocks of the radar architecture:

* Introduction to automotive radars
* Hybrid radar transceiver block diagram
* Zig-zag tuning
* Optimal High Switching Voltage
* Zig-zag PLL-based FMCW generator
* LO chirp distribution
* Experimental results

### Report

The report provides a more detailed analysis of the radar system, including the theoretical background, circuit-level explanation and performance discussion.

## Topics

* Automotive Radar
* 77-GHz Radar
* FMCW Radar
* TDM-MIMO
* Phased Array
* mm-Wave Circuits
* PLL Frequency Synthesizer
* Zig-Zag Tuning
* RF Front-End
* Telecommunication Electronics
