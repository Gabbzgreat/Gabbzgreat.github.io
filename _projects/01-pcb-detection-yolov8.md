---
layout: page
title: "Real-Time PCB Component Detection Using YOLOv8"
description: "A deep-learning perception system for detecting and classifying PCB components with YOLOv8."
img: assets/img/projects/pcb/main.jpg
importance: 1
category: computer_vision
related_publications: false
---

### Overview

This project presents a **real-time computer-vision system** for detecting electronic components on printed circuit boards (PCBs).  
Using the **YOLOv8** family of models (n, s, m), the system performs multi-class object detection and labeling with strong accuracy and fast inference — enabling automated PCB inspection for manufacturing and repair.

The work focuses on training, evaluating, and comparing YOLOv8 variants on a curated subset of the **RF100 PCB dataset**.

---

### Key Contributions
- Built a complete data preprocessing & augmentation pipeline (Mosaic, MixUp, geometric transforms).
- Trained YOLOv8n, YOLOv8s, and YOLOv8m under identical hyperparameters.
- Conducted detailed performance benchmarking: Precision, Recall, F1, mAP@0.5.
- Designed and deployed a backend using **FastAPI** for real-time detection via web or API.
- Implemented model export to ONNX for edge deployment.

---

### Results Summary

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
      {% include figure.liquid loading="eager" path="assets/img/projects/pcb/results1.jpg" title="Detection Example" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
      {% include figure.liquid loading="eager" path="assets/img/projects/pcb/results2.jpg" title="YOLOv8 Prediction Output" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
      {% include figure.liquid loading="eager" path="assets/img/projects/pcb/results3.jpg" title="Confidence Heatmap" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="caption">
Example detection outputs from the trained YOLOv8 models on PCB samples.
</div>

---

### Quantitative Performance

YOLOv8s achieved the best overall performance:

- **Precision:** 0.859  
- **Recall:** 0.678  
- **mAP@0.5:** 0.7305  
- Best balance between inference speed and accuracy.

YOLOv8m produced the highest localization accuracy, while YOLOv8n offered extremely fast inference suitable for embedded devices.

---

### Training Curves

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
      {% include figure.liquid path="assets/img/projects/pcb/loss_curve.jpg" title="Training Loss Curve" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
      {% include figure.liquid path="assets/img/projects/pcb/map_curve.jpg" title="mAP Curve" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="caption">
Training performance curves showing loss reduction and mAP improvement over epochs.
</div>

---

### Robotics Relevance

This project demonstrates robotics perception skills:

- Real-time object detection for complex scenes  
- Dataset engineering and augmentation  
- Optimization for inference speed  
- Vision pipeline deployment (FastAPI / ONNX)  
- Practical understanding of bounding box regression and feature extraction  

These skills translate directly to robotic manipulation, inspection, scene understanding, and autonomous navigation.

---

### Tools & Technologies
- **Python**, **PyTorch**, **Ultralytics YOLOv8**
- **FastAPI**, **OpenCV**
- **CUDA / GPU training**
- **ONNX for deployment**

---

### Links

- **Thesis PDF:** *(add link or upload later)*  
- **Source Code (optional):**  
- **Demo Backend:** *(optional)*

