# Cat vs Dog Image Classification Using PyTorch CNN

## Overview

This project implements a Convolutional Neural Network (CNN) using PyTorch to classify images into two categories: cats and dogs.

The project explores image preprocessing, CNN architecture design, model training, data augmentation, performance evaluation, and predictions on new images.

## Objectives

- Understand the basic working of CNNs.
- Build and train a CNN using PyTorch.
- Apply data augmentation to improve generalization.
- Evaluate the model using accuracy, loss, a confusion matrix, and classification metrics.
- Compare a baseline CNN with a CNN trained using data augmentation.
- Build a reusable pipeline for predicting the class of a new image.

## Dataset

The project uses the Cats vs Dogs image dataset.

- **Classes:** Cat and Dog
- **Image size:** 128 × 128 pixels
- **Candidate images:** 24,998
- **Training images:** 19,998
- **Validation images:** 5,000

The dataset was divided into training and validation sets. Images were converted to RGB format, resized, and transformed into PyTorch tensors.

### Data Augmentation

The augmented model uses:
- Random horizontal flipping
- Random rotation of up to 10 degrees

These transformations are applied during training to expose the model to variations of the input images. Validation images are resized and converted to tensors without random augmentation.

## Model Architecture

The CNN consists of:

1. **Convolutional layer 1:** Extracts initial image features using 16 filters.
2. **ReLU activation:** Introduces non-linearity.
3. **Max pooling:** Reduces spatial dimensions.
4. **Convolutional layer 2:** Learns more complex features using 32 filters.
5. **ReLU activation:** Introduces non-linearity.
6. **Max pooling:** Further reduces spatial dimensions.
7. **Flatten layer:** Converts feature maps into a feature vector.
8. **Fully connected layer:** Produces two output logits for Cat and Dog classification.

### Training Configuration

| Parameter | Value |
|---|---|
| Framework | PyTorch |
| Optimizer | Adam |
| Learning rate | 0.001 |
| Loss function | Cross-Entropy Loss |
| Batch size | 32 |
| Image dimensions | 128 × 128 |
| Training epochs | 15 |
| Output classes | 2 |

## Results

The following results are from the recorded validation experiments.

| Model | Best validation accuracy |
|---|---:|
| Original CNN | 76.54% |
| CNN with data augmentation | 81.92% |

The augmented CNN improved the best recorded validation accuracy by **5.38 percentage points**.

### Evaluation

The augmented model was evaluated on all 5,000 validation images.

| Metric | Cat | Dog |
|---|---:|---:|
| Precision | 82.57% | 81.29% |
| Recall | 80.92% | 82.92% |
| F1-score | 81.74% | 82.10% |

**Overall validation accuracy: 81.92%.**

The project also includes training and validation curves, a confusion matrix heatmap, and a comparison of the two CNN experiments.

> **Note:** These are validation results, not results from an independent held-out test set. Performance on a separate test set has not yet been established.

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Seaborn
- Pandas
- Scikit-learn
- Google Colab

## Project Structure

```text
cat-dog-cnn-pytorch/
├── cat_dog_cnn.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── cat_dog_cnn_model.pth
├── cat_dog_cnn_augmented.pth
└── results/
    ├── training_curves.png
    ├── confusion_matrix.png
    └── model_comparison.png
```

The `results/` directory is intended for exported figures. The notebook contains the implementation and experiments.

## How to Run

1. Clone or download this repository.
2. Open `cat_dog_cnn.ipynb` in Google Colab or Jupyter Notebook.
3. Install the required Python libraries.
4. Download the dataset from its original source and arrange it in the directory structure expected by the notebook.
5. Run the notebook cells in order to prepare the dataset, train the CNN, evaluate the model, and make predictions.

A GPU is recommended to reduce training time but is not mandatory.

## Future Improvements

- Evaluate the models on an independent test set.
- Experiment with dropout and batch normalization.
- Apply learning-rate scheduling and early stopping.
- Compare the custom CNN with transfer-learning models such as ResNet or MobileNet.
- Improve prediction reliability through additional data and systematic error analysis.

## Learning Outcomes

This project provided practical experience with CNN architecture design, PyTorch training loops, data augmentation, model evaluation, and image classification.

## Disclaimer

This is an educational image-classification project. The reported results are specific to the dataset split and training configuration used in these experiments.

