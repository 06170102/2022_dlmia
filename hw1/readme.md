# HW1 – Parkinson’s Disease Stage Prediction

## Overview

This assignment explores the application of convolutional neural networks (CNNs) for medical image analysis.

The goal is to build deep learning models capable of predicting the **stage of Parkinson’s disease** based on patient data and brain imaging.

The experiment integrates **clinical attributes** and **medical imaging features** to perform disease stage prediction.

---

## Dataset

The dataset contains **161 training samples** **40 testing samples**  of Parkinson’s disease patients.

Each record includes:

- **Age**
- **Gender**
- **Brain X-ray image**
  [xray](../images/brain_xray.png)

- 



The task is to predict the **disease stage** of Parkinson’s disease.

### Dataset Summary

| Feature | Description |
|------|------|
| Age | Patient age |
| Gender | Patient gender |
| Brain X-ray | Brain imaging data |
| Label | Parkinson's disease stage |

---

## Task

This task is formulated as a **medical image classification problem**.



## Models

Three CNN-based approaches are implemented.

### VGG16

A pretrained **VGG16** model is used to extract deep image features from brain X-ray images.

VGG16 provides a deep convolutional architecture suitable for image classification tasks.

---

### ResNet

A **Residual Network (ResNet)** architecture is used to improve feature extraction through residual connections.

ResNet helps mitigate vanishing gradient problems and enables deeper networks.

---

### Concatenated Model

  [concatenate](../images/concatenate_model.png)

A hybrid architecture is implemented by **concatenating features extracted from VGG16 and ResNet**.

The combined representation aims to leverage complementary information from both models.

Architecture concept:












