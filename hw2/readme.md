# HW2 – Medical Image Modeling with CNN and Multimodal MRI

## Overview

Two main objectives are addressed:

1. Improving the Parkinson’s disease stage prediction model by handling the class imbalance problem.
2. Applying 3D convolutional neural networks (3D CNN) to detect brain tumors using MRI data.

---

## Dataset

### Brain Tumor MRI Dataset

The second dataset contains brain MRI scans used for tumor detection.

Dataset composition:

- **100 normal brain scans**
- **100 tumor brain scans**



### MRI Modalities

Two MRI modalities are used:

- **T1-weighted MRI**
- **T2-weighted MRI**

These modalities highlight different tissue characteristics.  
To better visualize tumor regions, **T1 and T2 images are combined**, allowing the model to capture complementary structural information.

---

## Model Architectures

Several CNN-based models are implemented and compared.

### 3D CNN Model

### Early Fusion Model

### Late Fusion Model

### Singal Slice Model

