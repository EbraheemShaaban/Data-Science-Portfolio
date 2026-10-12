# Classifier Comparison and Decision Boundary Visualization

## Overview
This educational project compares 10 scikit-learn classifiers across three synthetic binary-classification datasets and visualizes their decision boundaries. It also evaluates multiple classification metrics, uses stratified cross-validation, inspects a confusion matrix, and demonstrates hyperparameter tuning with `GridSearchCV`.

## Algorithms
- K-Nearest Neighbors
- Linear Support Vector Machine
- RBF Support Vector Machine
- Gaussian Process Classifier
- Decision Tree
- Random Forest
- Multi-Layer Perceptron
- AdaBoost
- Gaussian Naive Bayes
- Quadratic Discriminant Analysis

## Datasets
- **Moons:** two crescent-shaped classes.
- **Circles:** inner and outer circular classes.
- **Classification Data:** a generated two-feature binary classification dataset.

All datasets are generated in the notebook, so no external data files are required.

## What the Notebook Covers
1. Visual comparison of decision boundaries for 10 classifiers.
2. Train/test evaluation using accuracy, macro precision, macro recall, and macro F1-score.
3. Stratified 5-fold cross-validation, including mean accuracy and standard deviation.
4. A confusion matrix and classification report for an example RBF SVM.
5. Hyperparameter tuning for an RBF SVM using `GridSearchCV` on the training split.
6. Explanations of preprocessing, evaluation, and common limitations.

## Methodology Notes
- Scaling is performed in a scikit-learn pipeline to avoid fitting the scaler on held-out data.
- `clone` creates a fresh classifier for each experiment.
- Cross-validation uses stratified folds.
- Hyperparameter search is performed on the training split; the test split is reserved for final evaluation.
- Metric values are calculated when the notebook runs. This README intentionally does not claim specific scores.

## Limitations
- The datasets are synthetic and small; they do not demonstrate real-world business performance.
- Results can vary by dataset generation, split, and scikit-learn version.
- Grid search explores a deliberately small parameter grid for learning purposes, not exhaustive optimization.
- For a stronger real-world project, use representative data, compare against a baseline, validate assumptions, and select metrics based on the problem's costs.

