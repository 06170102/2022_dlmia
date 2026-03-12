# HW4 – Chest X-ray Abnormality Detection
## Overview

This project applies deep learning object detection models to chest X-ray images to detect abnormal regions and predict possible chest diseases.


Possible abnormal categories include:
- Aortic calcification
- Aortic tortuosity
- Increased lung infiltration
- Thoracic spine degenerative disease
- Scoliosis
- Pleural thickening
- Cardiomegaly
- Normal

This problem is treated as an **object detection task**, where the model predicts:

Bounding Box + Disease Category

for abnormal regions in each image.

## Dataset

All datasets are provided in the compressed file hwk04_data.zip. 


Training Data

image/ → original chest X-ray images (.dcm)

mark/ → bounding box annotations (.jpg)


## Image Preprocessing

The original chest X-ray images are stored as DICOM (.dcm) files.

Pixel Intensity Relationship = LOG

Photometric Interpretation = MONOCHROME1

the pixel values must be converted before training.

### 1. Intensity Log Transformation

### 2. Contrast Adjustment

### 3. Image Resizing


Pipeline:

Input Image
      ↓
Backbone CNN
      ↓
**Region Proposal Network (RPN)**
      ↓
Region Classification + Bounding Box Regression

Faster R-CNN first generates candidate regions and then classifies them into disease categories.

Mask R-CNN

Mask R-CNN extends Faster R-CNN by adding a segmentation branch.

Pipeline:

Input Image
      ↓
Backbone CNN
      ↓
Region Proposal Network
      ↓
Bounding Box + Class Prediction
      ↓
Pixel-level Mask Prediction

This allows the model to localize abnormalities more precisely.