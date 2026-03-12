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
[t1+t2](../images/t1+t2_weight.png)
---

## Model Architectures

Several CNN-based models are implemented and compared.

### 3D CNN Model(效果差)

input_6 (InputLayer)         [(None, 150, 150, 66)]。疊加第brain 橫切面成為四維度，丟入3DCNN model。 

### Early Fusion Model

Input Fusion
(300 × 300 × 18) input kernal結合，形成early fusion。
        │
        ▼
 Conv2D(64) + BN
        ▼
 Conv2D(64) + BN
        ▼
 MaxPooling
        ▼
 Conv2D(64) + BN
        ▼
 Conv2D(64) + BN
        ▼
 MaxPooling
        ▼
Conv2D(128) + BN
        ▼
Conv2D(128) + BN
        ▼
 MaxPooling
        ▼
Conv2D(128) + BN
        ▼
Conv2D(128) + BN
        ▼
 MaxPooling
        ▼
     Flatten
        ▼
 Dense(256, ReLU, L1)
        ▼
   Dropout(0.2)
        ▼
 Dense(64, ReLU, L1)
        ▼
 Dense(1, Sigmoid)
        ▼
 Binary Output



### Late Fusion Model

Input 1 (300x300x3) ──> CNN Branch 1 ──> Flatten ──┐
                                                    │
Input 2 (300x300x3) ──> CNN Branch 2 ──> Flatten ──┼──> Concatenate
                                                    │         │
Input 3 (300x300x3) ──> CNN Branch 3 ──> Flatten ──┘         ↓
                                                        Dense(64, ReLU)
                                                               ↓
                                                        Dense(32, ReLU)
                                                               ↓
                                                      Dense(1, Sigmoid)
                                                               ↓
                                                         Binary Output


### Singal Slice Model(VGG16)

