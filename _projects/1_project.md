---
layout: page
title: "Comparative Analysis of YOLOv8 Architectures for PCB Defect Detection"
description: "A quantitative evaluation of lightweight vs. medium convolutional networks for real-time automated optical inspection (AOI)."
img: assets/img/projects/pcb/predictions/n_1.png
importance: 1
category: work
---

## 🔬 Research Abstract

Automated Optical Inspection (AOI) in electronics manufacturing faces a critical trade-off: high-accuracy models are often too computationally expensive for edge deployment, while lightweight models struggle with small-component granularity.

This study investigates the performance-to-latency ratio of **YOLOv8 nano (n), small (s), and medium (m)** architectures on the RF100 PCB dataset. The goal was to determine the optimal architecture for **resource-constrained robotic inspection systems** where inference speed (FPS) is as critical as Mean Average Precision (mAP).

---

## 🔵 Qualitative Analysis (Model Comparison)

The following visualizations demonstrate the detection capabilities across model depths. While all models successfully localized major components (IC chips, connectors), the **YOLOv8n** (Nano) variant exhibited higher jitter on smaller capacitors compared to the **YOLOv8m** (Medium) variant, highlighting the impact of feature pyramid depth on small-object detection.

### **YOLOv8n (Nano) – Low Latency Baseline**
*Observation: High inference speed but lower confidence on occluded components.*

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/n_1.png" title="YOLOv8n Prediction 1" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/n_2.png" title="YOLOv8n Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

### **YOLOv8s (Small) – Balanced Architecture**
*Observation: Improved bounding box stability with minimal latency penalty.*

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/s_1.png" title="YOLOv8s Prediction 1" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/s_2.png" title="YOLOv8s Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

### **YOLOv8m (Medium) – High Precision**
*Observation: Superior separation of densely packed components, though computationally heavier.*

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/m_1.png" title="YOLOv8m Prediction 1" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/projects/pcb/predictions/m_2.png" title="YOLOv8m Prediction 2" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## 🔵 Error Analysis (Confusion Matrices)

A critical analysis of the confusion matrices reveals that **inter-class similarity** (e.g., distinguishing between specific resistor values or similar IC packages) remains the primary source of error. The darker diagonals in the **YOLOv8m** matrix indicate a stronger semantic understanding of component classes compared to the Nano model, which was more prone to background false positives.

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

## 🔵 Performance Metrics (F1 & mAP)

The **F1-Confidence Curves** illustrate the precision-recall balance. The **YOLOv8m** model maintains a higher F1 score across a broader range of confidence thresholds, suggesting it is more robust for autonomous decision-making where false negatives (missed defects) are costly.

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

## 🚀 Future Research Proposal

While this study established a baseline for supervised detection, significant challenges remain for deployment in dynamic manufacturing environments. My proposed future research extends this work in two key directions:

1.  **Unsupervised Domain Adaptation:** Addressing the performance drop when models trained on one PCB style are applied to a different manufacturer's board (domain shift) without manual retraining.
2.  **Few-Shot Defect Detection:** Investigating generative techniques (GANs/Diffusion) to synthesize training data for rare defects, solving the class imbalance problem identified in the confusion matrices above.

This work serves as the foundation for my proposed **MPhil research into Robust Computer Vision for Industrial Robotics.**

---

## Technologies & Methodologies

**Deep Learning:** PyTorch, Ultralytics YOLOv8, CUDA Acceleration  
**Evaluation:** Precision-Recall Analysis, Confusion Matrix Profiling, mAP Benchmarking  
**Deployment:** ONNX Runtime Optimization for Edge Devices
