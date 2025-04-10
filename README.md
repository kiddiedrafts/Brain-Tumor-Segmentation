# Brain Tumor Segmentation

This repository contains a deep learning model for brain tumor segmentation from MRI images using a U-Net architecture. The model is trained on the LGG MRI Segmentation dataset from Kaggle.

The project implements a U-Net model to segment brain tumors from MRI scans. The model takes MRI images as input and outputs a binary mask indicating the presence and location of tumors. This type of segmentation is crucial for medical diagnosis and treatment planning.


## Dataset

The model uses the [LGG MRI Segmentation dataset](https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation) from Kaggle.

- License: CC-BY-NC-SA-4.0
- Contains 3,929 MRI images with corresponding masks
- Images are in TIFF format
- Masks are binary (0 for no tumor, 1 for tumor present)
