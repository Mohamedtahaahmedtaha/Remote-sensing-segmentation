## Remote-sensing-segmentation

This project focuses on semantic segmentation of satellite imagery using DeepLabv3 with ResNet50 as the backbone, trained with a Partial Cross-Entropy Loss function to handle partially labeled data.

# Overview

The goal was to build a model capable of segmenting satellite images into distinct land cover classes such as vegetation, urban areas, and water bodies.
The model was trained on the Remote Sensing Satellite Images dataset from Kaggle, containing labeled training, validation, and test splits.

Despite limited compute resources, the model achieved ~45% IoU after 10 epochs, showing strong learning potential and generalization capability for larger-scale training.

# Technical Details

Model: DeepLabv3 (ResNet50 backbone)

Loss Function: Partial Cross-Entropy Loss (to manage incomplete labels)

Optimizer: AdamW (LR = 3e-4)

Scheduler: CosineAnnealingLR

Epochs: 10

Frameworks: PyTorch, Albumentations, segmentation-models-pytorch

# Results
Metric	Value (after 10 epochs)
IoU	0.45
Dice Coefficient	— (not used)
Loss	Decreasing steadily across epochs
# Visualization

Each epoch outputs:

Original satellite image

Ground truth mask

Model prediction overlay

This allows tracking model improvements qualitatively across training.

# Key Takeaways

Partial supervision works effectively in remote sensing tasks with missing labels.

Transfer learning with ResNet50 accelerates convergence.

Further tuning (e.g., 30+ epochs or larger image sizes) would likely push IoU > 0.7.
