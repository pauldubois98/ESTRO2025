# Evaluation of transformer architecture for deep dose prediction in radiotherapy

## Introduction

Radiotherapy treatment planning seeks to maximize tumor control while sparing healthy tissue. Traditionally, treatment plans are developed through iterative, manual processes involving dose constraints. With advances in deep learning, automated dose prediction based on patient scans has gained traction, typically using architectures like 3D Unets. However, transformers, initially popularized in natural language processing, have recently demonstrated robust performance on image and audio data, suggesting potential for application in medical imaging. This study investigates replacing the conventional 3D Unet with a 3D transformer-based architecture for dose prediction, assessing performance and training efficiency.

## Material and Methods

We utilized a dataset of 168 patient CT scans (split 80-10-10 for training-validation-test). We also used the contours for Principal Target Volume (PTV) and Organs at Risk (OARs) used for treatment to compare the Dose-Volume Histograms (DVH). The model input consisted of CT scans and anatomical contours, with the output as the 3D dose prediction. We compared a 3D convolutional U-net and a transformer model, with self-attention layers substituting the convolutional layers of the U-net. The training was performed with a voxel-wise Mean Absolute Error (MAE) loss function on the 3D dose output and the DVH (this second loss helped the model focus on essential regions).
