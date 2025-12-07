---
layout: page
title: "PLC-Based Centrifuge Control System"
description: "A state-machine driven automation system for controlling a laboratory centrifuge with safety logic and HMI integration."
img: assets/img/projects/plc/hmi_cycle1.png
importance: 0
category: work
---

### Overview

This project implements a **fully automated centrifuge controller** using a PLC-based state machine.  
The system sequences the centrifuge through **filling, acceleration, running, deceleration, emptying, and cycle completion**, while enforcing strict **temperature-based safety interlocks**.

The project demonstrates core industrial automation skills:

- PLC state-machine design  
- Sequential control of motors and valves  
- Safety logic using temperature thresholds  
- HMI development for real-time monitoring  
- End-to-end cycle automation with counters  

---

## System Architecture

The control logic follows a deterministic state-machine. Each state manages actuators, checks sensor feedback, and governs transitions to the next stage.

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3">
    {% include figure.liquid path="assets/img/projects/plc/flowchart.png" title="Centrifuge state-machine overview" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## Safety Interlocks

Operation is blocked if the temperature is outside the allowed range.  
This prevents unsafe acceleration or heating of the centrifuge motor.

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3">
    {% include figure.liquid path="assets/img/projects/plc/hmi_temp_fault.png" title="Temperature safety lockout screen" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## Filling Sequence

The system gradually fills the centrifuge chamber while monitoring temperature, valve states, and cycle counters.  
The HMI visualizes both numeric states and the active process.

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3">
    {% include figure.liquid path="assets/img/projects/plc/hmi_filling.png" title="Filling state visualization" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## Running & Deceleration

The controller ramps the motor through **acceleration, running speed, and controlled deceleration**, showing smooth progression across states.  
A built-in trending graph helps validate the motion profile.

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3">
    {% include figure.liquid path="assets/img/projects/plc/hmi_running.png" title="Acceleration, running, and deceleration" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## Cycle Completion

Each cycle is counted, logged, and displayed on the HMI.  
The system resets automatically after two complete cycles, returning to a safe idle state.

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/plc/hmi_cycle1.png" title="One cycle completed" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/plc/hmi_cycle2.png" title="Two cycles completed and system reset" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

### Tools & Technologies

- PLC Programming (ST / Ladder Logic)  
- HMI Development  
- Industrial Sensors & Actuators  
- State-Machine Design  
- Safety Interlock Logic  

---

