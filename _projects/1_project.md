---
layout: page
title: "Comparative Analysis of YOLOv8 Architectures for PCB Component Recognition"
description: "A quantitative evaluation of lightweight vs. medium convolutional networks for real-time automated electronic component identification."
img: assets/img/projects/pcb/predictions/n_1.png
importance: 1
category: work
---

## 🔬 Project Overview

In the automated assembly of printed circuit boards (PCBs), accurate **Component Recognition** is the prerequisite for effective Quality Control. Before a system can identify a "defect" (like a missing or damaged part), it must first correctly identify and map every component on the board.

This study investigates the **YOLOv8** object detection family to determine the optimal neural network architecture for **real-time component identification** in resource-constrained environments. Unlike standard defect detection systems that look for soldering faults, this research focuses on the fundamental task of **classifying and localizing** densely packed components (ICs, Capacitors, Diodes) with high precision.

---

## 📊 Results Summary

Using the **RF100 PCB dataset**, this project benchmarked three model scales (Nano, Small, Medium). The **YOLOv8s (Small)** variant emerged as the optimal architecture for industrial application. It achieved a **Precision of 85.9%**, significantly outperforming the Nano baseline while maintaining a computational footprint small enough for real-time inference.

| Model Variant | Precision | Recall | mAP@0.5 | Performance Verdict |
|:-------------|:----------:|:------:|:-------:|:-------------------:|
| YOLOv8n (Nano) | 0.820 | 0.651 | 0.680 | High speed, low confidence on micro-components |
| **YOLOv8s (Small)** | **0.859** | **0.678** | **0.731** | **Optimal Balance (Selected)** |
| YOLOv8m (Medium) | 0.845 | 0.690 | 0.725 | Diminishing returns in accuracy vs. latency |

*Data sourced from experimental validation on the RF100 PCB dataset.*

---

## 🔵 Visual Validation & Architecture Analysis

The visual analysis highlights the impact of **Feature Pyramid Network (FPN)** depth on component separation. The Nano model, while fast, lacks the feature extraction depth required to consistently resolve small capacitors against complex board backgrounds. The Small model introduces sufficient depth to stabilize bounding boxes without the massive parameter increase of the Medium model.

### **YOLOv8n (Nano) – The Efficiency Baseline**
*Observation: While suitable for high-speed screening (>60 FPS theoretical), the Nano model exhibits lower confidence scores and bounding box jitter on occluded components.*

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/n_1.png" title="YOLOv8n Prediction" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/n_2.png" title="YOLOv8n Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

### **YOLOv8s (Small) – The Optimal Candidate**
*Observation: The "Small" variant successfully resolves densely packed components. The improved recall (0.678) ensures fewer missed components compared to the Nano variant, making it the preferred choice for mapping board layouts.*

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/s_1.png" title="YOLOv8s Prediction" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/s_2.png" title="YOLOv8s Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## 🔵 Error Analysis

A detailed look at the confusion matrices reveals that the primary challenge remains **Inter-Class Similarity**. Visually similar components (e.g., distinguishing between specific Diode packages or similar ICs) account for the majority of classification errors. However, the **YOLOv8s** model significantly reduced "Background False Positives" compared to the Nano version, proving it has a superior semantic understanding of the PCB structure.

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/confusion/n_confusion.png" title="YOLOv8n Confusion Matrix" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/confusion/s_confusion.png" title="YOLOv8s Confusion Matrix" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/confusion/m_confusion.png" title="YOLOv8m Confusion Matrix" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## 🤖 Future Research: From "Recognition" to "Actuation"

While this project successfully demonstrated **Visual Perception** (identifying components), my research ambition is to bridge the gap to **Robotic Actuation**.

My proposed MPhil/PhD research focuses on **Visual Servoing**: integrating this YOLOv8 inference stream directly into a robot arm's control loop. Instead of just "recognizing" a capacitor, the system would use that coordinate data to calculate the kinematic trajectory to physically grasp or solder it, transitioning from Computer Vision to **Embodied AI**.
