# BipedalWalker-v3 RL Solution

**Final Result:** 265.87 ± 43.46 points (Target: 300+)

---

## Repository Contents

**`BipedalWalker_Implementation.ipynb`** - Complete implementation containing all experiments, training code, evaluation, and visualization.

---

## Notebook Structure

### Setup & Installation
Environment setup, dependency installation (gymnasium, stable-baselines3, Box2D), GPU verification.

### Phase 1: Baseline PPO
Vanilla PPO implementation with default hyperparameters to establish baseline performance.  
**Result:** -87.03 ± 75.13 points

### Phase 2: Improved PPO
PPO with literature-based hyperparameters (n_epochs=30, ent_coef=0.01, vf_coef=0.5).  
**Result:** 208.35 ± 115.33 points

### Phase 3: Reward Shaping
Phase 2 + custom reward shaping (upright bonus, smoothness penalty, spin penalty).  
**Result:** 165.20 ± 88.35 points

### Phase 4: SAC Algorithm
Soft Actor-Critic implementation with reward shaping.  
**Result:** -19.62 ± 9.40 points

### Phase 5: Ultimate Model
Combined approach with observation normalization, action smoothing, and reward shaping.  
**Result:** -10.74 ± 1.68 points

### Phase 6: Extended Phase 3
Phase 3 trained to 1M total timesteps.  
**Result:** 160.38 ± 73.76 points

### Phase 7: Extended Phase 2
Phase 2 trained to 1M total timesteps.  
**Result:** 240.17 ± 85.37 points

### Phase 8: Extended to 2M Timesteps
Phase 2 trained to 2M total timesteps (final best model).  
**Result:** 265.87 ± 43.46 points

### Final Results & Visualization
Comparison plots, ablation study analysis, and comprehensive results summary.

### Video Recording
Records 3 episodes of the best model (Phase 8) and generates submission files.

---

## How to Run

1. Upload `BipedalWalker_Implementation.ipynb` to [Google Colab](https://colab.research.google.com/)
2. Enable GPU: Runtime → Change runtime type → GPU
3. Run all cells (takes ~5-6 hours total on A100 GPU)
4. Download outputs: video, training info, plots, and saved models

---

## Key Finding

**Simple hyperparameter tuning (n_epochs=30) + extended training (2M timesteps) outperformed all complex techniques.**
