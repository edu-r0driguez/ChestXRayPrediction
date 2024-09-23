# Classification and Gradient-based Localization of Chest Radiographs

**Project Description**  
This project utilizes a DenseNet model to classify chest X-ray images, predicting the presence of one or more pathologies (or none). Additionally, it applies Grad-CAM (Gradient-weighted Class Activation Mapping) to visualize the regions of the X-ray images that influenced the model's predictions.

## Table of Contents
- [Installation](#installation)
- [Data](#data)
- [Model](#model-architecture)
- [Results](#results)
- [Visualization](#visualization)
- [Contributing](#contributing)
- [License](#license)

## Installation

To set up the project locally, follow these steps:

```bash
# Clone the repository
git clone https://github.com/username/repository.git
cd repository

# Install dependencies
pip install -r requirements.txt

```

## Data
- **Source**: The chest X-ray dataset is sourced from [here](https://www.kaggle.com/datasets/nih-chest-xrays/data/discussion?sort=undefined).
- **Structure**: Each image is labeled with one or more pathologies, and some images may have no findings.
- **Preprocessing**: Images were resized and normalized.

## Model
We employed a DenseNet-121 model, pre-trained on ImageNet, to classify chest X-rays. The model architecture includes:

- **Input Size**: 224x224
- **Pretrained**: Yes, on ImageNet
- **Output**: Multi-label classification for detecting pathologies

### Why DenseNet?
DenseNet offers efficient feature reuse and tends to work well for medical imaging tasks due to its compact and highly connected structure. Moreover, the project developed by [Priyavrat Misra et al](https://github.com/priyavrat-misra/xrays-and-gradcam/blob/master/README.md) compared the performance of XRay analysis on another dataset (with different categories) and found a significant improvement in performance despite having less parameters ($7.98$ Million) than VGG-16 and ResNet-18 ($138$ and $11.17$ Million parameters respectively)

### Grad-CAM
Grad-CAM is applied post-classification to highlight the areas of the image most relevant to the model's decision-making process. This helps with model interpretability.

## Visualization
- __Localization with Gradient-based Class Activation Maps__
[original](./assets/result_example.jpg)

In this image we can see a random XRay and the focus the model gives to the pathologies that should be observed to reach it's decision.
