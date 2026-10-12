# Mask_RCNN_oilwell

This repository contains the Mask R-CNN implementation (TensorFlow 2.14) used for abandoned oil well detection from UAV LiDAR-derived terrain data.

### 1. Dataset

The datasets are stored separately on Google Drive.

#### Original Dataset:

https://drive.google.com/drive/folders/1Au7sdv6jL2wyPfMBmt9ZYo1SuYcLV-cP?usp=drive_link

##### Original Dataset Structure

The original dataset contains four subfolders:

| Folder Name | Description |
|---|---|
| `Comb_siteA` | Combined Site A dataset containing both pre-remediation and post-remediation data |
| `SiteA_post` | Site A post-remediation dataset |
| `siteA_pre` | Site A pre-remediation dataset |
| `siteB` | Site B dataset |

Each folder contains the corresponding dataset used for model training, validation, or testing.

#### Augmented Dataset: 
https://drive.google.com/drive/folders/1dU2zoaNbpNI6TdLWu38B9NyrswR58Ot6?usp=drive_link

Download and place the original dataset in: Mask-RCNN_TF2.14.0/datasets/oilwell/

### 2. Configuration Notes

Baseline: Retain the default configuration in the Mask R-CNN model.

IoU Optimization: Modify the RPN IoU thresholds:

RPN_POSITIVE_OVERLAP = 0.5
RPN_NEGATIVE_OVERLAP = 0.2

Backbone Fine-Tuning: Change the training layer selection:

layers = "4+"

Anchor Scale Optimization: Modify the anchor scales:

RPN_ANCHOR_SCALES = (8, 16, 32, 64, 128)

Data Augmentation: Use the augmented dataset for the final model configuration.

### 3. Notes

- All model training and optimization experiments are executed in the Jupyter notebook mrcnn_oilwell.ipynb
- Data augmentation is performed in the Jupyter notebook mrcnn_oilwell_aug.ipynb
- Each optimization stage builds on the preceding configuration.
- Unless otherwise specified, all other model parameters remain unchanged.

