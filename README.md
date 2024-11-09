# Pneumonia Detection Project

## Overview
This project aims to build a model that classifies chest X-ray images to identify cases of pneumonia. Using a convolutional neural network (CNN) model, the model detects if an X-ray shows signs of pneumonia and, as a further goal, distinguishes between viral and bacterial causes of pneumonia.

## Dataset
The dataset used for this project is the [Chest X-ray Images (Pneumonia)](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) dataset. It includes X-ray images categorized into:
1. **Normal**: Images showing no signs of pneumonia.
2. **Pneumonia**: Images showing signs of pneumonia, with additional labels for **viral** and **bacterial** pneumonia.

Due to the typical class imbalance in healthcare data (with more normal cases than abnormal), data augmentation techniques were applied to balance the dataset.

## Data Preprocessing and Augmentation
To balance the dataset:
- **ImageDataGenerator** was used to perform real-time data augmentation, including:
  - **Rotation**: Random rotations up to 20 degrees.
  - **Zoom**: Random zooming by 15%.
  - **Width and Height Shifts**: Up to 10% shift in both dimensions.
  - **Fill Mode**: Filling missing pixels created by shifts and rotations.
  
These techniques increased the number of pneumonia images, allowing the model to generalize better and mitigate overfitting.

## Model Architecture
The final model was built using a simple CNN architecture with the following key components:
- **Convolutional Layers**: To extract image features.
- **Pooling Layers**: To reduce spatial dimensions and retain important features.
- **Dense Layers**: Fully connected layers for final classification.
- **Regularization**: L2 regularization was used in the dense layers to prevent overfitting.
- **Threshold Adjustment**: The classification threshold was adjusted based on the desired trade-off between precision and recall, to enhance sensitivity for detecting pneumonia.

## Evaluation Metrics
The model was evaluated using:
- **Accuracy**: The proportion of correctly predicted samples.
- **Precision**: The accuracy of the pneumonia-positive predictions.
- **Recall**: The model’s sensitivity, or ability to detect pneumonia cases.
- **F1 Score**: The harmonic mean of precision and recall, providing a balance between them.

## Final Model Performance
On the test set:
- **Accuracy**: 78.25%
- **Precision**: 74.95%
- **Recall**: 98.25%
- **F1 Score**: 85.01%
  
### Future Work
I am looking to improve the accuracy of the model with the use of transfer learning and using pre-trained networks like VGG16 or ResNet. 
