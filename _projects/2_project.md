---
layout: page
title: "DC–AC Energy-Storing Full-Bridge Power Converter"
description: "Design and simulation of a cascaded DC–DC + DC–AC converter with PI control, unipolar PWM, and 3 kW power delivery."
img: assets/img/projects/converter/system_overview.png
importance: 2
category: work
---

## Overview

This project implements a **two-stage power converter** consisting of a DC–DC boost converter and a DC–AC full-bridge inverter.  
A cascaded PI control architecture regulates the DC-link voltage while a current-mode inverter delivers a clean sinusoidal AC output to the grid.

The system was modeled and simulated in **PLECS/Simulink**, achieving the design requirement of **3 kW regulated output power** with stable current and voltage regulation.

---

## System Architecture

A full schematic of the converter is shown below:

{% include figure.liquid path="assets/img/projects/converter/system_overview.png" title="Full DC–DC + DC–AC Converter Topology" class="img-fluid rounded z-depth-1" %}

The design consists of:

- **Boost Converter (300 V → ~700 V DC-link)**  
- **Cascaded PI control** (outer voltage loop, inner current loop)  
- **Full-bridge inverter** driven by unipolar PWM  
- **LCL output filtering** for grid-quality AC injection  

---

## DC–DC Converter Control

The DC–DC stage uses a cascaded control structure:

{% include figure.liquid path="assets/img/projects/converter/boost_control.png" title="Cascaded PI Control for Boost Converter" class="img-fluid rounded z-depth-1" %}

- The **outer voltage loop** maintains the DC-link at ~700 V  
- The **inner current loop** ensures fast current dynamics  
- A triangular-wave comparator generates the PWM duty cycle  

This structure provides fast transient performance and excellent disturbance rejection.

---

## DC–DC Performance

The converter was tested under dynamic changes in the voltage reference.  
The inductor current and capacitor voltage track their references cleanly and without oscillation:

{% include figure.liquid path="assets/img/projects/converter/boost_response.png" title="Boost Converter Response: Inductor Current and Output Voltage" class="img-fluid rounded z-depth-1" %}

This confirms stable PI tuning and proper energy transfer into the DC-link capacitor.

---

## DC–AC Modulation Strategy

The full-bridge inverter uses **unipolar PWM**, which reduces harmonic distortion and switching losses compared to bipolar control.

{% include figure.liquid path="assets/img/projects/converter/unipolar_pwm.png" title="Unipolar PWM Gate Signal Generation" class="img-fluid rounded z-depth-1" %}

Two carrier comparisons produce four complementary gating signals, enabling smoother AC output waveform shaping.

---

## AC Output Performance

The regulated AC current and grid voltage demonstrate correct sinusoidal operation and proper phase alignment:

{% include figure.liquid path="assets/img/projects/converter/ac_output.png" title="AC Output Current and Grid Voltage" class="img-fluid rounded z-depth-1" %}

This verifies that the full-bridge inverter and LC filters generate clean output suitable for grid connection.

---

## Power Delivery

The complete converter meets the **3 kW power requirement**, stabilizing at approximately **2980–3000 W**:

{% include figure.liquid path="assets/img/projects/converter/power_output.png" title="Output Power of the Full Converter System" class="img-fluid rounded z-depth-1" %}

This confirms that both the DC–DC and DC–AC stages work together efficiently under load.

---

## Tools & Technologies

- PLECS / Simulink  
- Cascaded PI control design  
- PWM modulation strategies  
- Power electronics modeling  
- Signal analysis and controller validation  

---

