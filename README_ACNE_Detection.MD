# Detection Folder

## Description
The Detection folder is dedicated to implementing YOLOv8 model architecture for the detection of acne and dark spots in facial images. The project utilizes a two-class dataset for effective detection and aims to optimize model performance through various training strategies.

## Model Training

### Initial Parameters
- **Learning Rate**: 0.01
- **Input Size**: 640 (maintaining aspect ratio)

### Dataset Classes
- **Dark Spots (ds)**
- **Acne**

## Augmentation Techniques
The training dataset employs a variety of augmentation schemes, which include:
- Rotation (±30 degrees)
- Grayscale randomization
- Saturation adjustments
- Random black boxes

### Key Augmentation Technique: Mosaic
Mosaic augmentation combines multiple images into a single image, significantly enhancing the detection of small objects like acne and dark spots. This technique has proven to be particularly effective in improving model robustness.

## Train Dataset Folders
The dataset is organized into various folders, each with specific objectives:

- **train_1_ds_acne**: Contains two classes, indicating a need for more dark spot images for better multi-class performance.
- **train_single_class_acne_plus_ds**: Merges both classes into one to aid further classification but resulted in degraded performance.
- **train_3_single_class_acne**: Focused solely on acne images but yielded false positives for dark spots.
- **train_3_single_class_acne_2**: Similar to the previous, with an aim to remove dark spots but still encountered false positives, particularly with images showing red spots or shine.
- **train_4_single_class_acne_plus_ds**: Added numerous unannotated dark spot images and background images (100 more images of 20 for shine, redness, dark spots, wrinkles, and elderly individuals) to reduce false positives for acne.

## Results
The results follow a naming convention for model names and classes. The best-performing model to date is from the `train_4_single_class_with_background` dataset, although further improvements are needed by incorporating client-side images and real-world datasets.

## Runs
This folder adheres to the YOLO naming convention and contains trained models. The `args.yaml` file provides detailed information about the model configurations.

## Future Work
The model has encountered performance issues with 65 test images from client data. Future work will focus on identifying more real-world datasets, annotating them, and integrating them into the training process to enhance model performance. 


