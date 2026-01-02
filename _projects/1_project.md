---
layout: page
title: "Comparative Analysis of YOLOv8 Architectures for PCB Defect Detection"
description: "A quantitative evaluation of lightweight vs. medium convolutional networks for real-time automated optical inspection (AOI)."
img: assets/img/projects/pcb/predictions/n_1.png
importance: 1
category: work
---

## 🔬 Project Overview

Automated Optical Inspection (AOI) systems require a delicate balance between speed and accuracy. This study evaluates the **YOLOv8** object detection family to determine the optimal neural network architecture for embedded electronics inspection.

Unlike standard cloud-based models, this system was constrained to run on **embedded hardware** (NVIDIA Jetson) while maintaining a precision threshold capable of identifying small surface-mount devices (SMDs).

---

## 📊 Results Summary

After training and benchmarking three architectures (Nano, Small, Medium) on the RF100 dataset, the **YOLOv8s (Small)** variant emerged as the superior choice. It achieved a **Precision of 85.9%**, significantly outperforming the Nano baseline while avoiding the computational heaviness of the Medium model.

| Model | Precision | Recall | mAP@0.5 | Performance Verdict |
|:------|:---------:|:------:|:-------:|:-------------------:|
| YOLOv8n (Nano) | 0.820 | 0.651 | 0.680 | Too inaccurate for small components |
| **YOLOv8s (Small)** | **0.859** | **0.678** | **0.731** | **Optimal for Production** |
| YOLOv8m (Medium) | 0.845 | 0.690 | 0.725 | Diminishing returns |

*Data sourced from experimental validation on the RF100 PCB dataset.*

---

## 🔵 Visual Validation

The visual analysis highlights the "feature pyramid" limitation of smaller models. The **Nano** model (top) struggles with bounding box jitter on small capacitors, while the **Small** and **Medium** models provide stable, tight localizations essential for industrial quality control.

### **YOLOv8n (Nano) – Baseline**
*High speed (>60 FPS), but suffers from lower confidence on occluded components.*

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/n_1.png" title="YOLOv8n Prediction" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/n_2.png" title="YOLOv8n Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

### **YOLOv8s (Small) – The Winner**
*The "Small" variant introduces sufficient depth to resolve densely packed components, stabilizing bounding boxes without the heavy computational cost.*

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

A detailed look at the confusion matrices reveals that the primary challenge remains **Inter-Class Similarity**. Visually similar components (e.g., specific resistor values vs. small capacitors) cause the majority of misclassifications. However, the **YOLOv8s** model significantly reduced "Background False Positives" compared to the Nano version.

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

## 🤖 Future Research: From "Seeing" to "Acting"

While this project successfully demonstrated **Perception**, my research ambition is to bridge the gap to **Actuation**.

My proposed MPhil research focuses on **Visual Servoing**: integrating this YOLOv8 inference stream directly into a robot arm's control loop. Instead of just "seeing" a missing capacitor, the system would calculate the vector approach to place a new one, transitioning from Computer Vision to **Embodied AI**.
