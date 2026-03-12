# HW3 – Carotid Artery Segmentation from Sonography Images


## Overview

This assignment focuses on applying deep learning models to medical ultrasound images for anatomical structure segmentation.

The goal is to automatically segment the carotid artery from neck sonography images. Accurate carotid artery segmentation helps clinicians analyze vascular structures and evaluate cardiovascular risk.

## Dataset
Ultrasound videos were collected from three volunteers.
From each video, 100 frames were randomly extracted.

Total training images:
300 ultrasound images
300 segmentation masks

Each training sample contains:

Ultrasound Image → Segmentation Mask

The task is treated as a semantic segmentation problem, where the model predicts a pixel-level mask indicating the carotid artery region.

Model Architectures

Two segmentation models are implemented and compared.

# FCN-8s

Fully Convolutional Network (FCN-8s) replaces fully connected layers with convolution layers so the network can produce pixel-wise predictions.

Input Image
      ↓
CNN Encoder
      ↓
Feature Map
      ↓
Skip Connections
      ↓
Upsampling
      ↓
Segmentation Mask
# U-Net

U-Net is a widely used architecture for medical image segmentation.

It follows an encoder–decoder structure:

Encoder → extracts features

Decoder → reconstructs spatial resolution

U-Net uses skip connections between encoder and decoder layers, helping preserve fine spatial details.

Input Image
      ↓
Encoder (Conv + Pooling)
      ↓
Bottleneck
      ↓
Decoder (Upsampling)
      ↓
Segmentation Mask

