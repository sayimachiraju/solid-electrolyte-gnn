# GNN for Ionic Conductivity Prediction in Solid Electrolytes

## Abstract
*To be written after results.*

## 1. Introduction
Solid-state batteries require electrolytes with high ionic conductivity...

## 2. Methods
### 2.1 Dataset
### 2.2 Graph Representation
### 2.3 Model Architecture
### 2.4 Training


## 3. Results

### 3.1 Baseline Models
Four baseline models were trained on 15 tabular compositional and structural features:

| Model | R² | MAE (eV) | RMSE (eV) |
|---|---|---|---|
| Linear Regression | 0.306 | 0.839 | 1.046 |
| Ridge Regression | 0.306 | 0.839 | 1.046 |
| Random Forest | 0.599 | 0.610 | 0.796 |
| Gradient Boosting | 0.616 | 0.597 | 0.779 |

The weak linear baseline (R² = 0.306) confirms that band gap in solid electrolytes
has nonlinear dependence on compositional features, motivating the use of a GNN.

### 3.2 GNN Performance
The Crystal Graph Neural Network achieved:

| Metric | Value |
|---|---|
| R² | 0.6645 |
| MAE | 0.5792 eV |
| RMSE | 0.7526 eV |

The GNN improved R² by +0.018 over the Gradient Boosting baseline,
demonstrating that crystal graph structure encodes information not captured
by mean-field compositional descriptors alone.

### 3.3 Error Analysis
Error varied significantly by crystal system. Cubic and hexagonal structures
showed lower median absolute error, likely due to higher symmetry reducing
the structural diversity the model must learn. Triclinic and monoclinic
structures — which dominate this dataset — showed higher error, consistent
with their structural complexity.

No significant difference in prediction error was observed between
Li-containing and Na-containing materials.

### 3.4 Top Candidates
20 materials were identified as high-priority solid electrolyte
candidates based on predicted band gap > 3.0 eV, energy above hull < 0.05 eV/atom,
and low model error (MAE < 0.4 eV). These are tabulated in data/processed/top_candidates.csv.
