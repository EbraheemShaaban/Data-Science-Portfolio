Breast Cancer Classification Using Machine Learning

Project Overview

This project applies Machine Learning classification algorithms to distinguish between malignant and benign breast cancer cases using numerical features extracted from breast cancer diagnostic data.

The project focuses on data preprocessing, feature scaling, model training, performance evaluation, hyperparameter tuning, and cross-validation.

Important: This project is for educational purposes only and is not intended for clinical diagnosis or medical decision-making.

Dataset

The dataset contains 569 records and 30 numerical predictive features, along with a diagnosis label.

Malignant (M): 212 records

Benign (B): 357 records

The dataset includes measurements such as radius, texture, perimeter, area, smoothness, compactness, concavity, and symmetry.

The id column and the unnecessary Unnamed: 32 column are removed during preprocessing.

The target variable is encoded as:

1: Malignant

0: Benign

Objectives

Explore and preprocess the dataset.

Analyze relationships between features using a correlation matrix.

Prepare training and testing datasets.

Apply feature scaling using StandardScaler.

Train and compare Support Vector Machine (SVM) and K-Nearest Neighbors (KNN) classifiers.

Optimize model hyperparameters using GridSearchCV.

Evaluate model performance using classification metrics and cross-validation.

Technologies and Libraries

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

Jupyter Notebook
