#  Multi-Class Vehicle Image Classification using CNNs and MLPs

This project aims to classify vehicle images into one of **seven categories** using deep learning techniques, specifically Convolutional Neural Networks (CNNs) and Multi-Layer Perceptrons (MLPs). It builds upon traditional binary classification efforts and extends them to a robust multi-class setting.

---

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Model Architectures](#model-architectures)
  - [CNN Architecture](#cnn-architecture)
  - [MLP Architecture](#mlp-architecture)
- [Training Setup](#training-setup)
- [Evaluation](#evaluation)
- [Results](#results)
- [Installation & Usage](#installation--usage)
- [Project Structure](#project-structure)
- [References](#references)

---

## Overview

This project is focused on **image-based vehicle classification** using deep learning. The goal is to classify images into the following classes:

- Auto Rickshaws
- Bikes
- Cars
- Motorcycles
- Planes
- Ships
- Trains

We compared two models:
- A **Convolutional Neural Network (CNN)** for spatial feature extraction
- A **Multi-Layer Perceptron (MLP)** as a baseline model

---

## Dataset

- Total images: **5,600**
- Images per class: **800**
- Classes: 7 vehicle types
- Sources: Custom-collected from diverse environments with variations in lighting, background, and orientation.

---

## Preprocessing

The following preprocessing steps were applied:

- **Resizing**: All images resized to 224x224 pixels
- **Normalization**: Pixel values scaled to the [0, 1] range
- **One-Hot Encoding**: For multi-class categorical labels
- **Data Splitting**: 80% training, 20% validation
- **Shuffling**: Applied to avoid any bias in training order
- **Batching**: Mini-batch size of 32

---

## Model Architectures

### CNN Architecture

- **Input**: 224x224x3
- **Layers**:
  - Convolutional layers with ReLU activation
  - MaxPooling layers
  - Dropout for regularization
  - Fully Connected Dense Layers
- **Output**: Softmax activation (7 units for 7 classes)

CNNs were chosen for their ability to exploit spatial hierarchies and patterns in image data.

### MLP Architecture

- **Input**: Flattened 224x224x3 vector
- **Layers**:
  - Dense layers with ReLU
  - Dropout layers
- **Output**: Softmax activation

MLPs served as a simpler baseline model for comparative evaluation.

---

##  Training Setup

- **Framework**: TensorFlow / Keras
- **Loss Function**: Categorical Cross-Entropy
- **Optimizer**: Adam
- **Metrics**: Accuracy, Precision, Recall, F1-Score
- **Early Stopping**: Applied on validation loss

---

## Evaluation

### Confusion Matrices

Confusion matrices were generated to inspect class-wise accuracy and misclassifications.

### Training Curves

Training and validation accuracy/loss were plotted to analyze convergence and generalization behavior.

---

## Results

| Metric      | CNN     | MLP     |
|-------------|---------|---------|
| Accuracy    | 82.5%   | 71.8%   |
| Precision   | 0.81    | 0.68    |
| Recall      | 0.82    | 0.70    |
| F1-Score    | 0.81    | 0.69    |

- CNN outperforms MLP across all metrics.
- MLP struggled with visually similar classes like Cars and Motorcycles.
- CNN showed strong performance even in such challenging cases due to hierarchical feature learning.

---

## Installation & Usage

### Requirements

```bash
pip install tensorflow numpy matplotlib scikit-learn
```
### Project Structure

├── Project_76.ipynb               # Main Jupyter Notebook

├── Project_Report_Endsem_76.pdf   # Project Report

└── README.md                      # This file

### References
1.TensorFlow

2.Keras

3.Krizhevsky, A., et al. (2012). ImageNet Classification with Deep CNNs

4.Rumelhart, D. E., et al. (1986). Backpropagation of Errors


