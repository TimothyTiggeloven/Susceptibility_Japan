# Hazard Susceptibility CNN

Deep learning models for natural hazard susceptibility mapping using convolutional neural networks (CNN).

## Overview

This repository contains CNN-based models for predicting susceptibility to natural hazards including landslides, floods, tsunamis, and multi-hazard scenarios. The framework supports base models, ensemble methods, and meta-learning approaches. Methodological paper can be found here: https://doi.org/10.1175/AIES-D-25-0039.1. 

Please cite as: Tiggeloven, T., Ferrario, D. M., Claassen, J. N., Jäger, W. S., Shapovalova, Y., Koyama, M., de Ruiter, M.C., Daniell, J.E., Torresan, S. & Ward, P. J. (2025). A Global Approach for Mapping Multi-Hazard Susceptibility Using Deep Learning: A Case Study in Japan. Artificial Intelligence for the Earth Systems, 4(4), 250039.

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
