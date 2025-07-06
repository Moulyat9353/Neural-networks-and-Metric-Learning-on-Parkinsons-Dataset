# Neural-networks-and-Metric-Learning-on-Parkinsons-Dataset

This repository contains code and experiments for predicting Parkinson’s disease progression using the Parkinson’s Telemonitoring Dataset from the UCI Machine Learning Repository. The task focuses on estimating motor UPDRS and total UPDRS scores from biomedical voice measurements.

## 📂 Dataset

- Source: [Parkinson’s Telemonitoring Data Set](https://archive.ics.uci.edu/dataset/189/parkinsons+telemonitoring)

- Size: 5,875 recordings from 42 patients

- Features: 26 biomedical voice measurements per record

- Targets:

  - Motor UPDRS (Unified Parkinson’s Disease Rating Scale)

  - Total UPDRS
 
## 📝 Problem Statement

- Goal: Predict motor UPDRS and total UPDRS from biomedical voice features.

- Methods Used:

  - Metric Learning with Gaussian Kernels

  - Neural Networks (single-layer regression)
 
## 🧪 Project Workflow

# 1. Data Preparation

- Randomly split dataset:

  - Train set: 70%

  - Test set: 30%

- Standardized all predictive features

- Excluded non-predictive feature subject#

# 2. Metric Learning with Gaussian Kernels

- Implemented metric learning for regression:

- Learned a low-dimensional linear transformation of input features

- Tuned number of components 𝑀 in:

  𝑀 ∈ {5, 10, 15, p}

  where p = number of predictive features

- Initializations tried:

  - PCA features (for M = 5, 10, 15)

  - Original features (for M = p)

- Evaluated models using:

  - R<sup>2</sup> score on training and test sets

# 3. Neural Network Regression

# (a) Without Early Stopping

- Built a single-layer feedforward neural network with:

  - Two outputs: motor UPDRS and total UPDRS

- Experimented with:

  - Hidden layer size

  - Activation functions

  - Optimizer

  - L2 regularization

- Chose design parameters by minimizing test set error.

- Reported:
  
  - R<sup>2</sup> on train and test sets

# (b) With Early Stopping

- Re-trained neural network using:

  - early_stopping=True

  - Validation fraction default (0.1) or tuned

- Compared:

  - Training and test performance vs. model without early stopping

- Early stopping prevents overfitting by halting training if validation error stops improving.

## 💡 Key Insights

- Metric learning significantly reduced dimensionality without much performance drop.

- Neural networks with early stopping performed better on the test set due to reduced overfitting.

- Careful tuning of hyperparameters like layer size, activation functions, and regularization was crucial for neural network performance.

## 🔧 Libraries

- scikit-learn

- pandas

- numpy

- matplotlib



