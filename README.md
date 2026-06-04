# Deep Learning Based Solar Panel Defect Detection and Performance Evaluation

## Overview

This project presents an end-to-end deep learning framework for automated solar cell inspection using Electroluminescence (EL) images.

The system performs:

- Defect Classification using ResNet50
- Defect Localization using YOLOv8
- Electrical Performance Prediction using EfficientNetB0
- Correlation Analysis between visual defects and photovoltaic performance degradation

The goal is to enable scalable and automated health assessment of photovoltaic (PV) modules by linking visual defects directly to electrical performance metrics such as Voc, ΔVoc, and Isc.

---

## Problem Statement

Solar cells often develop defects such as:

- Cracks
- Finger Interruptions
- Thick Line Defects

These defects reduce power generation efficiency and accelerate module degradation.

Traditional inspection methods are expensive, time-consuming, and difficult to scale.

This project uses computer vision and deep learning to automatically detect defects and estimate their impact on solar panel performance.

---

## Project Pipeline

```text
EL Images
    │
    ▼
Image Preprocessing
    │
    ▼
ResNet50
(Defective / Non-Defective)
    │
    ▼
YOLOv8
(Defect Localization)
    │
    ▼
Feature Extraction
    │
    ▼
Correlation Analysis
    │
    ▼
EfficientNetB0 Regression
    │
    ▼
Voc, ΔVoc, Isc Prediction
```

---

## Datasets

### Open Source Dataset

**PVEL-AD Dataset**

- 36,543 EL images
- Bounding box annotations available
- 12 defect categories

Defects used in this work:

- Crack
- Finger Interruption
- Thick Line Defect

### Industrial Dataset

- 61,786 real-world EL images
- Industrial manufacturing environment
- Associated IV curve measurements
- Used for photovoltaic performance prediction

After preprocessing:

- 44,372 usable images retained for training and analysis

---

## Models Used

### ResNet50 – Defect Classification

Binary Classification:

```text
Defective
vs
Non-Defective
```

Key Features:

- Transfer Learning
- Two-stage fine tuning
- Data augmentation
- Binary Cross Entropy Loss

### YOLOv8 – Defect Localization

Object Detection Classes:

- Crack
- Finger Defect
- Thick Line Defect

Capabilities:

- Real-time defect detection
- Multi-defect localization
- Bounding box prediction

### EfficientNetB0 – Performance Prediction

Regression Targets:

- Voc
- ΔVoc
- Isc

Combines:

- Deep image features
- Statistical image features
- Defect count information

for performance estimation directly from EL images.

---

## Image Processing Techniques

The preprocessing pipeline includes:

- Non-Local Means Denoising
- Histogram Normalization
- CLAHE Contrast Enhancement
- Image Sharpening
- Morphological Processing
- Offline Data Augmentation
- On-the-fly Data Augmentation

These techniques improve defect visibility while preserving critical defect structures.

---

## Results

### Defect Classification

| Model | Accuracy |
|---------|---------|
| ResNet50 | 97.3% |

### Defect Localization

| Model | mAP@50 |
|---------|---------|
| YOLOv8 | 0.97 |

### Electrical Performance Prediction

| Target | R² Score |
|----------|----------|
| Voc | 0.61 |
| ΔVoc | 0.63 |
| Isc | 0.78 |

The results demonstrate that EL image characteristics contain meaningful information for predicting photovoltaic performance degradation.

---

## Tech Stack

### Languages

- Python

### Deep Learning

- TensorFlow
- Keras
- PyTorch
- Ultralytics YOLOv8

### Computer Vision

- OpenCV
- NumPy
- Scikit-image

### Data Science

- Pandas
- Scikit-learn
- Matplotlib
- Seaborn

---

## Key Contributions

- Built a two-stage defect detection framework using ResNet50 and YOLOv8.
- Developed an EfficientNetB0-based multimodal regression model for PV performance prediction.
- Performed feature engineering and correlation analysis on industrial EL datasets.
- Designed separate preprocessing pipelines for open-source and industrial datasets.
- Linked visual defect characteristics to measurable electrical performance degradation.

---

## Future Improvements

- Multi-class defect classification
- Semantic segmentation for pixel-level defect localization
- Vision Transformers (ViT)
- Real-time deployment on production inspection lines
- Explainable AI (XAI) for defect interpretation

---

## Authors

- Vishal Thangakumar
- Akiellan S
- Ranjith Balu

Bachelor of Technology  
Computer and Communication Engineering  
Amrita Vishwa Vidyapeetham
