---
layout: page
title: "Real-Time PCB Component Detection Using YOLOv8"
description: "A deep-learning perception system for detecting and classifying PCB components with YOLOv8."
img: assets/img/projects/pcb/predictions/n_1.png
importance: 1
category: computer_vision
related_publications: false
---

### Overview

This project presents a **real-time computer-vision system** for detecting electronic components on printed circuit boards (PCBs).  
Using **YOLOv8n, YOLOv8s, and YOLOv8m**, the system performs fast multi-class detection suitable for automated inspection.

---

## 🔵 Prediction Examples (All Models & All Images)

### **YOLOv8n Predictions**

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/n_1.png" title="YOLOv8n Prediction 1" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/n_2.png" title="YOLOv8n Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

### **YOLOv8s Predictions**

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/s_1.png" title="YOLOv8s Prediction 1" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/s_2.png" title="YOLOv8s Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

### **YOLOv8m Predictions**

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/m_1.png" title="YOLOv8m Prediction 1" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/m_2.png" title="YOLOv8m Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## 🔵 Confusion Matrices

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

## 🔵 F1–Confidence Curves

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/curves/n_f1.png" title="YOLOv8n F1 Curve" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/curves/s_f1.png" title="YOLOv8s F1 Curve" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/curves/m_f1.png" title="YOLOv8m F1 Curve" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## 🔵 Combined Metrics (mAP, Fitness)

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/curves/metrics.png" title="mAP & Fitness Metrics" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

### Tools & Technologies
Python • PyTorch • YOLOv8 • FastAPI • OpenCV • CUDA • ONNX

---
