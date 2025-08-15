# Loss Function Exploration in Medical Image Segmentation

## Overview
This project investigates how different loss function combinations affect U-Net performance for medical image segmentation, specifically focusing on gastrointestinal polyp detection.

## Motivation
- Manual polyp detection is time-consuming and prone to human error
- Automated segmentation can improve consistency and speed in medical diagnosis
- Limited research exists on loss function impact vs. model architecture modifications
- Missing polyps (false negatives) can have serious clinical consequences

## Problem Statement
While much research focuses on improving model architectures for medical image segmentation, there's insufficient attention on how loss function selection affects performance. This study aims to determine which loss function combinations work best for U-Net-based polyp segmentation.

## Datasets
- **Kvasir-SEG**: 1,000 polyp images with manual annotations (resized to 320×320)
- **CVC-ClinicDB**: Clinical polyp dataset (original 384×288 pixels)
- **CVC-ColonDB**: Colon polyp dataset (resized from 574×500 to 320×320)

## Loss Functions Tested
- Binary Cross-Entropy (BCE)
- Dice Loss
- Adaptive t-vMF Dice Loss
- Focal Loss
- Tversky Loss
- Various hybrid combinations (11 total configurations)

## Model Architecture
U-Net with Attention Gates for enhanced feature selection and improved performance.

## Key Tasks
1. Implement U-Net with Attention mechanism
2. Train models with different loss function combinations
3. Evaluate performance using multiple metrics: Accuracy, Dice Coefficient, Precision, Recall, F1 Score, IoU, Boundary F1, and Boundary IoU
4. Conduct statistical analysis to determine significant differences
5. Provide practical guidance for loss function selection

## Results
- Adaptive loss functions generally improve Dice scores
- Tversky-based losses excel at reducing false negatives
- CVC-ColonDB showed highest variability due to smaller foreground regions
- Statistical tests confirmed reliable improvements over baseline models

## Technologies Used
- Python
- PyTorch
- CUDA (NVIDIA P100 GPU)
- NumPy, Pandas, Matplotlib, Seaborn

## Repository Structure
- Separate implementations for each dataset (Kvasir, CVC-ClinicDB, CVC-ColonDB)
- Consistent hyperparameters across experiments for fair comparison
- Statistical analysis and visualization code

## Future Work
- Expand to 3D datasets and other medical domains
- Test with transformer-based architectures
- Explore additional loss function combinations
- Scale to larger, multi-center clinical datasets
