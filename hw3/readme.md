# HW3 – Carotid Artery Segmentation from Sonography Images

This assignment focuses on applying deep learning techniques to medical ultrasound images for anatomical structure segmentation.

The goal of this work is to develop models capable of automatically identifying and segmenting the **carotid artery** from neck sonography images. Carotid artery segmentation is an important task in medical image analysis because it assists clinicians in evaluating vascular conditions and assessing cardiovascular risks.

The dataset used in this assignment consists of ultrasound images obtained from scanning the lower neck region. Sonography videos were collected from **three volunteers**, and **100 image frames were randomly extracted from each volunteer**, resulting in a total of **300 training images**. Each image has a corresponding carotid artery segmentation mask labeled by radiologists.

The training dataset contains two main components: the original sonography images and their corresponding labeled segmentation masks. These are organized in two folders, where the **pre folder contains the original ultrasound images and the post folder contains the carotid artery labels**. A file named `train.csv` provides the mapping between image files and their corresponding segmentation masks. :contentReference[oaicite:0]{index=0}

This assignment treats carotid artery extraction as a **semantic segmentation problem**, where the model predicts a pixel-level mask indicating the location of the artery in each ultrasound image.

Two deep learning segmentation architectures are implemented and compared in this assignment.

The first model is the **Fully Convolutional Network (FCN)**. In particular, the **FCN-8s architecture** is used. FCN replaces traditional fully connected layers with convolution layers so that the network can generate spatial prediction maps. FCN-8s further improves segmentation quality by introducing **skip connections**, which combine high-level semantic features with low-level spatial information. This enables the model to produce higher-resolution segmentation results.

The second model is **U-Net**, a widely used deep learning architecture designed specifically for biomedical image segmentation. U-Net consists of an encoder–decoder structure. The encoder extracts hierarchical image features, while the decoder progressively upsamples the feature maps to generate a segmentation mask. Skip connections between corresponding encoder and decoder layers help preserve spatial information and improve segmentation accuracy.

After training the models, the test ultrasound images are passed through the trained networks to generate predicted carotid artery masks. Each predicted segmentation result must be saved using the format:
