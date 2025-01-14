# Noise Detection and Uncertainty Estimation in ECGs

## Overview

This repository contains the report for my project "Noise Detection and Uncertainty Estimation in ECGs". The project aims to enhance the interpretability of Electrocardiograms (ECGs) by detecting noise using deep learning techniques. This work was conducted as part of an internship at Cordys Analytics.

## Research Objectives

The primary goals of this project include:

- Identifying out-of-distribution (OOD) noisy ECGs before they are input into a diagnostic classifier.

- Optimizing deep learning models to distinguish noise from diagnostically significant abnormalities in ECGs.

- Investigating whether uncertainty in model predictions can be used to classify ECGs as noisy or uninterpretable.

## Methods

Several approaches were implemented and evaluated for noise detection and uncertainty estimation:

- **Supervised Binary Classification**: Trained a binary classifier to classify ECGs as "clean" or "noisy" using noise-labeled data.

- **Self-Supervised Learning**:

  - **Autoencoder Reconstruction Loss**: Trained an autoencoder on clean ECGs, using reconstruction loss as a measure of noise.

  - **Feature Space Clustering**: Trained feature extractors and used Gaussian Mixture Models (GMMs) on the extracted features to detect noise.

- **Uncertainty-Based Detection**: Explored the use of estimated epistemic uncertainty in diagnostic classifiers to identify noisy or OOD ECGs.

## Data

- **UMCU Dataset (private)**: 386,413 8-lead ECGs provided by the University Medical Center Utrecht (UMCU) along with labels for noise and over 100 diagnostic criteria.

- **PhysioNet 2011 dataset (public)**: 1,000 12-lead ECGs annotated for diagnostic interpretability and noise levels.

## Architectures

- **Binary Classifier**: Residual 1D CNN encoder with classification head.

- **Autoencoder**: Double residual encoder-decoder architecture.

- **Diagnostic Classifier**: Residual encoder with classification heads for multiple diagnostic labels.

- **SimCLR**: Contrastive learning framework with a projection head.

## Results

- Achieved strong ROC-AUC scores across various datasets.

- Demonstrated the potential of autoencoder reconstruction techniques for OOD detection.

- Feature clustering and uncertainty estimation were found insufficient for detecting noisy ECGs.
