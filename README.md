# Solid Electrolyte GNN

A graph neural network for predicting ionic conductivity in solid electrolytes using crystal structure features from the Materials Project.

## Scientific Question
Can a GNN trained on crystal structure predict ionic conductivity, and which structural features drive high conductivity?

## Project Structure
- `data/` — raw and processed datasets
- `figures/` — publication-quality plots
- `models/` — saved model checkpoints
- `notebooks/` — Jupyter notebooks for each phase

## Phases
1. Data collection (Materials Project API)
2. EDA and baseline models
3. GNN training (PyTorch Geometric)
4. SHAP analysis and interpretation
5. Report

## Setup
```bash
conda create -n solid_electrolyte_gnn python=3.11
conda activate solid_electrolyte_gnn
pip install -r requirements.txt
cp .env.example .env  # add your Materials Project API key
```

## Results
*To be filled in as project progresses.*

## References
- Materials Project: https://materialsproject.org
- CGCNN: Xie & Grossman, PRL 2018
- PyTorch Geometric: Fey & Lenssen, 2019
