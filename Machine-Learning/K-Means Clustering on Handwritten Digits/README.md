# Handwritten Digit Clustering with K-Means

## Overview
This project explores unsupervised clustering of handwritten digit images using Scikit-learn's built-in Digits dataset. It compares K-Means initialization strategies, evaluates clustering quality, visualizes cluster composition, and studies how the number of clusters affects results.

## Dataset
- 1,797 grayscale images
- Each image is 8×8 pixels, represented by 64 features
- Ten known digit labels (0–9), used only for post-clustering evaluation and interpretation

## Methods
- Feature standardization with `StandardScaler`
- K-Means with `k-means++`, random, and PCA-based initialization
- Repeated runs to assess variability for stochastic initialization strategies
- Evaluation with inertia, homogeneity, completeness, V-measure, Adjusted Rand Index (ARI), Adjusted Mutual Information (AMI), and sampled silhouette score
- PCA projection for visualization
- Cluster-versus-true-digit composition heatmap and sample-image inspection
- Analysis of cluster counts from 2 to 15 using inertia and silhouette score

## Important interpretation notes
- The true labels are not passed to K-Means during fitting; they are used only for evaluation after clustering.
- Cluster IDs are arbitrary and do not necessarily correspond to digit labels.
- PCA's 2D view is a projection of clusters fitted in the original 64-dimensional feature space.
- The PCA-based initialization is an educational experiment using principal-component vectors as initial centers; it should not be assumed to outperform other strategies.
- Silhouette scores are estimated on a reproducible sample to reduce runtime.
- This is an educational benchmark on a small built-in dataset, not evidence of production readiness.
