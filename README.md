# Brain Tumor MRI Classification

A hybrid deep learning framework for multiclass brain tumor MRI classification that integrates image preprocessing, threshold-based tumor segmentation, radiomics, foundation model features, feature selection, gated multimodal fusion, and ArcFace-based classification.

---

## Overview

This repository presents an end-to-end framework for multiclass brain tumor MRI classification.

The proposed architecture combines handcrafted radiomic descriptors with deep semantic representations extracted by a medical vision foundation model. Unlike segmentation-based foundation models, tumor localization is performed using Otsu thresholding after CLAHE enhancement, providing a lightweight and computationally efficient preprocessing pipeline.

The extracted radiomic and deep features are refined through feature selection and fused using a gated attention mechanism before final classification.

---

## Proposed Architecture

```
Input Brain MRI
        │
        ▼
CLAHE Enhancement
        │
        ▼
Otsu Thresholding
        │
        ▼
Tumor Mask
        │
 ┌──────┴────────┐
 ▼               ▼
PyRadiomics   Rad-DINO
15 Features   768 Features
        │
        ▼
ARSM Feature Selection
Selected Features
        │
        ▼
Gated Attention Fusion
        │
        ▼
MLP Classifier
+ ArcFace Loss
        │
        ▼
Brain Tumor Prediction
```

---

## Key Features

- CLAHE-based MRI enhancement
- Otsu threshold-based tumor segmentation
- PyRadiomics handcrafted feature extraction
- Rad-DINO deep feature extraction
- ARSM feature selection
- Gated multimodal feature fusion
- ArcFace angular margin classification
- Four-class brain tumor prediction

---

## Model Components

### Image Enhancement

- CLAHE Contrast Enhancement

### Tumor Segmentation

- Otsu Thresholding
- Binary Mask Generation
- ROI Extraction

### Deep Feature Extraction

- Rad-DINO Vision Transformer
- Feature Dimension: 768

### Radiomics

Extracted handcrafted features include:

- First-order Statistics
- Shape Features
- GLCM Texture Features

### Feature Selection

- ARSM
- Mutual Information Based Selection

### Feature Fusion

- Gated Attention Fusion Module

### Classification

- Multi-Layer Perceptron
- ArcFace Angular Margin Loss

---

## Technologies

- Python
- PyTorch
- OpenCV
- PyRadiomics
- timm
- NumPy
- scikit-learn
- Matplotlib

---

## Dataset

Brain MRI Dataset

Classes:

- Glioma
- Meningioma
- Pituitary
- No Tumor

---

## Repository Structure

```
brain-tumor-classification/
│
├── dataset/
├── models/
├── notebooks/
├── train.py
├── test.py
├── utils.py
├── requirements.txt
├── README.md
└── LICENSE
```

---

## Installation

```bash
git clone https://github.com/your_username/brain-tumor-classification.git

cd brain-tumor-classification

pip install -r requirements.txt
```

---

## Future Improvements

- Adaptive Feature Selection
- Explainable AI (Grad-CAM)
- Multi-modal MRI Support
- External Dataset Validation

---

## Author

**Raju Mia**

Department of Computer Science and Engineering

Dhaka University of Engineering & Technology (DUET), Bangladesh
