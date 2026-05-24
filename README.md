# VideoDistill

Research on efficient video generation via distillation and attention acceleration for Diffusion Transformer (DiT) based video models.

## Research Mainline

### Distribution Matching Distillation
- **DMD** — Distribution Matching Distillation: one-step image/video generation by matching the student output distribution to the teacher via a regression loss + GAN-style distribution loss, avoiding classifier-free guidance at inference.
- **DMD2** — Extends DMD with improved training stability, fake-data-free distribution matching, and better handling of mode coverage.

### Attention Efficiency for Video DiT
- **SLA** ([arXiv 2509.24006](https://arxiv.org/abs/2509.24006)) — Sparse-Linear Attention: replaces full quadratic attention in video DiTs with a trainable fusion of sparse attention (critical tokens) and linear attention (background context), reducing the O(n²) bottleneck from long video token sequences.
- **SLA2** ([arXiv 2602.12675](https://arxiv.org/abs/2602.12675)) — Extends SLA with a learnable router (replaces heuristic weight-magnitude split), a more faithful sparse-linear decomposition with learnable mixing ratio, and quantization-aware fine-tuning (QAT) for low-bit attention. Achieves 97% attention sparsity and 18.6× attention speedup on video DiTs.

## Core Problems Addressed

| Problem | Method |
|---------|--------|
| Too many denoising steps (50→1) | DMD / DMD2 |
| Quadratic attention cost on long video sequences | SLA |
| Combined step + attention overhead | DMD2 + SLA joint training |

## Repository Structure

```
configs/       # Training & distillation configs (YAML)
data/          # Dataset loaders and preprocessing
models/        # Student / teacher model definitions, SLA attention modules
distill/       # DMD / DMD2 loss functions and distillation trainers
eval/          # Evaluation metrics (FVD, CLIPSIM, temporal consistency)
scripts/       # Training, inference, and export scripts
```

## Getting Started

```bash
pip install -r requirements.txt
# Coming soon
```
