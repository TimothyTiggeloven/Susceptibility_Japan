# Hazard Susceptibility CNN

Deep learning models for natural hazard susceptibility mapping using convolutional neural networks (CNN).

## Overview

This repository contains CNN-based models for predicting susceptibility to natural hazards including landslides, floods, tsunamis, and multi-hazard scenarios. The framework supports base models, ensemble methods, and meta-learning approaches.

## Models

- **Base Model**: Individual CNN for single hazard prediction
- **Ensemble Model**: Multiple CNNs with transfer learning
- **Meta Model**: MLP combining multiple hazard predictions

## Usage

```bash
python main.py <test_region> <hazard_type> <hyperparameter_tuning> <model_choice>
```

**Parameters:**
- `test_region`: 'sado', 'hokkaido', or 'japan'
- `hazard_type`: 'Landslide', 'Flood', 'Tsunami', or 'Multihazard'
- `hyperparameter_tuning`: 'True' or 'False'
- `model_choice`: 'base', 'ensemble', 'meta', or 'lr'

**Example:**
```bash
python main.py sado Landslide False base
```

## Dependencies

- TensorFlow/Keras
- NumPy, Pandas
- Scikit-learn
- Matplotlib
- Weights & Biases
- SHAP (optional)

## Data Structure

Expected input data in `Input/Japan/npy_arrays/` with masked arrays for environmental variables (elevation, slope, landcover, etc.).

## Output

Models save predictions as `.npy` files and visualizations in `Output/{region}/{hazard}/` directory.
