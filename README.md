# VideoDistill

Video generation distillation research — training compact student models to replicate the output distribution of large video generation teachers.

## Research Focus

- **Score distillation**: adapting score distillation sampling (SDS/VSD/CSD) to video diffusion models
- **Consistency distillation**: single/few-step video generation via consistency trajectory models
- **Feature-level distillation**: intermediate feature matching between teacher and student
- **Reward distillation**: distilling human preference signals into smaller generators

## Repository Structure

```
configs/          # Training & distillation configs (YAML)
data/             # Dataset loaders and preprocessing
models/           # Student and teacher model definitions
distill/          # Distillation loss functions and trainers
eval/             # Evaluation metrics (FVD, CLIPSIM, temporal consistency)
scripts/          # Training, inference, and export scripts
```

## Getting Started

```bash
pip install -r requirements.txt
# Coming soon
```
