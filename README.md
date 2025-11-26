# Computer-Vision-for-Bat-Detection-and-Counting

This repository contains all **research, experimentation, and model-development code** used in my thesis on *Computer Vision for Detecting and Counting Bats Using Thermal Imagery*.

It includes:

* The full **dataset structure**
* A **Google Colab training notebook** used for experimentation
* Two independent **modified Ultralytics YOLOv8 implementations**:

  1. **ultralyitcs** (architecture-modified)
  2. **ultralyitcs_ATFL** — Adaptive Threshold Focal Loss (custom loss function)

This repo complements the deployment repository (web interface + final selected model).
Deployment repo: [*(see main project repo)*](https://github.com/doa-elizabeth-roys/Bat-Population-Tracker.git)

---


## Overview

The purpose of this repository is to document and store **all experimental code** used to build, optimize, and test custom YOLO-based architectures for detecting bats in thermal images.

The goal of the thesis was to:

* Evaluate YOLOv8 baseline performance on thermal bat imagery
* Investigate whether *custom architectural modules* or *custom loss functions* could improve performance
* Select the best-performing model and deploy it through a web interface (available in the separate deployment repository)

This repository contains **all the iterations** preceding the final model selection.

---

## Dataset

The dataset folder includes:

* **Thermal images** captured from field recordings
* **Bounding-box annotations** in YOLO format
* Original **train/val/test split** used throughout the experiments

---

## Google Colab Notebook

`Mod-yolo.ipynb` includes:

* Pre-processing steps
* Experiments with baseline YOLOv8
* Training logs
* Hyperparameter tuning
* Comparisons of model variants
* Evaluation metrics (mAP, Precision, Recall, F1)
* Visualizations of predictions
---

## Model Variants Included

### **1. YOLOv8 + Pinwheel Convolution(PConv), CBAM & C3FGhost**

Folder: `ultralytics/`

### **Changes include**

* Modified model YAML
* Added custom convolution/attention modules
* Adjusted detection head to accommodate the new blocks

---

### **2. YOLOv8 + Adaptive Threshold Focal Loss (ATFL)**

Folder: `ultralytics_atfl/`

### **What is ATFL?**

ATFL is a modified focal loss where:

* the threshold for positive/negative samples is **adaptive**
* the loss focuses more heavily on *hard-to-detect*, dim, low-contrast bats
---

## ** Results Summary**

* Both modified architectures were benchmarked against **baseline YOLOv8**
* Metrics compared:

  * mAP30/ mAP50 / mAP50-95
  * Precision / Recall
  * False-positive and false-negative rates
* The **best-performing model** (see deployment repo) was later used to create the production-ready web interface

---

## ** Contact**

For questions or collaboration:
**Doa Roys**
Email: *doa.roys@my.jcu.edu.au*
