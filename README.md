# ResNet Transfer Learning for CIFAR100 Classification

## Project Overview
This project applies transfer learning using the ResNet architecture to classify images in the CIFAR100 dataset. It highlights the benefits of leveraging pre-trained models for efficient training and improved performance, especially for datasets with limited size.

---

## Dataset
### CIFAR100
- **Description**: A dataset of 60,000 color images (32x32 pixels), categorized into 100 classes.
- **Split**: 50,000 training images and 10,000 test images.
- **Challenges**:
  - Small resolution can make classification harder.
  - Imbalances in data distribution for some tasks.

---

## Methodology

### Model: ResNet
- **Architecture**: ResNet pre-trained on ImageNet.
- **Transfer Learning Strategy**:
  1. Freeze the last two layer groups to retain learned features.
  2. Replace the final fully connected layer with one tailored for CIFAR100 (100 outputs).
  3. Train only the unfrozen layers and the new classifier.

### Training
- **Loss Function**: Cross-entropy loss.
- **Optimizer**: Adam with learning rate scheduling.
- **Metrics**: Accuracy to measure performance.

### GPU Acceleration
- Training is optimized using a T4 GPU for faster computation.

---

## Workflow

1. **Data Preparation**:
   - Load and preprocess CIFAR100 using `torchvision`.
   - Apply normalization and augmentation.

2. **Model Customization**:
   - Load a pre-trained ResNet model.
   - Freeze specific layers.
   - Replace the fully connected output layer.

3. **Training**:
   - Train the network on the CIFAR100 dataset.
   - Use a scheduler for learning rate adjustments.

4. **Evaluation**:
   - Test the model using the CIFAR100 test set.
   - Visualize performance metrics.

---
