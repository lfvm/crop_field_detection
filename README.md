# Crop Field Segmentation using Deep Learning

## Overview

This project aims to develop an advance AI model for segmenting crop fields from satellite images using convolutional neural networks (CNN). It involves processing and analyzing satellite imagery to identify and delineate agricultural fields, which is crucial for various applications in agriculture such as yield prediction, crop monitoring, and land usage analysis.

## Dataset

The dataset consists of satellite images along with their respective mask images that delineate crop fields. The data is divided into training and testing subsets, with each subset containing paths to the images and their corresponding masks. The images are preprocessed and augmented to fit the requirements of the neural network models used.

## Models

Several state-of-the-art segmentation models have been implemented and trained, including:

- U-Net++: An advanced version of the original U-Net, designed with nested, dense skip pathways to provide better segmentation accuracy.

- DeepLabV3: Utilizes atrous convolutions to capture multi-scale information effectively.

- DeepLabV3+: Combines the advantages of DeepLabV3 and encoder-decoder architectures for improved segmentation.

- U-Net: The standard model for image segmentation tasks which uses a simple, yet effective architecture for various biomedical image segmentation.

Each model is trained using PyTorch Lightning, which simplifies the training pipeline and allows for easy scaling and monitoring. Models are evaluated based on the Intersection over Union (IoU) metric, among other performance metrics.

## Results

The models evaluated in this project demonstrated robust performance, with the U-Net model particularly standing out. This model was configured with a learning rate of 0.0001, used the Adam optimizer, employed a ResNet50 encoder, and was trained over 20 epochs. Although the U-Net++ model achieved a higher Intersection over Union (IoU), signs of overfitting were evident from the training plots.

The U-Net architecture outperformed the DeepLabV3 model. It was observed that higher learning rates complicated the stabilization of the gradient and negatively impacted the results. The optimizers used, which were two variants of Adam, showed similar performances.

Encoders, especially those from the ResNet series, were crucial in determining the model's speed and also influenced the accuracy in detailed areas of the images. This is particularly challenging as the compression process in the encoders reduces the image size, which can affect the model's ability to capture fine details necessary for accurate field segmentation.

## Predictions

The dataset uses a set of predefined classes along with specific RGB values for each class to label the satellite images. These labels help in categorizing different types of land cover visible in the images, which are crucial for accurate segmentation and analysis. Below are the classes and their corresponding RGB values:

- Urban Land: RGB (0, 255, 255) - Cyan
- Agriculture Land: RGB (255, 255, 0) - Yellow
- Rangeland: RGB (255, 0, 255) - Magenta
- Forest Land: RGB (0, 255, 0) - Green
- Water: RGB (0, 0, 255) - Blue
- Barren Land: RGB (255, 255, 255) - White
- Unknown: RGB (0, 0, 0) - Black

![image](https://github.com/lfvm/crop_field_detection/assets/57450093/8f7576a6-110d-43ef-b31e-a02bc85d3c57)

![image](https://github.com/lfvm/crop_field_detection/assets/57450093/3e88832a-8d30-4b29-829a-2a0f60872cb2)

![image](https://github.com/lfvm/crop_field_detection/assets/57450093/6cfd567e-8406-43c8-973c-50884a589694)

## Collaborators

- [Fernando Valdeón](https://github.com/lfvm)
- [Uriel Aguilar](https://github.com/u-urieldev)
- [Diego Araque](https://github.com/DiegoAraque21)
