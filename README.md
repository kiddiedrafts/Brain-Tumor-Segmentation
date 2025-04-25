# Brain Tumor Segmentation

This repository contains a deep learning model for brain tumor segmentation from MRI images using a U-Net architecture. The model is trained on the LGG MRI Segmentation dataset from Kaggle.

The project implements a U-Net model to segment brain tumors from MRI scans. The model takes MRI images as input and outputs a binary mask indicating the presence and location of tumors. This type of segmentation is crucial for medical diagnosis and treatment planning.


## Dataset

The model uses the [LGG MRI Segmentation dataset](https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation) from Kaggle.

- Contains 3,929 MRI images in TIFF format with corresponding masks
- Masks are binary (0 for no tumor, 1 for tumor present)

## Data Preprocessing

The data preprocessing pipeline includes:
1. Downloading and extracting the dataset from Kaggle
2. Organizing the data into a pandas DataFrame with columns:
   - patient_id
   - image_path
   - mask_path
   - mask (binary indicator)
3. Splitting the data into training, validation, and test sets.
4. Creating a custom data generator (`BrainTumorGenerator`) that:
   - Loads images and masks
   - Resizes them to 256x256 pixels

## Model Architecture

The model uses a U-Net architecture with the following components:

**Encoder (Downsampling Path):**
- 3 levels of convolutional blocks (Conv2D + Conv2D + MaxPooling2D)
- Number of filters increases from 64 to 256

**Bottleneck:**
- Two convolutional layers with 512 filters

**Decoder (Upsampling Path):**
- 3 levels of upsampling blocks (UpSampling2D + concatenation + Conv2D + Conv2D)
- Skip connections from corresponding encoder levels
- Number of filters decreases from 256 to 64

**Output:**
- Final 1x1 convolution with sigmoid activation for binary segmentation

## Training

The model was trained with:
- Optimizer: Adam
- Loss function: Binary crossentropy
- Batch size: 16
